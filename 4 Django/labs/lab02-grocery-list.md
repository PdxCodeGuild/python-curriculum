# Lab 2: Grocery List

### Let's create a simple grocery list app. 


Create an app `grocery_list` with a model called `GroceryItem`

`GroceryItem` should have the following fields:
- description (`CharField`)
- created_date (`DateField`)
- completed_date (`DateField`)
- completed (`BooleanField`)


The user should be presented with an input field and a button (in a form). When the clicks the button, it should save the data to the server and show the newly-added item in the list. The user should be presented with a list of incomplete items and a list of complete items. The user should be able to mark an item complete/incomplete and be able to delete an item.
