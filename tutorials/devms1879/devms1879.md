---
title: devms1879 30.05.19
description: Links, tips, tricks and more for getting started with the SAP HANA, express edition
primary_tag: products>sap-hana\,-express-edition
tags: [  tutorial>how-to, tutorial>beginner, tutorial>intermediate, products>sap-hana, products>sap-hana\,-express-edition  ]
time: 66

---
## Prerequisites  
 - **Systems used:** SAP HANA 1.00 SPS12, SAP HANA 2.00 SPS00, SAP HANA 2.00 SPS01, SAP HANA 2 SPS02 - SAP HANA, express edition


---

[ACCORDION-BEGIN [Step 1: ](All 3 options, all with code snippets)]
1.  From the **Sources** list, choose **Service URL**.  

2.  Then choose the following:

    | -------------:| ---------------------------------- |
    | Drop-down Box | **`Northwind Sample OData`**          |
    | URI           | **`/V2/Northwind/Northwind.svc`**      |

3.  Click the **Test** button to test the service.  If the data is correct, you should see the service entities appear.  

4.   Click **Next** to continue.


[OPTION BEGIN [Windows]]
Click the **Data Sources** tab at the top of the screen.
```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
 ```
 Define a new User Input Filter for restricted **measures (1)**. **Choose** on the **`popup`** the tab **User Input Filters** and **enter the attributes (2)** on the following **`popup`**. **Click** on the **new Button (3)** to create a new input filter **(4) + (5)**. The dimension is derived from the version.
 
[OPTION END]

[OPTION BEGIN [iOS]]
**Select** all following **fields** of the Data View, so that they can be copied to the query:
-  `Amount in CC Crcy`
-  `Controlling Area`
-  `Cost Center`
-  `Fiscal Year`
-  `Fiscal Year Variant`
-  `Cost Object`
-  `Transaction Currency`
-  `Fiscal Period`

```cds
    namespace my.bookshop;
entity Authors {
  key ID : UUID;
  name : String;
  books : Association to many Books;
}
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]

[OPTION BEGIN [Linux]]

Switch to the **Filters** tab. This section displays the fixed value filters and the user input values for the selected dimension. **Change** Filters from **No Filters** to **User Input Values**.
A dialog will be shown in the design studio to read value from user.

```cds
    namespace my.bookshop;
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]
 
![Relative with space](tutorials/bug/cat.png)
----

## Troubleshooting

 - **Missing a file?**  If the list of files doesn't match the picture, you may have used the wrong template when you created the project.  Delete the project, and start the [Create a new project](sapui5-webide-create-project) tutorial again.

 - **$metadata file not listed?**  This means one of the files in your project is incorrect.  Check the files, and make sure no red X marks appear in the left hand column.  These indicate a problem with the file syntax.  Check the pictures carefully.

 - **The `Northwind` system does not appear in the drop down box.**  This can happen when the Web IDE is "out of sync" with the server.  Reload the Web IDE (by clicking the reload button in your browser).  You will come back to the same place, and you can start the steps to create a new OData service again.

 - **Don't forget to save your files!**  If a file name has a * next to it, the file isn't saved.  

 ---

[ACCORDION-END]

[ACCORDION-BEGIN [Step 2: ](All 3 options, all with code snippets and Done button)]
1.  From the **Sources** list, choose **Service URL**.  

2.  Then choose the following:

    | -------------:| ---------------------------------- |
    | Drop-down Box | **`Northwind Sample OData`**          |
    | URI           | **`/V2/Northwind/Northwind.svc`**      |

3.  Click the **Test** button to test the service.  If the data is correct, you should see the service entities appear.  

4.   Click **Next** to continue.


[OPTION BEGIN [Windows]]
Click the **Data Sources** tab at the top of the screen.
```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
 ```
 Define a new User Input Filter for restricted **measures (1)**. **Choose** on the **`popup`** the tab **User Input Filters** and **enter the attributes (2)** on the following **`popup`**. **Click** on the **new Button (3)** to create a new input filter **(4) + (5)**. The dimension is derived from the version.
 
