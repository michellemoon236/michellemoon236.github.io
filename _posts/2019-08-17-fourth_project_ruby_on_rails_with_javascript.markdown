---
layout: post
title:      "Fourth Project: Ruby on Rails with Javascript "
date:       2019-08-17 18:22:48 +0000
permalink:  fourth_project_ruby_on_rails_with_javascript
---


My fourth project is an expansion of my previous Ruby on Rails website, Project Align, which is a project management tool for teams. For this project, I expanded the website to have dynamic Javascript features. Project Align is a tool that enables teams to keep track of projects they are working on along with the associated tasks for the project that need to be completed. Each team member is able to view and edit the project and tasks on their dashboard. 

With this project, I was able to experiment with the power of Javascript and its vast ability to manipulate the Document Object Model (DOM). With Javascript, I was able to change several features making it easier for users to navigate through the website. For example, without Javascript, every time a new task was added to a project, the webpage was directed to a whole new page with a form to take in the information for the new task. However, with Javascript, I was able to change this so on the same page where the project information is displaying I could inject a form right into the DOM to take in information for a new task without doing a whole new page load. Also, with another Javascript function, I was able to add a function to view the task details right on the project show page again without a new page load.

This project also let me explore building and interacting with an Application Programming Interface (API). I used Active Model Serializer to serialize Ruby object data to JavaScript Object Notation (JSON), which then lets me build an internal API that is in an easily accessible format. Then, I was able to use the Javascript fetch function to access the API data. I was able to practice using the fetch function several times and see it is a great and simple way to fetch JSON data.

