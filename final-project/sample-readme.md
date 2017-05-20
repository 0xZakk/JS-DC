# Overview
The application I would like to build for my final project is a Farmer's Market Explorer: Farmer.ly! Using data from the Department of Agriculture ([here](https://catalog.data.gov/dataset/farmers-markets-geographic-data)), I will build an application that lets users sign in, search for farmers markets in their city and 'favorite' their favorite local markets. Additionally, I'll include the ability for users to show 'stories' on their profile, so that other users can see how they Farmers Market.

# UI Draft

My application will have the following views or pages:
  - a homepage that inspires people to sign up and search for farmers markets
  - a sign up page (for signing up new users)
  - a log in page (for logging in existing users)
  - a search page, so that users who have signed up can search for farmers markets
  - a search results page, to display the list of farmers markets that meet the search criteria
  - a show page for an individual farmers market, listing all the information about a specific farmers market and the users who attend this farmers market
  - a user profile page, listing all the information about a user and all their favorite farmers market


# Technical Requirements
My application will rely on the following packages:
  - express
  - mongo
  - mongoose
  - passport
  - passport-local
  - passport-local-mongoose

My application will have the following features:

### Authorization
Users will be able to visit the sign up page to put in their email, username and password and create a new account in my application. They will add this information through a form that will be submitted to my express server, which will have a route for handling this post request. Inside that route handler, I will take the email, username and password and register a new user, then authenticate that user. If all this works, then the user will be logged in and redirected to their new profile. After a user has created an account, they'll be able to log in to my application through the login page. The login page will have a form for either the user's username or email address and their password. When they submit this form, it will post this information back to my server. The route handler will then take the email or username and password and try to authenticate the user. If it works, it will redirect them to their profile. If it doesn't work, I'll send them back to the login page and display the error, so they can try to login again.

### Searching for farmers markets
I will use the dataset from the Department of Agriculture to seed a database of farmers markets. Then, on the search page, I will have a set of criteria the user can use to search for farmers markets in their area. This search form will go to my server where I will take these parameters and find all the farmers markets that fit them. Then I will render a search results view, listing all the results.

### Favoriting farmers markets
When a user is looking at the list view of farmers market, they will have the option to favorite a farmers market by clicking on a start icon next to the farmers market's name. When they click on this, I will use AJAX to send a post request with the ID of the farmers market back to my server. Then, in a route handler I will add that ID to an array of favorited farmers markets on the currently signed in user. Then, when a user loads their profile or a user loads the profile of another user, I will find all of their favorited farmers markets and display them on the profile.
