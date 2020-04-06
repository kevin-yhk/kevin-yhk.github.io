---
layout: post
title:      "Sinatra Project - Car Management System"
date:       2020-04-06 02:20:02 +0000
permalink:  sinatra_project_-_car_management_system
---


This project and the Sinatra curriculum gave me a small taste of what it was like to create a web application. 

Like the previous project, it wasn't necessarily a walk in the park but working on a topic (cars) that I genuinely had passion for made this project more fluid and less stressful to create. Needless to say, it felt great to have the project up and running when I entered in that final line of code. 

My Sinatra app is titled Virtual Car Garage, pretty much where you can enter in your car's information and then having the ability to edit your cars, add more cars, or delete car entries.  

For this project, I created two models: the user class and the car class.  The user class has a relationship with the car class in that users have many cars and the car belongs to the user.  Insted of writing a plethora amount of code using ORMs, Ruby has blessed us with ActiveRecord which eliminates the need to write almost anything in our model classes.  
```
class User < ActiveRecord::Base
    has_many :cars
    has_secure_password

    validates :username, :email, uniqueness: true
    validates :username, :email, :password, presence: true
end 
```
```
class Car < ActiveRecord::Base
    belongs_to :user 
end 
```
This is all the code I had to write in my model classes since we are able to inherit methods from ActiveRecord, there is no reason at all to tire ourselves by writing extra code that would do the same job from inheriting from ActiveRecord. 

Next in my application controller, I added in helper methods 
```
helpers do
    def logged_in?
      !!session[:user_id]
    end

    def current_user
      User.find(session[:user_id])
    end
  end
	```which will help me perform validations of making sure that certain processes will be executed depending on whether the user is logged in and gaining specific access to sites assuming they are the current user. 
	
I then created controllers for both my user and car models with their corresponding views, the views being the front end portion of this project while the controllers serve as backend, the behind the scenes aspect of this project.  

I know that this is a very small portion of what it is like doing full-stack, but I think as the program goes on  I will probably establish an affinity for either front or backend.  However, I hope I become more than proficient in both fields to be able to call myself a full-stack engineer. 
