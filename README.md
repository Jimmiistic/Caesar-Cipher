# CAESAR'S CIPHER

#### Video Demo: <https://youtu.be/2JhxTcZY-C4>

#### Description:

**Explain what your project is about?**

> Problem:

In this Era we really think and care about our privacy and security; But when it comes to have passwords, mostly people just don't care about the password strength and set a password that could probably easy to guess if someone knows their information.

> Solution:

To make a password difficult to guess (for others) and easy to remember (for user), I created a web program that encrypts passwords.

---

---

**What each of the files you wrote for the project contains and does?**

There are three types of files included in my project

- **script.js** _( Caesar Function )_
- **caesar.html** _( Main File )_
- **2 fontfaces** _( for styling purpose )_
  - _Code Bold.otf_
  - _Code Light.otf_

## - **script.js**

This file includes a `Caesar()` function. The reason I made a separate file is because I only want a function inside this file.

Lets take a look at `script.js`

> First, we define a Function named `caesar()` that takes two arguments `str` which is string and a `key` which is a shifting number.

> Let's skip this condition because first we have to know how this caesar function working...

```javascript
if (key < 0) return ceasar(str, key + 26);
```

> First we declare a variable to store the result: `var result = ''; `

> Then we iterate over the string using `for` loop to the `str.length`

> inside this `for` loop we get the character that we are going to add in a new variable
> `var char = str[i];`

> then we give a `if` condition To ensure that we are only changing **alphabets** by using `char.match` function.

> If the condition is true:

```javascript
// Get the letter's code
var code = str.charCodeAt(i);
// For Capital letters
if (code >= 65 && code <= 90)
  char = String.fromCharCode(((code - 65 + key) % 26) + 65);
// For Lowercase letters
else if (code >= 97 && code <= 122)
  char = String.fromCharCode(((code - 97 + key) % 26) + 97);
```

> this will store the values in `char` variable. **REMEMBER** we have changed character by character. so, in order get the value of all of the text: `result += char;` will fulfill the need.

> and Lastly we have to `return result` outside the `if` condition.

---

## - **caesar.html**

This html contains 3 labels:

- For input, where the user types the desired text:
  ![OriginalText](images/textfull.png)

- To type a number to shift letters:
  ![shiftnumber](images/shiftpositive.png)

- To see the encrypted text:
  ![encryptedtext](images/enctext.png)

- and an **ENCRYPT** button.

  ![Encryptbutton](images/pressencrypt.png)

> When you click the **Encrypt** button after giving two inputs ( **original message** and **shift** ), there is a function inside the **html file** called `function1()` that takes the values of these two inputs using `.getElementById().value` and store them into variables respectively.

> **Then there is a function called `caesar()`** that takes 2 inputs: Original text and shifting number. By giving the values, it will look like this:

```javascript
caesar(org_text, Number(shft_num));
```

> NOTE: The function `caesar()` is in a file called **script.js**.

> The resultant value (which is encrypted text) is stored in a variable called `encrypted`

> **Here's how the output is generated:**
> We called `document.getElementById("encrypted").value` to get its value, which is currently empty. To fill the value that we obtained from `Caesar()` function. It will be ` document.getElementById("encrypted").value = encrypted;`

> By doing this, the `encrypted` text will be shown at our webpage.

**How This Program Works?**

#### **CAESAR CIPHER**

> When you open a page, you'll see the following screen:

![fullimage](images/fullimage.png)

There are three things:

- _Original Message_
- _Shift_
- _Encrypted Message_

> In **Original Message**, you'll type the desired text that you want to encrypt. For example...

![OriginalText](images/textfull.png)

> Then In **Shift**, you'll type a number or click on arrowhead button that changes the number. In my case let say 3...

![shiftnumber](images/shiftpositive.png)

> Press **Encrypt** Button and you'll see the Encrypted Text below.

![encryptedtext](images/resultpositive.png)

> To decrypt a message, simply reverse the process. Here in my case:

![decryptedtext](images/resultnegative.png)

---

---

### _I am greatful to have CS50X, wishing you and CS50 team best of luck for the future._ ❤

_Jamshed Iqbal._
