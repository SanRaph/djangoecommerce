##PikinHop Django ecommerce store
###Semicolon Africa project cohort4
#### Raphael Sani


![PikinHop ERD Diagram](/static/images/erdpikinhop.png)

####Overview
The diagram above represents **PikinHob** children ecommerce model for cohort 4 Django project. We will be working within our apps model.py located in the store app.
Here we created 5 models, not including the build in Django User model.
1.	User – Build in Django User model. An instance of this model will be created for each customer that registers with our website. This model will give us the ability to later use Django default authentication system without having to manually set this up ourselves.
2.	Customer – Along with the user model each customer will contain a Customer model that holds a one to one relationship to each user (OneToOneField)
3.	Product – The Product model represents the products we have in store.
4.	Order – Order represents a transaction that is placed or pending. The model will hold information such as the transaction_ID, date_completed and order_status.
5.	OrderItem – An order item is one item with an order. For example, a shopping cart may consist of many items but it’s all part of one order.Therefore, the OrderItem will be a child of the PRODUCT and the ORDER model.
6.	ShippingAddress – Not every order will need shipping information. For orders containing physical products that need to be shipped, we will need to create an instance of the shipping model to know where to send the order. Shipping will simply be a child of the order model when necessary.

####Workflow
My website workflow is as below:
1) user sign up and redirect to login screen once registration successful.
2) user login and now he/she sees a form, where he/she needs to fill in mandatory fields
3) use information is saved and then user go to store click on "Add to cart" button(in the store item display) to add chosen item to cart, or click on "arrow up or down" in cart  to increase or reduce the quantity of items in cart, continue button will redirect to the checkout page automatically for order processing.
what's working:
[x]	Registration page
[x]	Login page
[x]	User successfully able to fill in the extra information
[x]	Redirect to the logged in user's profile page.
[x]	Data getting saved in DB.
[x]	User enters store
[x]	Process and check out order
####What's not working:
The checkout page that is getting generated for shipping information that leads to payment processing is reloading and not getting populated or moving to the next page.
Pending.
I have examined the code without any trace of where it might have gone wrong.
Register Use-case (template)
####Use case name: Register
Description: All users of the system must register for account
Primary actor: Customer
Secondary actor: N/A
Trigger: New user would like to create account
precondition: User does not have existing account
Main-flow
  step1: use case starts when user clicks 'Register'
  step2: system displays the register page and allows to enter details
step3: user enters registration details
a. first name
b. surname
c. email address
d. telephone number
e. password
f. confirm password

step4: system validates registration details
step5:  use case ends when all registration details have been saved
Alternate flow: Register with fb account
1. this flow starts when user selects Register with fb
2. system allows user enter fb log in details
3. system validates user details from fb
4. system retrieves user details from fb
5. continue from step 5 above

Exception: where can something go wrong
-in step four of main flow, if registration details not successfully validated, display suitable message and allow usser to retry
-in step 5 of main flow if system is unable to save registration details, display suitable message and log error
post condition: the state it should be in
Registration details saved and new customer account created

![PikinHop activity Diagram](/static/images/pikinhopactivitydiagram.png)

![PikinHop usecase Diagram](/static/images/pikinhopusecasediagram.png)

![PikinHop class Diagram](/static/images/pikinhopclassdiagram.png)

