---
layout: post
title:      "Third Project: Ruby on Rails based Project Align"
date:       2019-07-21 00:19:33 -0400
permalink:  third_project_ruby_on_rails_based_project_align
---


My third project called Project Align is a Ruby on Rails website that is a project management tool for teams to keep track of projects with associated tasks. Users are able to create projects that other users on their teams can also see and everyone on the team is able to keep track of associated tasks that need to be completed.

This was my first Ruby on Rails application and it was incredible to see the strengths of Ruby on Rails and how it works. Through this project I was able to explore various aspects of Ruby on Rails that make it so powerful including aspects such as Rails generators where you are able to create models and migrations easily and Active Record association macros such as has_many and belongs_to. Learning Sinatra first was helpful in understanding the foundations for Ruby on Rails and the basic structure for a model-view-controller (MVC) structured web application. 

In Project Align, I wanted to have the ability to create a project and several associated tasks for the project at the same time. I was able to do this using nested attributes. By setting up the right Active Record associations (Project has_many tasks and Task belongs_to project) and using the accepts_nested_attributes_for class method, the project (parent) is created along with the nested attributes of tasks (children) which are created through the parent. This also works with the edit/update actions where the project and nested tasks can be edited at the same time.

```
class Project < ApplicationRecord
  has_many :tasks
  accepts_nested_attributes_for :tasks, reject_if: proc { |attributes| attributes['content'].blank? }
end

class Task < ApplicationRecord
  belongs_to :project
end

```

You can also add options to the nested attributes such as my example above of only allowing nested tasks to be created if their content is not blank. Nested attributes in Rails are quite powerful.
