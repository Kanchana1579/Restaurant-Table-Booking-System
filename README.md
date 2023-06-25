RMS V0.1.1

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/ad338f40-47ed-4bf0-83b1-58d649dcc157)

. General introduction Restaurants nowadays require modern solutions to handle daily tasks, especially when it comes to order handling as book 
  keeping is outdated for modern times, in which human fault might cost the facility lots of money. Restaurant Management System (will be 
  referred as RMS from now on) offers following to tackle the problem:

i. Store the configuration of the given restaurant and its menu to easily handle reservations and orders

ii. Create and store orders for the requested tables

iii. Generate and save bills when requested

. RMS Capabilities

• Storing the restaurant configuration: configure facility name, table/seat counts and menu with the ability to modify them in the future. Users will have the ability to modify the data through “Configure Facility/Menu” section of the app

. Create bills for chef (backend): Application will first send the order to kitchen for cooks to see, prepare and fulfil the order.

❖ First stage of this process is confirmation of the order by the customer,

❖ second stage is informing the kitchen staff so they start the cooking process,

❖ third stage is finishing the meals and getting fulfillment of the chef so customers can receive their orders

❖ fourth stage is keeping the order active as long as customer requests for a final receipt

. Create bills for customers (frontend): upon request program will generate a custom made, i.e., restaurant name embedded receipt for customers. 
  GUI will have a template for order creation with dropdown menus to get menu data from the database by the cashier. Upon fulfillment, orders 
  will be stored in the database for further data analysis.
  
3. Technical side

Application will have Graphical User Interface using Python’s built-in module Tkinter. SQLite3 will be the database of choice; hence no active internet connection is required. Initial start will start with main window.Application doesn’t require third-party packages in order to run.

Use of the application

1. Initial run

. When started Main Window will pop up. Through its filebar we can access all the necessary windows.

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/5ad20699-00b5-496c-981f-325b704ea74d)

. Filebar let's us see the current state of the application. At first as there is no database file we can only open up the "Configure 
  Facility/Menu" window to store configurations.

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/4926299a-54b4-42e2-8d11-b7fc4db6a10a)

2. Configuration Window

. In this window we can see the main configuration form to be filled. All of the Entry widgets have validation so, there is quite amount of error 
  handling.

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/0290ffa8-1882-49d9-8d7a-cb04ca2158aa)

. Below is the correct way of configuring the application. First, facility name, table (max. 50) and seat (max. 400) numbers should be filled and 
  saved. Next up, filling name and price of the product and clicking "Add Product" button to store it. By this time there will be a database file 
  created and data will be stored on-the-go. And if you want to change the menu item, you can either click "Remove" or press the "Delete" button 
  AFTER selecting the menu item.

  ![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/bab4ede9-1c8c-471e-b185-0094174893e1)

. This window includes various validations as listed below:

  i. Table Number validation is handled as you type, when it exceeds maximum allowed amount the window below will show error (you can't enter 
     anything other than digits)

  ![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/5937ec2a-68f6-466c-a26b-6a75fc23e5ab)

 ii. Seat Number exceeds maximum allowed (working principle is the same as table validation)
 
![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/5fbc4ca4-0268-4348-b939-c3030a6d3585)

 iii. Add button checks for the empty fields:

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/64bf76bf-4ff9-45b5-b492-114afb0d57e0)

 iv. Add button validates product name length (max. allowed length 20) and price (max. allowed 10 mln Hungarian Forints and real numbers of type float)

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/55b82edc-ebc3-4266-9cfc-457eabd3d006)

3. Create Orders Window
   
. As soon as the configuration menu closed and if there is configurations stored, a new window will be accessible through the main window

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/29f06d40-b160-471f-adfb-98500a096652)

. In this new window we will be able to create orders and send them to the kitchen

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/2048564f-87ec-4bbe-88b1-b8a180869299)

. The correct way of filling out the forms is as follows:

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/c826674d-e0e4-458b-86de-76e24af971d4)

. There is no limit on the number of products you can add to this list, and after getting orders and quantities, "Send to kitchen" button is activated, then the user is prompted to keep getting orders or return to the main window:

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/e90cf306-5445-4dbc-927a-d1568bf587c2)

.This window includes various validations as listed below:

1. Table number is not entered correctly or left empty:

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/ede3e535-c1bf-4d10-8a92-ce76e9e72a65)

2. There is at least one meal that is not selected, if this is the case, the items should all be deleted and started over (if you have better solutions please open up PR)

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/2c8f024c-aa12-493e-a653-2199bbb680c5)

3. Kitchen

. As soon as the previous window closes and there are orders stored in the database, "Kitchen" will be activated in the filebar

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/6a8954d8-e924-4c56-acdb-d2cea93ec19d)

. This window registers orders to a Notebook widget and lists the orders with quantities.

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/e29dab57-60e8-4e32-a1eb-a94169759caa)

. In order to fulfil an order, the item has to be chosen, "Cook" button should be clicked and if and only if all of the items are cooked then "Fulfil order" button will be activated. When clicked on, this button will remove this order from "Orders" table and store it to "Cooked_Orders" table. It also deletes the current Notebook tab, hence if it's the only tab then the window is closed and "Kitchen" is deactivated until new orders are sent.

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/3fc9bb33-69ed-4ad8-a2c7-dd8c170fa14b)

5. Print Orders Window

. This window is activated right after an order is completed in the kitchen. Interface is similiar to "Create Orders" window.

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/f80cc75b-2539-421a-91fe-e6572ffa2736)

. After filling out the table number correctly the orders can be loaded via "Load orders" button. When the orders are listed the "Print receipt" button is activated

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/b18942ec-8ea3-4745-a840-4dd09197bb00)

. The receipt is created based on a template HTML file and stored with the given table number as its file name. Right after storing the file is opened in the default browser where it can be printed

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/ecd7bdcf-1ec1-4f64-9da5-269ce6ebe293)

. This window includes various validations as listed below:

1. Table number is not entered or entered incorrectly:

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/e5ab3f34-0344-416c-816d-b2f6cf6c8aae)

2. There is no any order made for the given table number (Warning message is used instead of Error):

![image](https://github.com/Kanchana1579/Restaurant-Table-Booking-System/assets/128084963/a379f2ab-aa7c-4474-a3d7-9656beb4ceee)

























