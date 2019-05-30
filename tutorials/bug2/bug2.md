---
title: BUG2 24.05
description: Links, tips, tricks and more for getting started with the SAP HANA, express edition
primary_tag: products>sap-hana\,-express-edition
tags: [  tutorial>how-to, tutorial>beginner, tutorial>intermediate, products>sap-hana, products>sap-hana\,-express-edition  ]
time: 77

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
 1. h
 
[ACCORDION-END]

[ACCORDION-BEGIN [Step : ](First)]

```c#
using System;
 
class HelloWorld
{
  public static int Main()
  {
    Console.WriteLine("Hello World!");
    return 0;
  }
}
* This source code was highlighted with Source Code Highlighter.
```
 
[ACCORDION-END]

