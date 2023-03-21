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

