
# Questions
1. What is the event loop in JS? How do micro and macro tasks being handled?
Provide an example for micro and a macro task
2. What is AOT in Angular?
3. Explain the difference between ngOnInit and component Constructor.
4. What are Angular Elements?
5. What change detection strategy leverages immutable data?
6. Why would you use renderer methods instead of using native element methods?
7. How would you insert an embedded view from a prepared TemplateRef?
8. How to detect a route change in Angular?
9. What is Reactive programming and how does it relate to Angular?
10. Explain briefly about Factory method design pattern?
11. How would you use a 3rd party library in Angular?
12. What is NgZone? Could you provide some particular examples of its usage?




# Code
## Guidelines
1. Components must use `OnPush` change detection strategy
2. Your project should have `fullTemplateTypeCheck` set to true
3. Your view encapsulation should be set to None
4. Write at least 2 unit tests for different items (e.g. 1 for service, 1 for the component)
5. You can use whatever UI / Component library you prefer
6. Data
   1. Endpoint: https://my-json-server.typicode.com/danzrou/json-placeholder/products
   2. Supports:
      1. GET
      2. POST (add)
      3. PUT (update)
      4. DELETE (remove)
## Exercise
In the following exercise, you will be implementing a minimal shopping site.
Your app should include:
1. Header:
   1. The header should have the title “Shopping” 
   2. An icon of a shopping cart with a total amount of items currently in the cart
   3. Clicking on the icon should open a menu which displays the items, their amount and the total price of the cart
2. Content
   1. Will include 2 tabs: View and Edit
   2. Each tab will navigate to a separate route, whereas each route loads the related module
3. View 
   1. Displays all shopping items as cards.
      1. Each card should include the item’s name, description, type (UI representation) and price
      2. The card’s footer should include:
         1. Add - this will add the item to the cart
         2. Remove - will remove the item from the cart
         3. Amount - a counter for the number of items of this type which will be added to the cart
   2. Add a filter to the view tab which filters the displayed items.
      1. Filter by item type
      2. Filter by a search term - search term will be applied to the item’s name and/or description. 
         1. Filtering by search term will highlight the search term in the item’s name and description
      3. Filter by price range
4. Edit
   1. Should include a list/table of the available items.
   2. Should include an Add button (on top) which allows adding a new item using a dialog
   3. Each item should have last modified date, displayed in the format ‘dd-mm-yyyy hh:mm’
   4. Each item should have an edit button which will open a dialog
   5. Edit dialog
      1. Should allow editing the name description, and price of the item
      2. Type should be displayed but cannot be edited
      3. Should includes Submit and Cancel buttons
   6. Submit
      1. Will update the item’s last modified to the current time
      2. The details of the item will be updated both on View and Edit tabs
   7. Cancel
      1. Will close the dialog
Models
  ```
  export interface ShoppingCart {
  items: ShoppingCartItem;
  totalAmount: number;
}

export interface ShoppingCartItem {
  id: number;
  name: string;
  description: string;
  type: ShoppingCartItemType;
  price: number;
}

export const enum ShoppingCartItemType {
  Beverage,
  Snack,
  Fruit,
  Vegetable,
  Meat
}
  ```

Bonus Questions
* Implement a minimal example of Angular’s *ngFor
* Implement Promise.all with function callbacks
