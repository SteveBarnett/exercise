# Front End Developer assessment

Feel free to use any git workflow/branching strategy which best demonstrates your knowledge of git.

## HTML/CSS knowledge check

- Give a brief description of the Box Model​ in your own words.
- Feel free to illustrate with examples from your experience.

The box model is the combination of the following things that determine the size of a given HTML element. From the outside in:

- width / height (the content of the box);
- padding (the space between the content and the border);
- border (the, uh, border).
- margin (the space between the border and surrounding elements);

Other box-y things worth noting are `outline` and `box-shadow`. These don't mess with the box model, making them great choices to use for `:focus` styles for a11y: show what's got focus without messing with the layout.

## JS exercise

```js
const sales = [
  {
    itemSold: "Football",
    price: 19.99,
    dateSold: "2018-04-07",
    id: "j_123",
  },
  {
    itemSold: "Trainers",
    price: 159.95,
    dateSold: "2018-03-02",
    id: "t_acds1",
  },
  {
    itemSold: "Cricket bat",
    price: 204.97,
    dateSold: "2018-04-05",
    id: "j_456",
  },
  {
    itemSold: "Rugby ball",
    price: 30.0,
    dateSold: "2017-04-22",
    id: "t_acds3",
  },
  {
    itemSold: "Hockey stick",
    price: 54.95,
    dateSold: "2017-03-19",
    id: "j_999",
  },
];
```

### 1. Return the sum of the price of all properties as a single value.

```js
// Return 469.86
sales
  .reduce((runningTotal, sale) => {
    return runningTotal + sale.price;
  }, 0)
  .toFixed(2);
// Since it's a price, add toFixed(2)
```

### 2. Return the items which were sold in 2017.

```js
// Returns
// [
//   {
//     "itemSold": "Rugby ball",
//     "price": 30,
//     "dateSold": "2017-04-22",
//     "id": "t_acds3"
//   },
//   {
//     "itemSold": "Hockey stick",
//     "price": 54.95,
//     "dateSold": "2017-03-19",
//     "id": "j_999"
//   }
// ]

sales.filter((sale) => new Date(sale.dateSold).getFullYear() === 2017);
```

### 3. Return an array of all of the itemsSold properties as strings, sorted alphabetically.

```js
//  Returns
// [
//   "Cricket bat",
//   "Football",
//   "Hockey stick",
//   "Rugby ball",
//   "Trainers"
// ]
sales.map((sale) => sale.itemSold).sort();
```

### 4. Using id as an argument, return the sale which matches the id.

```js
/**
 * Find sale item by id
 * @param {Array<Object>} sales  The sales items to search in
 * @param {String} searchId  The id to search for
 */

const findSaleItemByID = (sales, searchId) => {
  return sales.find((sale) => sale.id === searchId);
};

// Example:
// Returns
// {
//   "itemSold": "Hockey stick",
//   "price": 54.95,
//   "dateSold": "2017-03-19",
//   "id": "j_999"
// }
// findSaleItemByID(sales, 'j_999')

// Using "id" as an argument works, but could potentially be confused with the object's id property
```

## Replicate layout

Please use this as a chance to show your HTML/CSS prowess and design chops. You're free to choose your own colours, typography, icons, and other design elements to demonstrate your design sensibilities. ​We want to know that you can code up a well structured user-friendly UI for scale, with minimal help from UI library/frameworks.
The layout and code must:

- Loosely follow the given layout. This includes:
  - A header, containing:
    - A search box
    - An icon button
    - The search box and icon doesn't need to work or output any result
  - A main content area
  - A sidebar
- Use SCSS, and compiles into CSS
- Use semantic HTML
- Work well in most modern browsers
- Be responsive in most common viewports (feel free to choose your own narrow viewport
  layout)
- Be well documented/commented

If you're itching to do more, consider:

- CSS methodology
- Interactivity
- Accessibility
- UI Components
  Utilise the ​README.md​ file to explain your technical and design decisions.
