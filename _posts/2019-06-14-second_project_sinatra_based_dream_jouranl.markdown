---
layout: post
title:      "Second Project: Sinatra based Dream Jouranl"
date:       2019-06-14 15:52:02 -0400
permalink:  second_project_sinatra_based_dream_jouranl
---


For my second project, I created a Sinatra based website of a Dream Journal. I like to record my night dreams in a paper journal and over time look for themes throughout my dreams. So I thought this would be a good project to keep track of dreams and also be able to tag each dream with categories so it is possible to view dreams by category. It was quite exciting to build an actual website and see how all the parts of the Model View Controller (MVC) framework interact with each other.

Through this project, I experienced the power of ActiveRecord Associations. A user can have many dreams, and a dream belongs to a user. But what about the relationship with dreams and categories? I liked the possibility of being able to tag a dream with multiple categories. So that meant this is a many_to_many relationship where a dream can have many categories and a category can have many dreams. So in addition to having user, dream, and category tables, I also created a join table of dream_category in order for the many_to_many relationship between dream and category to work. This join table then allows for any dream instance to see all categories associated with that dream using the `.categories` method and for any category instance to see all dreams associated with that category using the `.dreams` method. One very interesting thing I found was by connecting the dream and category models through this many_to_many association, I was also able to create an association with user and categories through dreams. By having the class Dream have both` has_many :categories, through: :dream_categories` and `belongs_to :user`, then I able able to make the association class User `has_many :categories, through: :dreams`. This is quite incredible and shows one example of how powerful ActiveRecord is. With this new association, on any user instance using the `.categories` method we can see directly all categories associated with that user (return is an array of all categories the user has associated with it). See the full model associations for all classes below.

```
class User < ActiveRecord::Base
  has_many :dreams
  has_many :categories, through: :dreams
end

class Dream < ActiveRecord::Base
  belongs_to :user
  has_many :dream_categories
  has_many :categories, through: :dream_categories
end

class Category < ActiveRecord::Base
  has_many :dream_categories
  has_many :dreams, through: :dream_categories
end

class DreamCategory < ActiveRecord::Base
  belongs_to :dream
  belongs_to :category
end
```

