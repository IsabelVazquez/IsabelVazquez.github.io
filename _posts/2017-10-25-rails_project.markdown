---
layout: post
title:      "Rails Project"
date:       2017-10-26 01:01:05 +0000
permalink:  rails_project
---


During my Rails project, I wanted the Recipe form to write to the Cuisine model. I tried the following originally while whitelisting the parameters and building the associations in the controller:
```
class Cuisine < ApplicationRecord
  has_many :recipes
  has_many :users, through: :recipes
 ** validates :name, uniqueness: true**
end

class Recipe < ApplicationRecord
  belongs_to :cuisine
  **accepts_nested_attributes_for :cuisine**
end
```

However, the above resulted in `Cuisine name is already taken` instead of either creating or finding in the Cuisine model. Without the name validation in Cuisine, the Recipe form ended up creating various instances of Cuisine without recognizing that the name already exists.

Therefore, I deleted the bolded code above and did the following custom writer.
```
def cuisine_attributes=(attributes_hash)
   self.cuisine = Cuisine.find_or_create_by(:name => attributes_hash[:name])
end
```
