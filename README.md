# JavaScript Key Events – Movable Emoji Box

A simple JavaScript project that demonstrates **keyboard events** using `keydown` and `keyup`. The user can move an emoji box around the page using the **Arrow Keys**, while the box changes its emoji and background color when a key is pressed and released.

## Features

- Detects keyboard `keydown` and `keyup` events.
- Changes the emoji when a key is pressed.
- Changes the background color while a key is pressed.
- Restores the emoji and background color when the key is released.
- Moves the box using:
  - ⬆️ `ArrowUp`
  - ⬇️ `ArrowDown`
  - ⬅️ `ArrowLeft`
  - ➡️ `ArrowRight`
- Uses JavaScript `switch` statements to handle different arrow keys.
- Uses CSS positioning to move the box dynamically.

## Technologies Used

- HTML5
- CSS3
- JavaScript

## JavaScript Concepts Practiced

- DOM Manipulation
- `document.getElementById()`
- Event Listeners
- `keydown` Event
- `keyup` Event
- Event Object
- `event.key`
- `startsWith()`
- `if` Statement
- `switch` Statement
- `case` and `break`
- Template Literals
- CSS Manipulation using JavaScript
- Variables using `const` and `let`

## Project Structure

```text
Key-Events/
│
├── index.html
├── index.js
└── style.css
```

## How It Works

### 1. Selecting the Box

The JavaScript first selects the HTML element using its ID:

```javascript
const myBox = document.getElementById("myBox");
```

### 2. Setting the Movement Amount

The box moves by `100px` for every arrow-key press:

```javascript
const moveAmount = 100;

let x = 0;
let y = 0;
```

- `x` controls horizontal movement.
- `y` controls vertical movement.

### 3. Keydown Event

When any key is pressed, the box changes its emoji and background color:

```javascript
document.addEventListener("keydown", event => {
    myBox.textContent = "😮";
    myBox.style.backgroundColor = "tomato";
});
```

### 4. Keyup Event

When the key is released, the box returns to its normal appearance:

```javascript
document.addEventListener("keyup", event => {
    myBox.textContent = "😄";
    myBox.style.backgroundColor = "lightblue";
});
```

### 5. Detecting Arrow Keys

The program checks whether the pressed key starts with `"Arrow"`:

```javascript
if(event.key.startsWith("Arrow")) {
```

This prevents unrelated keys from moving the box.

### 6. Moving the Box

A `switch` statement determines which arrow key was pressed:

```javascript
switch(event.key) {
    case "ArrowUp":
        y -= moveAmount;
        break;

    case "ArrowDown":
        y += moveAmount;
        break;

    case "ArrowLeft":
        x -= moveAmount;
        break;

    case "ArrowRight":
        x += moveAmount;
        break;
}
```

The movement works using the following directions:

| Key | Action |
|---|---|
| ⬆️ ArrowUp | Moves the box up |
| ⬇️ ArrowDown | Moves the box down |
| ⬅️ ArrowLeft | Moves the box left |
| ➡️ ArrowRight | Moves the box right |

### 7. Updating CSS Position

The updated `x` and `y` values are applied to the box:

```javascript
myBox.style.top = `${y}px`;
myBox.style.left = `${x}px`;
```

The template literals add the `px` unit to the position values.

## Complete JavaScript Code

```javascript
const myBox = document.getElementById("myBox");
const moveAmount = 100;

let x = 0;
let y = 0;

document.addEventListener("keydown", event => {
    myBox.textContent = "😮";
    myBox.style.backgroundColor = "tomato";
});

document.addEventListener("keyup", event => {
    myBox.textContent = "😄";
    myBox.style.backgroundColor = "lightblue";
});

document.addEventListener('keydown', (event) => {
    if(event.key.startsWith('Arrow')) {

        switch(event.key) {
            case "ArrowUp":
                y -= moveAmount;
                break;

            case "ArrowDown":
                y += moveAmount;
                break;

            case "ArrowLeft":
                x -= moveAmount;
                break;

            case "ArrowRight":
                x += moveAmount;
                break;
        }

        myBox.style.top = `${y}px`;
        myBox.style.left = `${x}px`;
    }
});
```

## HTML Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Key Events</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div id="myBox">😄</div>

    <script src="index.js"></script>
</body>
</html>
```

## CSS

```css
body {
    margin: 0px;
    padding: 0px;
}

#myBox {
    width: 200px;
    height: 200px;
    background-color: lightblue;
    display: flex;
    justify-content: center;
    text-align: center;
    position: relative;
    font-size: 8rem;
}
```

## How to Run

1. Download or clone the project.
2. Open the project folder in VS Code.
3. Make sure these files are present:

```text
index.html
index.js
style.css
```

4. Open `index.html` in a browser.
5. Press the arrow keys to move the box.

## Upload to GitHub

```bash
git init
git add .
git commit -m "Add JavaScript key events project"
git branch -M main
git remote add origin YOUR_GITHUB_REPOSITORY_URL
git push -u origin main
```

Replace `YOUR_GITHUB_REPOSITORY_URL` with your GitHub repository URL.

## Future Improvements

- Prevent the box from moving outside the browser window.
- Add diagonal movement using multiple keys.
- Add WASD controls.
- Add smooth movement using CSS transitions.
- Add a score or movement counter.
- Add sound effects for keyboard actions.
- Add a reset button to return the box to its original position.

## Author

**Kushal Raj U R**

B.E. – Information Science and Engineering
