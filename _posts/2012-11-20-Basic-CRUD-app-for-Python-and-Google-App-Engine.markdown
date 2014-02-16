---
layout: post
title: Basic CRUD app for Python and Google App Engine
date: 2012-11-20
---

I wrote a very basic CRUD app for Google App Engine in Python.  It's a basic sample on how to add, edit, delete, and list a single entity in GAE.  I didn't see anything like this on the web when I was learning GAE.  I hope this helps you.

You need python 2.7 installed and Google App Engine installed to get up and running.  I ran into one issue on Windows where nothing worked until I specified the version of python in GAE.  I didn't have this issue on Mac OS X. 

### basiccrud.py

{% highlight python %}
import webapp2
import cgi
import datetime
import urllib

from google.appengine.ext import db
from google.appengine.api import users

#blog###################################################
class BlogPost(db.Model):
    title = db.StringProperty()
    content = db.StringProperty()
    date = db.DateTimeProperty(autonowadd=True)

def BlogPostKey():
    return db.Key.frompath('Blog','defaultblog')

def BlogById(id):
    return BlogPost.getbyid(id,parent=BlogPostKey())


#PAGES#################################################
class MainPage(webapp2.RequestHandler):
    def get(self):
        self.response.write(
            '<html>'
                '<body>'
                    '<a href="/AddPost">AddPost</a>')

        BlogPosts = db.GqlQuery("select * from BlogPost order by date desc limit 10")

        self.response.write('<ul>')

        for post in BlogPosts:
            self.response.write('<li>{title} at {date} key: ' \
            '{key}<a href="/EditPost?id={key}">Edit</a></li>'
                .format(title=post.title,date=post.date,key=post.key().id()))

        self.response.write('</ul>')
        self.response.write('</body></html>')


class AddPost(webapp2.RequestHandler):
    def get(self):
        self.response.write(
            '<html>'
                '<body>'
                '<form action="/AddPost" method="POST">'
                    'TITLE:<input type=text name=title value=""/>'
                    '<br>CONTENT:<input type=text name=content value=""/>'
                    '<br><input type=submit text="submit"/>'
                '</form>'
                '</body>'
            '</html>')
    def post(self):
        title = self.request.get('title')
        content = self.request.get('content')
        newpost = BlogPost(parent=BlogPostKey())
        newpost.title = title
        newpost.content = content
        newpost.put()
        self.redirect('/')

class EditPost(webapp2.RequestHandler):
    def get(self):
        id = int(self.request.get('id'))
        newpost = BlogById(id)
        self.response.write(
            '<html>'
                '<body>'
                '<form action="/EditPost" method="POST">'
                    '<input type="hidden" value="{id}" name="id">'
                    'TITLE:<input type=text name=title value="{title}"/>'
                    '<br>CONTENT:<input type=text name=content value="{content}"/>'
                    '<br><input type=submit value="Save"/>'
                '</form>'
                '<form action="/DeletePost" method="POST">'
                    '<input type="hidden" value="{id}" name="id">'
                    '<br><input type=submit value="delete"/>'
                '</form>'
                '</body>'
            '</html>'
            .format(title=newpost.title,
                content=newpost.content,id=newpost.key().id()))
    def post(self):
        title = self.request.get('title')
        content = self.request.get('content')
        id = int(self.request.get('id'))
        newpost = BlogById(id)
        newpost.title = title
        newpost.content = content
        newpost.put()
        self.redirect('/')

class DeletePost(webapp2.RequestHandler):
    def post(self):
        id = int(self.request.get('id'))
        newpost = BlogById(id)
        newpost.delete()
        self.redirect('/')


app = webapp2.WSGIApplication([('/', MainPage),
                                ('/AddPost',AddPost),
                                ('/EditPost',EditPost),
                                ('/DeletePost',DeletePost)],
                              debug=True)

{% endhighlight %}

### app.yaml

{% highlight yaml %}
application: basiccrud
version: 1
runtime: python27
api_version: 1
threadsafe: true

handlers:
- url: /.*
  script: basiccrud.app
{% endhighlight %}