[OPTION END]

[OPTION BEGIN [iOS]]

**Select** all following **fields** of the Data View, so that they can be copied to the query:
-  `Amount in CC Crcy`
-  `Controlling Area`
-  `Cost Center`
-  `Fiscal Year`
-  `Fiscal Year Variant`
-  `Cost Object`
-  `Transaction Currency`
-  `Fiscal Period`

```cds
    namespace my.bookshop;
entity Authors {
  key ID : UUID;
  name : String;
  books : Association to many Books;
}
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]

[OPTION BEGIN [Linux]]

Switch to the **Filters** tab. This section displays the fixed value filters and the user input values for the selected dimension. **Change** Filters from **No Filters** to **User Input Values**.
A dialog will be shown in the design studio to read value from user.

```cds
    namespace my.bookshop;
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]
 
![Relative with space](tutorials/bug/cat.png)
----

## Troubleshooting

 - **Missing a file?**  If the list of files doesn't match the picture, you may have used the wrong template when you created the project.  Delete the project, and start the [Create a new project](sapui5-webide-create-project) tutorial again.

 - **$metadata file not listed?**  This means one of the files in your project is incorrect.  Check the files, and make sure no red X marks appear in the left hand column.  These indicate a problem with the file syntax.  Check the pictures carefully.

 ---
 
[DONE]
[ACCORDION-END]

[ACCORDION-BEGIN [Step 3: ](All 3 options, 2 of them with code snippets)]
1.  From the **Sources** list, choose **Service URL**.  

2.  Then choose the following:

    | -------------:| ---------------------------------- |
    | Drop-down Box | **`Northwind Sample OData`**          |
    | URI           | **`/V2/Northwind/Northwind.svc`**      |

3.  Click the **Test** button to test the service.  If the data is correct, you should see the service entities appear.  

4.   Click **Next** to continue.


[OPTION BEGIN [Windows]]
Click the **Data Sources** tab at the top of the screen.
```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
 ```
 
 Define a new User Input Filter for restricted **measures (1)**. **Choose** on the **`popup`** the tab **User Input Filters** and **enter the attributes (2)** on the following **`popup`**. **Click** on the **new Button (3)** to create a new input filter **(4) + (5)**. The dimension is derived from the version.
  
[OPTION END]

[OPTION BEGIN [iOS]]

1. Click the **Data Sources** tab at the top of the screen.

2. Click the **+** icon next to the *Define OData services for the application and...* box.

[OPTION END]

[OPTION BEGIN [Linux]]

Switch to the **Filters** tab. This section displays the fixed value filters and the user input values for the selected dimension. **Change** Filters from **No Filters** to **User Input Values**.
A dialog will be shown in the design studio to read value from user.

```cds
    namespace my.bookshop;
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]
 
![Relative with space](tutorials/bug/cat.png)
----

## Troubleshooting

 - **Missing a file?**  If the list of files doesn't match the picture, you may have used the wrong template when you created the project.  Delete the project, and start the [Create a new project](sapui5-webide-create-project) tutorial again.

 - **$metadata file not listed?**  This means one of the files in your project is incorrect.  Check the files, and make sure no red X marks appear in the left hand column.  These indicate a problem with the file syntax.  Check the pictures carefully.

 ---
 
[DONE]
[ACCORDION-END]

ACCORDION-BEGIN [Step 4: ](All 3 options, common code snippets, no code snippets in tabs)]
1.  From the **Sources** list, choose **Service URL**.  

2.  Then choose the following:

    | -------------:| ---------------------------------- |
    | Drop-down Box | **`Northwind Sample OData`**          |
    | URI           | **`/V2/Northwind/Northwind.svc`**      |

3.  Click the **Test** button to test the service.  If the data is correct, you should see the service entities appear.  

4.   Click **Next** to continue.

```cds
    namespace my.bookshop;
