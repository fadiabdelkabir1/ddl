******* Create Customer Table *********

CREATE TABLE Customer(
	Customer_id VARCHAR(20) NOT NULL,
	Customer_name VARCHAR(20) NOT NULL,
	Customer_tel INT(11),
        CONSTRAINT PK_Customer PRIMARY KEY (Customer_id)
);


## Create Product Table ##

CREATE TABLE Product(
	Product_id VARCHAR(20) NOT NULL,
	Product_name VARCHAR(20) NOT NULL,
	Price INT(11) UNSIGNED CHECK (Price> 0),
        CONSTRAINT PK_Product PRIMARY KEY (Product_id)
);

## Create Orders Table ##

CREATE TABLE Orders(
	Customer_id VARCHAR(20) NOT NULL,
	Product_id VARCHAR(20) NOT NULL,
	Quantity NUMBER,
        Total_amount NUMBER,
        CONSTRAINT FK_Orders FOREIGN KEY (Customer_id) REFERENCES Customer(Customer_id),
        CONSTRAINT FK1_Orders FOREIGN KEY (Product_id) REFERENCES Product(Product_id)
);



## Add a column Category (VARCHAR2(20)) to the PRODUCT table ##

ALTER TABLE Prodcut ADD Category VARCHAR2(20);

## Add a column OrderDate (DATE)  to the ORDERS table which have SYSDATE as a default value ##

ALTER TABLE Orders 
ADD OrderDate DATE DEFAULT GETDATE();
