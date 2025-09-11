# Premium Roulette

A visually stunning, animated roulette wheel built with HTML, CSS, and JavaScript. Designed to let users spin and win prizes with a realistic spinning effect.

---

## How to Add New Prizes (Segments)

Each segment of the roulette wheel corresponds to a prize object in the JavaScript array called `prizes`.

### Step 1: Locate the `prizes` Array

Open the HTML file and scroll to the `<script>` tag at the bottom. You'll find this array:

```js
const prizes = [
    { number: 1, color: 'red', prize: 'Bocina Bluetooth', weight: 3 },
    { number: 2, color: 'black', prize: 'Descuento 10%', weight: 12 },
    { number: 3, color: 'red', prize: 'Vacaciones', weight: 2 },
    { number: 4, color: 'black', prize: 'Decuento 5%', weight: 25 },
    { number: 5, color: 'red', prize: 'Cuponera', weight: 10 },
    { number: 6, color: 'black', prize: 'Bolsa de Regalo', weight: 6 },
    { number: 7, color: 'red', prize: 'Termo', weight: 6 },
    { number: 8, color: 'black', prize: 'Camioneta SUV', weight: 1 }
];
```

---

### Step 2: Add a New Prize

To add a new segment, insert a new object in the array like so:

```js
{ number: 9, color: 'red', prize: 'Playera Edición Especial', weight: 8 },
```

Make sure:
- `number` is **unique** and **sequential** (1, 2, 3, ...).
- `color` is either `'red'` or `'black'`.
- `prize` is the **label** displayed on the wheel.
- `weight` is a **number** that controls the chance of being selected (higher = more likely).

#### Example: Adding Two More Prizes

```js
{ number: 9, color: 'red', prize: 'Playera Edición Especial', weight: 8 },
{ number: 10, color: 'black', prize: 'Taza Premium', weight: 10 }
```

---

### Step 3: Recalculate Angles (Auto Handled)

The wheel automatically recalculates:
- The angle of each segment
- The layout of the labels

There is **no need to manually update** any drawing or math logic when you add/remove prizes.

---

## Segment Color & Layout

- Use alternating colors like `'red'` and `'black'` for a visual casino-style look.
- The angle per segment is calculated as:

```js
360 / totalNumberOfPrizes
```

- All drawing is done inside an SVG created in the `<div id="wheel-svg-container"></div>` element.

---

## Important Notes

- The wheel redraws itself dynamically every time the page is loaded.
- You can customize text font, color, size, and segment styles via CSS or JavaScript.
- You can adjust spin speed and rotation animation via the `.wheel` element in CSS and JS.

---

## Want More Features?

If you want to improve or expand this roulette, consider adding:
- Weighted prize selection logic based on the `weight` field.
- Spin sound effects or background music.
- A celebration animation like confetti when a prize is won.
- Limiting the number of spins per user.
- Saving spin results to a server or local storage.
- Making the design responsive for mobile devices.

