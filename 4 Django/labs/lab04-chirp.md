# Lab 4: Chirp (Twitter Clone)

**Write a simple MVP (minimum viable product) clone of Twitter!**
Let's build a copy of the popular social media site Twitter!


You will need to create two apps for this project, `posts` and `users`.

The `posts` app will have a `Chirp` model.

`Chirp` should contain the following fields:
- user (`ForiegnKey`)
- message (`CharField`)
- created_at (`DateTimeField`)
- likes (`IntegerField`)

The `users` app will have a `User` model.

`User` should extend the built in django user object and include the following fields:
- username (`CharField`)
- password (`CharField`)
- created_date (`DateField`)


Your project will also need to have the following functionality:
* User login / sign up
* The ability to post chirps of some constrained length (eg. 128 characters)
* A public profile page that shows all the users chirps
* Basic UI (navbar, footer) and styling (either by hand or with a framework)
