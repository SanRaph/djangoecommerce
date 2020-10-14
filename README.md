![Pikinhop logo](/static/images/pikinhoplogowhite.jpg "Pikinhop logo")
## eCommerce Store 
### [Semicolon Africa](https://www.semicolon.africa/)
##### <em>Raphael Sani</em>
###### Cohort 4
###### October 5, 2020


![Pikinhop erd](/static/images/pikinhoperddiagram.jpg "Pikinhop erd diagram")

###### *[Check out PikinHop here](https://sanraph.pythonanywhere.com)*

#### Overview
<p>The diagram above represents PikinHop children ecommerce model for cohort 4 Django project.</p> 
<p>We will be working within our apps model.py located in the store app.
Here we created 5 models, not including the build in Django User model.</p>
<p> 1.	User – Built in django is this Django User model. An instance of this model will be created for each customer that registers with our website. 
This model will give us the ability to later use Django default authentication system without having to manually set this up ourselves. </p>
<p> 2.	Customer – Along with the user model each customer will contain a Customer model that holds a one to one relationship to each user (OneToOneField). </p>
<p> 3.	Product – The Product model represents the products we have in store. </p>
<p> 4.	Order – Order represents a transaction that is placed or pending. The model will hold information such as the transaction_ID, date_completed and order_status. </p>
<p> 5.	OrderItem – An order item is one item with an order. For example, a shopping cart may consist of many items but it’s all part of one order.Therefore, the OrderItem will be a child of the PRODUCT and the ORDER model. </p>
<p> 6.	ShippingAddress – Not every order will need shipping information. For orders containing physical products that need to be shipped, we will need to create an instance of the shipping model to know where to send the order. 
Shipping will simply be a child of the order model when necessary. </p>


#### Workflow
My website workflow is as below:
1) user sign up and redirect to login screen once registration successful.
2) user login and now he/she sees a form, where he/she needs to fill in mandatory fields
3) use information is saved and then user go to store click on "Add to cart" button(in the store item display) to add chosen item to cart, or click on "arrow up or down" in cart  to increase or reduce the quantity of items in cart, continue button will redirect to the checkout page automatically for order processing.

#### What's working:
* [x] Registration page
* [x] Login page
* [x] User successfully able to fill in the extra information
* [x] Redirect to the logged in user's profile page.
* [x] Data getting saved in DB.
* [x] User enters store
* [x] Process and check out order

#### What's not working:
The checkout page that is getting generated for shipping information that leads to payment processing is reloading and not getting populated or moving to the next page.
Pending. <br />
I have examined the code without any trace of where it might have gone wrong. <br />

#### Register Use-case (template)
* [x] Use case name: Register
* [x] Description: All users of the system must register for account
* [x] Primary actor: Customer
* [x] Secondary actor: N/A
* [x] Trigger: New user would like to create account
* [x] Precondition: User does not have existing account
* [x] Main-flow
  step1: use case starts when user clicks 'Register'
  step2: system displays the register page and allows to enter details
  step3: user enters registration details
    a. first name
    b. surname
    c. email address
    d. telephone number
    e. password
    f. confirm password

 step4: system valids registration details
 step5:  use case ends when all registration details have been saved
 * [x] Alternate flow: Register with fb account
    1. this flow starts when user selects Register with fb
    2. system allows user enter fb log in details
    3. system validates user details from fb
    4. system retrievs user details from fb
    5. continue from step 5 above

 * [x] Exception: where can something go wrong
    -in step four of main flow, if registration details not successfully validated, display suitable message and allow usser to retry
    -in step 5 of main flow if system is unable to save registration details, display suitable message and log error
 * [x] Post condition: the state it should be in
    Registration details saved and new customer account created


#### Use Case name: Log in
* [x] Description: all users are required to authenticate to access sensitive information
* [x] Primary Actor(s): customer, admin
* [x] Secondary Actor: Actor
* [x] Trigger: user request to access sensitive information
* [x] Precondition: user has a valid registered account
* [x] Main Flow: 
    Use case starts when user clicks login
    System displays login page and allow users to provide login details
    Email address
    Password
    User enters required login details
    System validates and authenticates user details
    System welcomes user and grants access to restricted information
    Use case ends when user has been granted access
* [x] Alternate Flow:
    This flow starts when user selects the ‘login with Facebook’
    System displays Facebook login page
    Continues from step 3 above
* [x] Exception Flow:
    In step 4 above, if system is unable to authenticate user details
    Allow a minimum of 3 attempts
    After 3 attempts, extend change password use case
* [x] Post Condition: user is granted access to access to the system and login details are unchanged

![Pkinhop use case](/static/images/pikinhopusecasediagram.png "Pikinhop erd diagram")

![Pkinhop erd](/static/images/pikinhopactivitydiagram.png "Pikinhop erd diagram")

![Pkinhop erd](/static/images/pikinhopclassdiagram.png "Pikinhop erd diagram")
