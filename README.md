# Calculator Web App

This is a simple web-based calculator built using **HTML, CSS, and JavaScript**. It supports basic arithmetic operations such as addition, subtraction, multiplication, and division, as well as other functionalities like clearing the input, deleting the last digit, and using the percentage operator.

## Features
- Basic arithmetic operations (+, -, ×, ÷, %)
- Backspace functionality
- Clear input button
- Responsive design
- Keyboard support

---

## Project Structure
```
Calculator/
├── index.html   # Main HTML structure
├── style.css    # CSS styling
├── script.js    # JavaScript logic
```

---

## Code
### **HTML (index.html)**
```html
<!DOCTYPE html>
<html lang="en">
<head>
   <title>Calculator</title>
   <link rel="stylesheet" href="style.css">
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
   <script src='script.js'></script>
</body>
</html>
```

### **CSS (style.css)**
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
#backspace, #clear {
    background-color: rgb(237, 89, 30);
    color: white;
}
#res {
    padding: 10px;
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

### **JavaScript (script.js)**
```js
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

---

## Explanation
1. **HTML**: Defines the structure of the calculator, including buttons and the display area.
2. **CSS**: Styles the calculator, making it visually appealing and responsive.
3. **JavaScript**:
   - `Solve(val)`: Appends a value to the display.
   - `Result()`: Evaluates the expression entered in the calculator.
   - `Clear()`: Clears the display.
   - `Back()`: Removes the last entered character.
   - `document.addEventListener('keydown')`: Allows keyboard input for the calculator.

---

## How to Run
1. Clone the repository:
   ```sh
   git clone https://github.com/your-username/calculator.git
   ```
2. Open `index.html` in a browser.

---

## License
This project is open-source and free to use.

---

### **Enjoy using the calculator! 🚀**

