# Online-Shopping-Cart-Database-Project

Simple E-Commerce Online Stall built with Java Console and stored in a Database.

## Databases

Do check out the Database scripts and download the [MySQL Connector] (https://osdn.net/projects/sfnet_vimcloud/downloads/mysql-connector-java-5.1.18-bin.jar/).

* Table.sql: Create tables for entities and relationships above.
* Insert.sql: Insert datas into tables.
* Modification.sql: Modify the data.

### Entities

* User (__userId__, name, phoneNum)
* Buyer (__userId__)
* Seller (__userId__)
* Bank Card (__cardNumber__, userId, bank, expiryDate)
* Credit Card (__cardNumber__, organization)
* Debit Card (__cardNumber__)
* Store (__sid__, name, startTime, customerGrade, streetAddr, city, province)
* Product (__pid__, sid, name, brand, type, amount, price, colour, customerReview, modelNumber)
* Order Item (__itemid__, pid, price, creationTime)
* Order (__orderNumber__, creationTime, paymentStatus, totalAmount)
* Address (__addrid__, userid, name, city, postalCode, streetAddr, province, contactPhoneNumber)

### Relationships

* Manage (__userid__, __sid__, SetupTime) (userid ref Seller, sid ref Store)
* Save to Shopping Cart (__userid__, __pid__, quantity, addtime) (userid ref Buyer, pid ref Product)
* Contain (__orderNumber__, __itemid__, quantity) (orderNumber ref Order, itemid ref Order Item)
* Deliver To (__addrid__, __orderNumber__, TimeDelivered) (addrid ref Address, orderNumber ref Order)
* Payment (__C.cardNumber__, __orderNumber__, payTime) (C.cardNumber ref Credit Card, orderNumber ref Order)

## Java GUI

[SQL.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/SQL.java) is the acutal program that we wrote to submit the sql execution to the database based on the sample above.

[Java_GUI](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/tree/master/Java_GUI) contains the Java programs for creating the GUI.

1. [MainFrame.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/MainFrame.java): Provide main menu for user to choose different function.

![image](http://www.aaronguan.com/images/database/MainFrame.png)

2. [Register.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/Register.java): User registration interface.

![image](http://www.aaronguan.com/images/database/Register.png)

3. [Login.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/Login.java): User log-in interface.

![image](http://www.aaronguan.com/images/database/Login.png)

4. [AddAddress.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/AddAddress.java): Add address for delivery.

![image](http://www.aaronguan.com/images/database/Add%20Addr.png)

5. [SearchFrame.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/SearchFrame.java):Search products in database.

![image](http://www.aaronguan.com/images/database/Search%20Prod.png)

6. [SaveToCartFrame.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/SaveToCartFrame.java): Add products into shopping cart.

![image](http://www.aaronguan.com/images/database/Add%20to%20cart.png)

7. [SetUpOrderFrame.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/SetUpOrderFrame.java): View the shopping cart and create the order.

![image](http://www.aaronguan.com/images/database/View%20Shoppingcart.png)

8. [addressFrame.java](https://github.com/aaronzguan/Online-Shopping-Cart-Database-Project/blob/master/Java_GUI/addressFrame.java): Select a delivery address and finish the shopping.

![image](http://www.aaronguan.com/images/database/Select%20Addr.png)