entity Authors {
  key ID : UUID;
  name : String;
  books : Association to many Books;
}
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```

[OPTION BEGIN [Windows]]
Click the **Data Sources** tab at the top of the screen.
```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
 ```
 Define a new User Input Filter for restricted **measures (1)**. **Choose** on the **`popup`** the tab **User Input Filters** and **enter the attributes (2)** on the following **`popup`**. **Click** on the **new Button (3)** to create a new input filter **(4) + (5)**. The dimension is derived from the version.
 
[OPTION END]

[OPTION BEGIN [iOS]]

**Select** all following **fields** of the Data View, so that they can be copied to the query:
-  `Amount in CC Crcy`
-  `Controlling Area`
-  `Cost Center`
-  `Fiscal Year`
-  `Fiscal Year Variant`
-  `Cost Object`
-  `Transaction Currency`
-  `Fiscal Period`

[OPTION END]

[OPTION BEGIN [Linux]]

Switch to the **Filters** tab. This section displays the fixed value filters and the user input values for the selected dimension. **Change** Filters from **No Filters** to **User Input Values**.
A dialog will be shown in the design studio to read value from user.


[OPTION END]

```cds
    namespace my.bookshop;
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
 
![Relative with space](tutorials/bug/cat.png)
----

## Troubleshooting

 - **Missing a file?**  If the list of files doesn't match the picture, you may have used the wrong template when you created the project.  Delete the project, and start the [Create a new project](sapui5-webide-create-project) tutorial again.

 - **$metadata file not listed?**  This means one of the files in your project is incorrect.  Check the files, and make sure no red X marks appear in the left hand column.  These indicate a problem with the file syntax.  Check the pictures carefully.

 ---
 
[DONE]
[ACCORDION-END]


[ACCORDION-BEGIN [Step 5: ](2 options out of 3, 1 is missing code snippets, with Done button)]
1.  From the **Sources** list, choose **Service URL**.  

2.  Then choose the following:

    | -------------:| ---------------------------------- |
    | Drop-down Box | **`Northwind Sample OData`**          |
    | URI           | **`/V2/Northwind/Northwind.svc`**      |

3.  Click the **Test** button to test the service.  If the data is correct, you should see the service entities appear.  

4.   Click **Next** to continue.



[OPTION BEGIN [iOS]]

**Select** all following **fields** of the Data View, so that they can be copied to the query:
-  `Amount in CC Crcy`
-  `Controlling Area`
-  `Cost Center`
-  `Fiscal Year`
-  `Fiscal Year Variant`
-  `Cost Object`
-  `Transaction Currency`
-  `Fiscal Period`

```cds
    namespace my.bookshop;
entity Authors {
  key ID : UUID;
  name : String;
  books : Association to many Books;
}
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]

[OPTION BEGIN [Linux]]

Switch to the **Filters** tab. This section displays the fixed value filters and the user input values for the selected dimension. **Change** Filters from **No Filters** to **User Input Values**.
A dialog will be shown in the design studio to read value from user.

```cds
    namespace my.bookshop;
type Genre : enum {
  Mystery;
  Fiction;
  Drama;
}
service CatalogService {
  entity Books as projection on bookshop.Books;
  entity Authors as projection on bookshop.Authors;
}
 ```
[OPTION END]
 
![Relative with space](tutorials/bug/cat.png)
----

## Troubleshooting

 - **Missing a file?**  If the list of files doesn't match the picture, you may have used the wrong template when you created the project.  Delete the project, and start the [Create a new project](sapui5-webide-create-project) tutorial again.

 - **$metadata file not listed?**  This means one of the files in your project is incorrect.  Check the files, and make sure no red X marks appear in the left hand column.  These indicate a problem with the file syntax.  Check the pictures carefully.

 ---
 
[DONE]
[ACCORDION-END]
