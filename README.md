# internship-codesoft-calculator
markdown
 Calculator Application

This is a simple calculator application built with HTML, CSS, and JavaScript. It provides basic arithmetic operations including addition, subtraction, multiplication, division, and percentage calculations.

 Table of Contents

- [Project Overview]
- [Technologies Used]
- [File Structure]
- [How to Use]
- [Features]
- [License]

 Project Overview

This calculator application has a user-friendly interface designed with a responsive layout to work on various screen sizes. Users can perform basic arithmetic operations and view the result directly on the interface. The application also supports keyboard input for convenience.

 Technologies Used

- HTML: Structure of the web page.
- CSS: Styling of the calculator and its elements.
- JavaScript: Functionality of the calculator, including event handling and calculations.

 File Structure

The project has the following files:

- `index.html`: Contains the structure of the calculator.
- `style.css`: Contains the styles for the calculator.
- `script.js`: Contains the JavaScript code for the functionality.

 `index.html`

This file sets up the basic structure of the calculator.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Calculator</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <div id="calc">
        <div id="content">
           <form>
              <div id="output">
                 <input type="text" id='res'>
              </div>
              <div class="btn">
                 <input type="button" value='C' onclick="Clear()" id="clear">
                 <input type="button" value='←' onclick="Back()" id="backspace">
                 <input type="button" value='%' onclick="Solve('%')">
                 <input type="button" value='/' onclick="Solve('/')">
                 <br>
                 <input type="button" value='7' onclick="Solve('7')">
                 <input type="button" value='8' onclick="Solve('8')">
                 <input type="button" value='9' onclick="Solve('9')">
                 <input type="button" value='x' onclick="Solve('*')">
                 <br>
                 <input type="button" value='4' onclick="Solve('4')">
                 <input type="button" value='5' onclick="Solve('5')">
                 <input type="button" value='6' onclick="Solve('6')">
                 <input type="button" value='-' onclick="Solve('-')">
                 <br>
                 <input type="button" value='1' onclick="Solve('1')">
                 <input type="button" value='2' onclick="Solve('2')">
                 <input type="button" value='3' onclick="Solve('3')">
                 <input type="button" value='+' onclick="Solve('+')">
                 <br>
                 <input type="button" value='00' onclick="Solve('00')">
                 <input type="button" value='0' onclick="Solve('0')">
                 <input type="button" value='.' onclick="Solve('.')">
                 <input type="button" value='=' onclick="Result()">
              </div>
           </form>
        </div>
     </div>
        
    <script type="text/javascript" src="script.js"></script>
  </body>
</html>
```

 `style.css`

This file provides styling for the calculator, making it visually appealing and responsive.

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
#calc {
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
}
#content {
    background: #2c302c;
    padding: 20px;
    border-radius: 10px;
}
#content form input {
    border: 0;
    outline: 0;
    width: 50px;
    height: 50px;
    border-radius: 8px;
    font-size: 15px;
    margin: 10px;
    cursor: pointer;
}
#backspace {
    background-color: rgb(237, 89, 30);
    color: white;
}
#res {
    padding: 10px;
}
#clear {
    background-color: rgb(237, 89, 30);
    color: white;
}
form #output {
    display: flex;
    justify-content: flex-end;
    margin: 15px 0;
}
form #output input {
    text-align: right;
    flex: 1;
    font-size: 25px;
}
```

`script.js`

This file contains the JavaScript code that handles the calculator's functionality.

```javascript
function Solve(val) {
    var v = document.getElementById('res');
    v.value += val;
}

function Result() {
    var num1 = document.getElementById('res').value;
    try {
        var num2 = eval(num1.replace('x', '*'));
        document.getElementById('res').value = num2;
    } catch {
        document.getElementById('res').value = 'Error';
    }
}

function Clear() {
    var inp = document.getElementById('res');
    inp.value = '';
}

function Back() {
    var ev = document.getElementById('res');
    ev.value = ev.value.slice(0, -1);
}

document.addEventListener('keydown', function (event) {
    const key = event.key;
    const validKeys = '0123456789+-*/.%';
    if (validKeys.includes(key)) {
        Solve(key === '*' ? 'x' : key);
    } else if (key === 'Enter') {
        Result();
    } else if (key === 'Backspace') {
        Back();
    } else if (key.toLowerCase() === 'c') {
        Clear();
    }
});
```

 How to Use

1. Open `index.html` in a web browser.
2. Use the calculator interface to perform arithmetic operations.
3. You can also use the keyboard for input:
   - Number keys (0-9)
   - Operators (+, -, *, /, %)
   - Decimal point (.)
   - Enter key for equals (=)
   - Backspace key to delete the last character
   - 'C' key to clear the input

 Features

- Basic Operations: Supports addition, subtraction, multiplication, division, and percentage calculations.
- Keyboard Support: Perform calculations using the keyboard.
- Responsive Design: Designed to work on different screen sizes.

 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
