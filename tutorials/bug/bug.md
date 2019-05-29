---
title: BUG 24.05
description: Links, tips, tricks and more for getting started with the SAP HANA, express edition
primary_tag: products>sap-hana\,-express-edition
tags: [  tutorial>how-to, tutorial>beginner, tutorial>intermediate, products>sap-hana, products>sap-hana\,-express-edition  ]
time: 66

---
## Prerequisites  
 - **Systems used:** SAP HANA 1.00 SPS12, SAP HANA 2.00 SPS00, SAP HANA 2.00 SPS01, SAP HANA 2 SPS02 - SAP HANA, express edition


---

[ACCORDION-BEGIN [Step 1: ](First steps after registering to attend the event)]

```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
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
 
![Relative with space](tutorials/bug/cat.png)

[ACCORDION-END]


[ACCORDION-BEGIN [Step 2: ](TEST)] 

Text before all tabs

[OPTION BEGIN [1]]
ONE
[OPTION END]
  
[OPTION BEGIN [2]]
![Relative with space](tutorials/bug/cat.png)
[OPTION END]

Text after all tabs
 
[ACCORDION-END]  


[ACCORDION-BEGIN [Step 4: ](Run the Outliers service)]

Content to be displayed before tab content disregard what tab is selected.

[OPTION BEGIN [Windows]]
Content to be displayed on ‘Windows’ tab.
[OPTION END]

[OPTION BEGIN [iOS]]
![Repositories](cat.png)
[OPTION END]

[OPTION BEGIN [Linux]]

```cds
    namespace my.bookshop;
entity Books {
  key ID : UUID;
  title : String;
  genre : Genre;
  author : Association to Authors;
}
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

Content to be displayed after tab content disregard what tab is selected.

[ACCORDION-END]
