---
layout: post
title:      "Sinatra Reflection "
date:       2020-10-11 19:27:40 +0000
permalink:  sinatra_reflection
---

## where the magic comes from



With software engineering, you can never move on to another topic; instead, you are always building. So after spending weeks understanding databases and how to efficiently create and store information, it was time to make it possible for a User to interact with this data. With the introduction of controllers and the view pages that display our data, the amount of hard-coding needed for a simple application can sound a little daunting. That’s where Active Record and Sinatra come in, with a few extra lines in your Gemfile, building out relational databases and their user interface becomes easier.

Just because there are extra bits of software helping out, it does not mean we can just sleep on the job. Keeping track of which files use which add-on, and the particular branch of that add-on is important. 

Active Record deals with the database, it handles the creation of the database tables and the associations between data. The classes in which the database tables are created inherit functioning from the Migration branch of Active Record, this is denoted by:
class CreateGeologists < ActiveRecord::Migration[5.2]

While the models, or different objects your database is dealing with, will inherit from Base, allowing them to relate to one another. The associations are created within the class, by stating whether that model ‘belongs_to’ or ‘has_many’ of the other model(s).
class Geologist < ActiveRecord::Base
	   has_many :rocks



| Active Record     | Database Tables    | < ActiveRecord::Migration     |
|                                   | Models                      | < ActiveRecord::Base   |
|                                   |                                      | has_many // belongs_to |


Sinatra on the other hand, works only with the controllers. The main inherits from Sinatra::Base, and the subsequent controllers inherit from the main controller giving them all the same abilities to receive routes and render views. 
class ApplicationController < Sinatra::Base



