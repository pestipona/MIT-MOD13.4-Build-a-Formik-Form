# Build A Formik Form:

##  Learning Outcome Addressed:

6. Create and validate a form with Formik

## Using Formik:

**Formik** is a **small library** that can help you with the **three most annoying aspects** of **creating forms** in **React**:


* Getting **values in** and **out** of the **form state**
* **Validation** and **error messages**
* Handling **form submission**

By **collecting** all of the above **in one place**, **Formik** can keep things **organized**, making **testing**, **refactoring**, and **reasoning** your forms much easier.

In this activity, you will be using ```npm``` to **install React**, **Formik**, and any other **required libraries**. This is **different** from the way you’ve been using React so far.

Before you **get started** with this activity, you need to:

[Download the Project Starter Files](https://mo-pcco.s3.us-east-1.amazonaws.com/mo-fren/week3/build-a-formik-form_starter.zip). These files include: 


* ```public/index.html``` (this is where your **React app** will be **loaded** inside the **root element**)
* ```src/App.js``` (this is the **main component** of your **React application**. This is where **most of your code** will go)
* **Open** a **command line** on your computer and **run the command** cd ```path/to/project/root```, which allows you to **point to** the **root folder** of the **starter files** (note that ```path/to/project/root``` should be replaced with the **actual path** to the **starter files**)
* Within the same **command-line window**, run ```npm install``` to **install all dependencies**
* Once the **command completes successfully**, run ```npm start``` to **start the application** in your **browser**.

In this activity, your task is to **create** a **login form** with **validation** using **Formik**.

Your form **should include** the **following**:

* Email field
* Password field
* Submit button

Your form **should implement** the following **input validation rules**:

* If the username or password inputs are empty, display the message ```Field required``` under the text input.
* If the username is not in an email format, display the message ```Username should be an email``` under the text input.
* If the username and password pass the above validations, then display the message ```Login Successful``` in an alert box.

Your form **should implement** the following **specific details**:


* The **email input field** should have the ID ```emailField```
* The **email error message** should be within a ```div``` element that has the ID ```emailError```
* The **password input field** should have the ID ```pswField```
* The **password error message** should be within a ```div``` element that has an ID ```pswError```
* The **submit button** should have an ID ```submitBtn```

The **starter code** can be found inside ```src/App.js```

### Instructions:

When you are **finished**, **upload a link** to this project to your **GitHub repository**.

## Solution:

### 1. CD into the directory and run ```npm install```:

**Open** a **command line** on your computer and **run the command** cd ```path/to/project/root```, which allows you to **point to** the **root folder** of the **starter files** (note that ```path/to/project/root``` should be replaced with the **actual path** to the **starter files**)

Within the same **command-line window**, run ```npm install``` to **install all dependencies**

![Screenshot_01.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_01.png)

There were a few errors, so I had to run ```npm audit fix``` but this didn't resolve ell the error messages. 

![Screenshot_02.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_02.png)

### 2. Run the command ```npm start```:

Once the **command completes successfully**, run ```npm start``` to **start the application** in your **browser**.

![Screenshot_03.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_03.png)

This opens up the blank web page with the instructions as shown below.

![Screenshot_04.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_04.png)

### 3. Write the code in ```App.js```

Edit the ```App.js``` file to include the code for all the fields and input validation rules.

```js
import React from "react";
import {useFormik} from "formik";

function App() {

    const formik = useFormik({
        initialValues: {
            email: '',
            password: ''
        },

        onSubmit: values => {
            alert("Login Successful");
        },

        validate: values => {
            let errors = {};
            if (!values.email) errors.email = 'Field required';
            else if (!/^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i.test(values.email)) {
                errors.email = 'Invalid email address';
            }
            if (!values.password) errors.password = 'Field required';
            return errors;
        }
    });

  return (
    <div>
        <form onSubmit={formik.handleSubmit}>

            <div>Email:</div>
            <input id="emailField" name="email" type="text" onChange={formik.handleChange} value={formik.values.email}/>
            {formik.errors.email ? <div id="emailError" style={{color: 'red'}}>{formik.errors.email}</div>: null}

            <div>Password:</div>
            <input id="pswField" name="password" type="text" onChange={formik.handleChange} value={formik.values.password}/>
            {formik.errors.password ? <div id="pswError" style={{color: 'red'}}>{formik.errors.password}</div>: null}

            <div><br/></div>
            <button id="submitBtn" type="submit">Submit</button>
        </form>
    </div>
  );

}

export default App;
```

Save and reload the page, it now shows the email, and password fields as well as the submit button.

![Screenshot_05.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_05.png)

### 4. Input Validation:

Test if the input validation rules are working by pressing the submit button without providing any input values in the fields.

As can be seen the following error messages are shown underneath the email and password fields.

![Screenshot_06.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_06.png)

The second test includes providing a fault email format, and as shown below the email validation works, with the error message shown.

![Screenshot_07.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_07.png)

Finally, the proper email and password input is provided and a "Login Successful" message is shown in an alert box.

![Screenshot_08.png](build-a-formik-form_starter%2FScreenShots%2FScreenshot_08.png)