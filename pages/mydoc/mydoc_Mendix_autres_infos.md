---
title: Diverses infos Mendix
tags: [Mendix]
last_updated: July 30, 2025
keywords: Mendix
summary: "infos diverses et tips Mendix"
sidebar: mydoc_sidebar
permalink: Mendix_autres_infos.html
folder: mydoc
---

### Performance

### Exemples d'usages spécifiques 

How to make a Slack bot with Mendix (Medium)

Publishing REST APIs in Mendix (Medium)

GenAI from Marketplace ([Medium](https://medium.com/mendix/2024-wrapped-on-the-mendix-marketplace-genai-genai-genai-42d18f448b36))

### Autres infos

java actions

[Explore Mendix Java Actions](https://yashvaantlakham73.medium.com/explore-mendix-java-actions-d8293460a297)

[How to work with Variables in Java actions — Mendix How-to](https://medium.com/mendix/how-to-work-with-variables-in-java-actions-mendix-how-to-12db5c79e4fd)

[Medium](https://medium.com/@ryanmocke) de Ryan Mocke

* Mendix documentation [best practices](https://docs.mendix.com/refguide/dev-best-practices/#pages)

* Mendix documentation [best practices offline](https://docs.mendix.com/refguide/mobile/building-efficient-mobile-apps/offlinefirst-data/best-practices/)

* Mendix documentation [raccourcis clavier](https://docs.mendix.com/refguide/keyboard-shortcuts/)

* Forum Mendix : discussion [Productivity tips and tricks](https://community.mendix.com/link/space/app-development/questions/16852)

* Forum Mendix : discussion [tips and tricks you wish you would have known](https://community.mendix.com/link/space/studio-pro/questions/108056) 
  - ctrl + shift + tab : go back to previous open tab

* Forum reddit : discussion [the most useful Mendix tips & tricks](https://www.reddit.com/r/mendix/comments/a168d2/what_were_the_most_useful_mendix_tips_tricks_you/)
  - Never place a breakpoint on a retrieve if all you do with that list after the retrieve is a "count". The modeler will skip over the retrieve as it can do a count straight away, so you'll never break even when the microflow runs.
  - If you're looking for the place to set conditional breakpoints - you can only make a breakpoint conditional after first adding a normal one. Just right-click the action and then click "edit breakpoint condition"
  - When using ctrl+g to go to a microflow, but you're not sure what it's called exactly, search by using a space in between the keywords

* Developer Blog tag [Tips & Tricks](https://www.mendix.com/tag/tips-tricks/)

* Medium article : [10 tips you wish you knew earlier to speed up your Mendix development](https://medium.com/mendix/heres-10-tips-you-wish-you-knew-earlier-to-speed-up-your-mendix-development-f8152f5cb9ac)
1. Use dissolve container to quickly remove a container
2. Use inline snippet to return snippet contents back to a page
3. Quickly set the return value in a microflow : right click an activity that contains a variable and press "Set as return value"
4. Instantly swap input widget types for enumerations and booleans : right click "Convert to radio buttons"
5. Dragging and dropping :
  - from Explorer into Microflows (to create Call Microflow activity or replace an existing one),
  - from Explorer into pages (to add widget/layout ; drag a microflow onto a button to set that microflow as the button action; drag a page into a page view to insert a button linking to that page, drag a microflow onto a dataview to set that microflow as the datasource),
  - drag connector items into data views to insert input widgets ( the connector tab will show you the attributes for the entity in that dataview. You can use the connector to drag any of those attributes into the dataview to instantly create an input widget for that attribute)
6. Keyboard shortcuts : Ctrl+Enter, Ctrl+G, Ctrl+Space, F5, F9 (view app), Ctrl+W, Shift+mouse wheel
7. Custom caption on Call microflow activity 
8. Add custom design properties to your project (design properties are defined in design-properties.json in your project directory ; you can add custom design properties to your project to allow all team members to easily discover available custom classes)
9. Align your microflows automatically
10. Use the documentation export to quickly generate app documentation (right click in app explorer "Export documentation"

* kinetech : [9 Pro Tips for Starting with Mendix](https://www.kinetechcloud.com/kinetech/9-tips-for-starting-w-mendix)
1. Understand the Data Model or Question the Relationships
2. Navigate Using the “Right-Click” Go to Form, Microflow, Entity (Data Model) or Find Usage
3. Use SubFlows / Reusability
4. Agree on Naming Conventions
5. Use the Debugger
6. Minimize Retrieves where Possible
  - Beginners will commonly use a retrieve then check if it is empty (for a GetOrCreate Subflow for example).  A faster and more efficient way to do this is **simply to check if the association exists**, then act accordingly.  
7. X-Path Constraints
  - When writing XPath constraints, you can only compare variables to the contents of an association or with the value of an attribute.  Furthermore, XPath constraints always consist of an odd number of elements.
  - So \[Parent_Child/Child = $Variable\] is not possible but you can use: \[Parent_Child = $Variable\] or \[Parent_Child/Child/id = $Variable\] or \[Parent_Child/Child/Name = $Variable/Name\].
8. Account for Null Values
  - Anytime you are performing a calculation (with numbers, dates, etc.) always be sure to check for empty values before performing the calculation.  This is particularly important when using On Change microflows.
9. Annotate your work and test, test, test.

* Medium article : [Common UX mistakes everyone still makes 2.0](https://uxplanet.org/common-ux-mistakes-everyone-still-makes-2-0-c320bb07b21d) 

- rule of thumb about whitespace 
The more often a page is used, the less whitespace it should have. The less often a page is used, the more whitespace it can have.

- tables vs. layout grids
Tables
Tables <table> are not responsive by default. They show clear relationships between rows and columns, which matters when multiple entries exist, making them great for comparing data.
The DOM sees <table> and understands that it holds data in a tabular format.
(table because the relationship between columns and rows matters)

Layout-grid
Layouts-grids (CSS Grid) communicate to the browser that this element is part of the layout. The element does not have a defined place or relationship with the data, because of this, the CSS allows us much greater freedom to position elements in relation to other elements.

When building widgets, use the correct HTML elements instead of relying on JavaScript and inline styling. For example, if your data is tabular, render it as a <table> element. This allows users to copy and paste it directly into Excel or Google Sheets while preserving formatting.

- card vs. panel

CARD
- Modular & portable
- Actionable
- Focus on content
- Visual separation
→ Clickable unit.
Can contain content, but not other cards or panels.

PANEL
- Structural & organizational
- May not be standalone
- Interactive
- Persistent area
 → Structural container.
Can hold nested panels or cards.

1. Build consistently. Follow your design system so every page is predictable and maintainable.
2. Stick to shared interaction patterns. Users learn your app once; don’t make them guess how things behave.
3. Respect whitespace. Compact for daily-use screens, spacious for rare or goal-focused interactions.
4. Use widgets wisely. Fancy does not mean better. Follow the patterns your team has agreed on.
5. Know when to use tables vs layouts. Tables for multiple, structured entries; layouts for single or nested content.
6. Understand cards vs panels and use semantic HTML. Cards for actions, panels for structure, and always pick the right HTML elements to improve accessibility and maintainability.


* Medium article : [A Sneaky Mendix Trick to Dynamically Trigger Microflows](https://medium.com/@vishnuprasath011/a-sneaky-mendix-trick-to-dynamically-trigger-microflows-6fec6667a7cf)
aim : dynamically trigger the microflow of the dataview that is inside the groupbox
Approach 1: Using JavaScript to Toggle the Data View (JS snippet to detect when a Group Box was clicked or expanded)
Approach 2: Using a Nested Data View Inside a List View (List-to-Widget Trick)
Approach 3: Switching to Data Grid 2 for Built-In On-Click Handling (**Data Grid 2 comes with a built-in on-click event**)

* Medium article : [Convert a Mendix Page to PDF](https://medium.com/mendix/how-to-convert-a-mendix-page-to-pdf-using-the-document-generation-module-a63714472cc4) ; voir aussi l'article [PDF Document Generation in Mendix](https://medium.com/mendix/pdf-document-generation-in-mendix-a95e67d41503)
-> Using the 'PDF Document Generation' Module ([doc officielle](https://docs.mendix.com/appstore/modules/document-generation/))

* Articles Medium sur comment convertir des champs de sélection de date de naissance en champ de saisie de texte (pour saisie plus facile); [partie 1](https://medium.com/@bart.zantingh/dating-issues-or-re-building-a-date-of-birth-component-in-mendix-part-1-e8652cbfcfe2) avec notamment la logique de validation ; partie 2 sur comment adapter l'accessibilité de ces champs, notamment avec field set et le module [Accessibility Helper](https://marketplace.mendix.com/link/component/114803) (permet par ex. d'ajouter des attributs HTML)

* Medium article [Guide for Implementing Drag and Drop Widget in Mendix Applications](https://medium.com/@ashirwadmittal/guide-for-implementing-drag-and-drop-widgets-in-mendix-applications-a3dc6403ba84) (widget [Drag and Drop ](https://marketplace.mendix.com/link/component/116604)de MxLabs)

* Article Medium sur Commit Mendix et comparaison avec SQL commit ([Committing to the Mendix commit activity](https://medium.com/@rcpoolen/committing-to-the-mendix-commit-activity-70a2a1d954bb)) 
  
From Mendix documentation  : *a Mendix commit is not the same as a database commit. For an object of a persistable entity, the saved value is not committed to the database until the microflow and any microflows from which it is called, complete. This means that errors in a microflow can initiate a rollback. If a microflow activity errors and has Error handling set to Rollback or Custom with rollback, the value of the object is rolled back to the value it had at the start of the microflow*

In SQL :

```
INSERT INTO customer (name, age, gender, …)
VALUES (“John”, 35, whatever, …);
COMMIT;
```
If you leave out the COMMIT statement it will only save it in the database for your session. No other sessions that are connecting to your database will see your record until you’ve added the COMMIT part. 

a Mendix-Commit can be seen more as an SQL INSERT or UPDATE statement.
Each Mendix-Commit is automatically adding SQL SAVEPOINT lines (if there is already previous committed data for this microflow transaction). 
Savepoints in SQL are used to store a moment in the transaction to which it can rollback to whenever an error occurs/is handled.

*If i commit objects in a microflow and afterwards in that same microflow an unhandled error occurs, are my objects then stored in the database or not?*
No, they will not be stored in the database because the microflow is terminated before it could get to the hardcoded SQL COMMIT statement at the end of the (successful-)microflow transaction. The database that you did are rolledback by the default rollback mendix behaviour. (they are actually removed from your sessions database storage)

*If i commit objects in a microflow and afterwards try to retrieve those objects from the database, will the retrieve action return these objects?*
Yes, since the commit action is actually a call to the database, it is stored in the database already for your session. So when your session tries to retrieve data it will find your inserted object already. Another session will not be able to retrieve the object though since it has not been released for others yet (at least until the end of your microflow).

*Committing inside a loop VS committing outside a loop:*
committing outside a loop is better for performance. Not only because the reduction of individual database calls, but also that it does not have to manage a lot of unnecessary savepoints.

* Article Medium : exemple comment exporter Data grid 2 vers Excel des données différentes pour chaque utilisateur (entité "helper" et Xpath) ([Exploring Personalization and Exporting in Data Grid 2](https://itnext.io/exploring-personalization-and-exporting-in-data-grid-2-8130037976f2))

* Article Medium avec points d'attention sur la validation des inputs (validation flow not always triggered) ([Write-up Mendix CTF 2025: Refill Overkill](https://medium.com/@johan.flikweert/write-up-mendix-ctf-2025-refill-overkill-f20ef2b0a327))
*Why did the validation flow only trigger the first time and not the second? The only difference was that the changes were committed, so apparently the Order flow only executed the validation when the attribute was changed. It seems ok to only validate changed attributes, but as it turns out: it may be unsafe!*
- Always validate input for flows which can be called by the client, just reuse the (partial) validation flows triggered in on change flows.
- Don’t assume validations have taken place earlier in the process, preferably do double validations then the possibility to bypass them!
- If possible, avoid committing the full object after partial validation.

* Article Medium [Mendix — Decoding XAS](https://medium.com/@nkhard98/mendix-decoding-xas-service-655d2c5b7acf) 

**XAS** is the private HTTPS REST API endpoint used by the Mendix client to communicate with Mendix Runtime. It is one of the request handlers offered by Mendix. This is sent as a form of API request [...]. Each type of call to this API is called an **action**, and necessary parts of the state are sent along with it. 

You can inspect XAS requests in the Network tab of your browser’s developer tools and filter out requests to the XAS path.

Whenever a XAS action (such as a microflow call) is triggered, Mendix Client also sends the state. Mendix Client does not send the entire state to the runtime, \[but\] decides which parts of the state should be sent by analyzing each microflow during the deployment of the applications.

* Article Medium sur les entités Object Query Language (OQL) View : [OQL View as a Solution: When XPath and Microflows Aren’t Enough](https://medium.com/@risshis11/oql-view-as-a-solution-when-xpath-and-microflows-arent-enough-91fcf900fc01)

OQL View Entities are stored as database views 
They don’t store data themselves — only the query definition.
Each time you access them, the DB runs the query and returns fresh results.
Performance depends on query efficiency and indexes.

 exemples d'utilisation : 
- calculer le nombre de commandes par client ; on a une entité "Client" et une entité "Commandes" et on veut afficher le nombre total de commandes par client. On peut avoir un microflow qui le calcule ou mettre à jour un attribut, mais le plus efficace c'est de passer par une entité OQL View.
- 
```
SELECT
    c.ID AS OrderCount_Customer,
    COUNT(DISTINCT o.ID) AS OrderCount
FROM OQLTest.Customer AS c
LEFT JOIN c/OQLTest.Order_Customer/"OQLTest.Order"/ AS o
GROUP BY c.ID
```

- classifier clients comme actif/inactif selon s'ils ont passé commande dans les 6 derniers mois
  
```
SELECT
    c.ID AS CustomerStatus_Customer,
    CASE
        WHEN DATEDIFF(MONTH, MAX(o.OrderDate), '[%CurrentDateTime%]') <= 6
            THEN 'Active'
        ELSE 'Inactive'
    END AS Status
FROM OQLTest.Customer AS c
LEFT JOIN c/OQLTest.Order_Customer/"OQLTest.Order" AS o
GROUP BY c.ID
```

- commandes en fonction de l'utilisateur logged-in
  
```
SELECT
    o.ID AS OrderID,
    o.OrderDate AS OrderDate,
    o.TotalAmount AS TotalAmount,
    u.Name AS UserName
FROM "OQLTest.Order" AS o
INNER JOIN o/OQLTest.Order_Account/Administration.Account AS u
WHERE u.ID = '[%CurrentUser%]'
```

- top 5 produits

```
SELECT
    c.ID AS CustomerID,
    c.CustomerName AS CustomerName,
    SUM(o.TotalAmount) AS TotalSales
FROM OQLTest.Customer AS c
INNER JOIN c/OQLTest.Order_Customer/'OQLTest.Order' AS o
GROUP BY
    c.ID,
    c.CustomerName
ORDER BY
    TotalSales DESC
LIMIT 5

```

OQL Views for
- Associations → Link directly to persistable entities.
- Aggregations → SUM, COUNT, AVG, MIN, MAX.
- Filtering → Use tokens like $currentUser.
- Grouping & Ordering → Push heavy logic to DB instead of microflows.
- Widgets → Use directly in grids, charts, and exports.


Avoid them when:
- Simple XPath already solves the problem.
- Your domain model changes frequently (OQL needs manual query updates).
- You need create, update, or delete operations (OQL Views are read-only).

* Article Linkedin [View Entities in Mendix: The Complete Implementation Guide for 10x Performance Gains](https://www.linkedin.com/pulse/view-entities-mendix-complete-implementation-guide-10x-neel-desai-ajklf)



By storing named OQL queries as virtual entities, developers can achieve database-level performance for operations that previously required extensive microflow processing
View Entities fundamentally change this paradigm by executing OQL queries directly at the database level, bypassing the Mendix object layer entirely for read operations
The result is dramatic performance improvement
scenarios where View Entities provide maximum benefit: data grids with multiple associations, reporting dashboards requiring aggregations, API endpoints exposing denormalized data, etc.

Example: Order summary with customer and product information

```
SELECT 
    o.ID,
    o.OrderNumber,
    o.OrderDate,
    c.Name AS CustomerName,
    c.Email AS CustomerEmail,
    SUM(oi.Quantity * oi.UnitPrice) AS TotalAmount,
    COUNT(oi.ID) AS ItemCount
FROM MyModule.Order o
JOIN o.Customer c
JOIN o.OrderItems oi
WHERE o.OrderDate >= '[%BeginOfCurrentMonth%]'
GROUP BY o.ID, o.OrderNumber, o.OrderDate, c.Name, c.Email
ORDER BY o.OrderDate DESC OFFSET 0        
```

Patterns with multi-level aggregations combined with conditional logic and other advanced techniques can demonstrate huge improvements in server memory and faster performance. Examples of conditional aggregations: Usage of CASE statements, subqueries for complex calculations, and HAVING clauses for post-aggregation filtering. The result is a single query that would otherwise require dozens of microflow operations

View Entities support **parameterization** through system variables and **context-aware filtering**, enabling dynamic behavior while maintaining performance benefits.

```
SELECT 
    s.ID,
    s.SalesDate,
    s.Amount,
    s.Region,
    u.FullName AS SalesRepName,
    (s.Amount - s.Cost) AS Profit
FROM MyModule.Sale s
JOIN s.SalesRep u
WHERE s.SalesDate BETWEEN '[%BeginOfCurrentMonth%]' AND '[%EndOfCurrentMonth%]'
    AND u.ID = '[%CurrentUser%]'
ORDER BY s.SalesDate DESC OFFSET 0        
```

Optimizing data grid performance : Data grids displaying information from multiple entities represent the ideal View Entity use case. Traditional approaches create N+1 query problems, where displaying 100 records might execute 300+ database queries.

A single query can replace multiple retrieve actions and provide all data needed for a comprehensive dashboard, complete with aggregated statistics.

While View Entities execute at the database level, **proper indexing** remains crucial for optimal performance. Focus indexing efforts on columns used in WHERE clauses, JOIN conditions, and ORDER BY statements.

View Entities consume less memory than traditional entity retrieval since **they bypass object instantiation**. However, large result sets still require careful memory management. Implementing **pagination is recommended for View Entities returning >1000 records**

Best Practices: OQL query management
1. Comment complex queries to explains business logic
2. Document parameter usage and expected data ranges
3. Maintain change logs for query modifications
4. Create test cases validating query results
5. Refresh data grids after modifying underlying entities
6. Design View Entities with future growth in mind

* [Mendix doc about OQL View Entity](https://docs.mendix.com/refguide/use-view-entities/)

The data that view entities contain is determined when you retrieve the data.
A view entity can be seen as a named OQL query that behaves like a persistable entity.
The entire query is executed by the database, often resulting in faster performance compared to executing multiple independent retrieves.

use case : data preparation (e.g. when using data grids with associations from multiple entities, view entities increase speed and allow for full sorting, pagination, and filtering functions), charting, API stability (To **decouple data usage from data storage**, especially for APIs, view entities allow you to expose data while keeping your domain model flexible. This ensures API stability for external applications and allows you to change your domain model as needed without affecting the API.)

example : list all customers at an organization that are over age 18 :
```
FROM Shop.Customer AS c
 LEFT JOIN c/Shop.BillingAddress/Shop.Address as ba
 LEFT JOIN c/Shop.DeliveryAddress/Shop.Address as da
WHERE datediff(YEAR,c.DateOfBirth,'[%CurrentDateTime%]') > 18
SELECT
 c.CustomerId                                                                                   as CustomerId
,c.LastName + ', ' + FirstName                                                                  as FullName
,datediff(YEAR, c.DateOfBirth,'[%CurrentDateTime%]')                                            as Age
,ba.Streetname + ' ' + ba.StreetNumber + ' ' + ba.Zipcode + ' ' + ba.City + ' ' +  ba.Country   as BillingAddress
,da.Streetname + ' ' + da.StreetNumber + ' ' + da.Zipcode + ' ' + da.City + ' ' +  da.Country   as DeliveryAddress
```

count the number of customers that were born in each decade and group them appropriately.
```
 FROM
   (
    FROM HowToThink.CustomerWithAddressVE as c SELECT CAST(c.Age:10 as integer) * 10 as AgeBucket ,
                                                      c.CustomerId as CustomerId) as b
 GROUP BY b.AgeBucket
 SELECT b.AgeBucket as AgeBucketStart ,
        b.AgeBucket + 9 as AgeBucketEnd ,
        COUNT(b.CustomerId) as CustomerCount
 ORDER BY b.AgeBucket
 LIMIT 10
```

The ORDER BY clause can be used in a view entity in combination with LIMIT or OFFSET clauses to define a specific set of data to retrieve. If you do this, **you still should not rely on the order of the output**. If you want the results in particular order, they can be sorted on retrieval.

For example, the following OQL query defines a view entity Books.Bestseller, which contains data of the ten books which have sold the most copies. When using this view entity in your app, **you should still explicitly specify sorting of the results**.
```
FROM Books.Book
SELECT Name AS Name,
       ISBN AS ISBN,
       Sold AS Sold
ORDER BY Sold DESC
LIMIT 10
```

assume you have an entity with the attributes FirstName and LastName. In a view entity, you combine both the first name and last name into a FullName attribute. When you select from this entity, you can specify an XPath expression that limits the data on the full attribute name
Alternatively, you can store the parameter value in the database, then use that value in your view entity. For example, the image below is of a view entity that returns the data of the Product entity in the language of the current user.

```
FROM Shop.Product as p
LEFT JOIN System.User as u ON (u.ID = '[%CurrentUser%]')
LEFT JOIN u/System.User_Language/System.Language as l
LEFT JOIN p/Shop.ProductTranslations_Product/Shop.ProductTranslations as t ON (t.LanguageCode = l.Code)
SELECT p.ID as ID,
       p.ProductId as ProductId,
       COALESCE(t.Name, p.Name) as Name,
       COALESCE(t.Description, p.Description) as Description,
       p.WeightInGrams as WeightInGrams,
       l.Code as UserLanguageCode
```
This is done by joining an entity that has all the necessary translations and filtering it by the language of the current user. Coalesce is used to return the default language in case there is no translation is available.

If you have a multitenant system where every user has a tenant ID, you can ensure through view entities that any data that is tenant-specific will only return data for the tenant of the current user

Use the WHERE clause of a view entity to ensure only data that should be available to the user is returned. This is an alternative to the access rules you can have on both persistable entities and view entities.

**Persistable entity access rules are not applied when using view entities**. Instead, you must specify the access rules. You can define what users have access to while still allowing access to aggregated data. 

For example, you may want to know how many employees are part of each department of a company. However, you should not be able to see the detailed information of each employee. View entities allow you to give a user access to specific employee data without revealing sensitive information.

a view entity is used to implement multitenant security. The view entity CustomersVE only returns the customers that belong to the tenant of the current user. Any additional view entity that uses CustomersVE instead of the persistable entity Customer will only get data belonging to the tenant of the user.
```
FROM Shop.Customer as c
JOIN ShopViewSamples.CurrentUserVe u ON (u.UserTenantId = c.TenantId)
SELECT c.CustomerId as CustomerId,
       c.FirstName as FirstName,
       c.LastName as LastName,
       c.EmailAddess as EmailAddess,
       c.DateOfBirth as DateOfBirth
```

Instead of joining with the \[%CurrentUser%\] expression, this example joins with a view entity that only returns one object: the current user and related details, such active language and tenant ID. This simplifies use of user information for other view entities.

```
FROM System.User as u
LEFT JOIN u/System.User_Language/System.Language as l
LEFT JOIN u/Shop.UserTenant_User/Shop.UserTenant as t
WHERE (u.ID = '[%CurrentUser%]')
  SELECT u.Name as UserName ,
         l.Code as UserLanguageCode ,
         t.TenantId as UserTenantId

```

Mendix doc [Charting with View Entities](https://docs.mendix.com/refguide/charting-with-view-entities/)


Mendix charts do not take associations, so you usually have to take extra steps to use a non-persistable entity as a source. Using view entities is a faster and simpler way to create a chart.

chart to see how much you make in sales each year, and how each product category contributes to the number


```
SELECT
  CAST(DATEPART(YEAR, o.OrderDate) as INTEGER) as OrderYear
  , c.CategoryId as CategoryId
  , c.CategoryName as CategoryName
  , SUM(ol.Quantity * ol.UnitPrice * (1 - ol.Discount)) as TotalSales
FROM SalesDashboard."Order" as o
  JOIN SalesDashboard.OrderLine_Order/SalesDashboard.OrderLine as ol
  LEFT JOIN SalesDashboard.OrderLine_Product/SalesDashboard.Product as p
LEFT JOIN SalesDashboard.Product_Category/SalesDashboard.Category as c
GROUP BY c.CategoryId, c.CategoryName, CAST(DATEPART(YEAR, o.OrderDate) as INTEGER)
```

* Mendix doc [Create a Pivot Table with View Entities](https://docs.mendix.com/refguide/view-entity-pivot-table/)

You want to analyze seasonal sales volumes, which is how much your business makes from sales in each quarter per year

Create a view entity that shows each order together with its total value, calculated from the OrderLine entity

```
SELECT
  o.OrderId as OrderId
  , CAST(DATEPART(QUARTER, o.OrderDate) as INTEGER) as OrderQuarter
  , CAST(DATEPART(YEAR, o.OrderDate) as INTEGER) as OrderYear
  , o.RequiredDate as RequiredDate
  , o.ShippedDate as ShippedDate
  , SUM(ol.UnitPrice * ol.Quantity * (1 - ol.Discount)) as TotalOrderValue
  , SUM(ol.Quantity) as TotalProductCount
  , COUNT(*) as UniqueProductCount
FROM Shop."Order" as o
  JOIN o/Shop.OrderLine_Order/Shop.OrderLine as ol
GROUP BY o.OrderId, o.OrderDate, o.RequiredDate, o.ShippedDate

```

Add another view entity to show the expected table

```
SELECT
    o.OrderYear as OrderYear,
    SUM(CASE WHEN o.OrderQuarter = 1 THEN o.TotalOrderValue ELSE 0 END) as TotalSales_Q1,
    SUM(CASE WHEN o.OrderQuarter = 2 THEN o.TotalOrderValue ELSE 0 END) as TotalSales_Q2,
    SUM(CASE WHEN o.OrderQuarter = 3 THEN o.TotalOrderValue ELSE 0 END) as TotalSales_Q3,
    SUM(CASE WHEN o.OrderQuarter = 4 THEN o.TotalOrderValue ELSE 0 END) as TotalSales_Q4
FROM Shop.OrderVE o
GROUP BY o.OrderYear

```

* Mendix doc [Data Versioning with View Entities](https://docs.mendix.com/refguide/view-entity-data-versioning/)

view the latest status of an order

```
SELECT
    o.OrderId as OrderId,
    o.RequiredDate as RequiredDate,
    u.OrderStatus as OrderStatus,
    u.UpdateDate as UpdateDate
FROM Shop.OrderInfo o
JOIN o/Shop.OrderUpdate_OrderInfo/Shop.OrderUpdate u
JOIN (
    SELECT
        u.OrderId as OrderId,
        MAX(u.UpdateDate) as UpdateDate
    FROM Shop.OrderUpdate u
    GROUP BY u.OrderId
) latest ON (latest.OrderId = o.OrderId AND latest.UpdateDate = u.UpdateDate)
```

The above query is a nested query. It retrieves information from the OrderInfo table, then joins it with the OrderUpdate table. The result is a table with every update of every order. If you are only interested in the latest update of each table, retrieve the latest date an order is updated using MAX(u.UpdateDate) and combine it with the previous JOIN.


Another advantage of data versioning is that you can take a snapshot of the order status on any given date

For example, if you want to know the status of orders on 8/17/1997

```
SELECT o.OrderId AS OrderId,
    o.RequiredDate AS RequiredDate,
    u.OrderStatus AS OrderStatus,
    u.UpdateDate AS UpdateDate
FROM Shop.ORDER
Info o
JOIN O / Shop.OrderUpdate_Order Info / Shop.OrderUpdate u
JOIN 
( SELECT u.OrderId AS OrderId,
        MAX (u.UpdateDate) AS UpdateDate
    FROM Shop.OrderUpdate u
    GROUP  BY u.OrderId) latest ON (latest.OrderId = o.OrderId
                                AND latest.UpdateDate u.UpdateDate)
WHERE u.UpdateDate <  CAST ( '1997/08/17'  AS DATETIME)
```

* Mendix doc [Exporting Data with View Entities](https://docs.mendix.com/refguide/view-entity-expport-data/)
  
créer une OQE View et ensuite export mapping pour export json

```
SELECT
    c.CustomerId as CustomerID,
    c.CompanyName as Company,
    (c.FirstName + ' ' + c.LastName) as FullName,
    c.Phone as Phone, 
    c.Fax as Fax,
    (ba.Address + ', ' + ba.City + ' ' + ba.PostalCode + ', ' + ba.Country) as BillingAddress,
    (da.Address + ', ' + da.City + ' ' + da.PostalCode + ', ' + da.Country) as DeliveryAddress
FROM Shop.Customer c
    LEFT JOIN c/Shop.BillingAddress/Shop.Address ba
    LEFT JOIN c/Shop.DeliveryAddress/Shop.Address da
```

* Mendix doc [OQL](https://docs.mendix.com/refguide/oql/)

The Mendix Object Query Language (OQL) is a relational query language inspired by SQL. The major advantage of OQL is that it uses Mendix entity and association names instead of actual database table names. In that way, it is possible to create queries that use names from the data model of your Mendix app without thinking about how that data model is represented in the database.

In addition, OQL can use predefined relations (associations) to easily join objects without having to calculate which columns should be coupled. Despite these differences, many SQL keywords also work in OQL

* Mendix doc [OQL Clauses](https://docs.mendix.com/refguide/oql-clauses/)

- SELECT
- FROM
- WHERE
- GROUP BY
- HAVING (allowed only in combination with GROUP BY)
- ORDER BY
- LIMIT
- OFFSET

A unique feature of OQL is the ability to access attributes of associated objects using paths. For example:

```
SELECT
	Number AS RequestNumber,
	Sales.Request/Sales.Request_Customer/Sales.Customer/LastName AS CustomerName
FROM Sales.Request
```

It is possible to **build paths over multiple associations**. Associated entities can be reached from both directions. 
System associations System.owner and System.changedBy can also be used in such association paths, assuming they are enabled for the entity. For example:

```
SELECT
	LastName AS CustomerName,
	Sales.Customer/Sales.Request_Customer/Sales.Request/System.owner/System.User/Name AS UserName
FROM Sales.Customer
```

In the case when the association multiplicity type is **one-to-many or many-to-many, every attribute over association may result in multiple results per object**. If there are multiple attributes over association in the FROM clause, the result will be a **cartesian product** of associated objects meaning that there will be a row for every combination of associated objects. If you want to avoid that effect, consider rewriting the query using **JOIN**.

For example, when a Sales.Customer with LastName "Doe" has two associated Sales.Request objects with a Number attribute with values 1 and 2, the following query will return 4 rows:

```
SELECT
	LastName AS CustomerName,
	Sales.Customer/Sales.Request_Customer/Sales.Request/Number AS RequestNumber,
	Sales.Customer/Sales.Request_Customer/Sales.Request/Number AS OrthogonalRequestNumber
FROM Sales.Customer
WHERE Sales.Customer/LastName = 'Doe'
```

You can select data from both entities at once.

```
SELECT *
FROM Sales.Customer, Sales.Request
```

This returns get all attributes of both entities. Every object of the first entity is combined with every object of the second entity, which results in a cartesian product of objects of the two entities.

To avoid ambiguity in case of duplicate attribute names, you should use the entity name or alias when specifying columns to be selected. The format in that case is, respectively, <module>.<entity>/<attribute> or <alias>/<attribute>. You can also **retrieve all attributes** of a particular entity using <alias>/*.

A feature that is specific to OQL and is not in the standard SQL syntax is using paths to other entities over associations.

For example, when selecting from entity Sales.Customer, we can access an attribute of the associated entity Sales.Request:

SELECT FirstName, LastName
FROM Sales.Customer
WHERE
	Sales.Customer/Sales.Request_Customer/Sales.Request/Number = 1

The **HAVING** clause is used to filter aggregated results of GROUP BY. The difference between HAVING and WHERE is that **WHERE is applied to every object before the objects are grouped, and HAVING is applied only to the aggregate rows**.

The following query returns only aggregate rows for brands with more than one location:

```
SELECT Brand, SUM(Stock) AS SumStock, COUNT(*) AS LocationCount
FROM Sales.Location
GROUP BY Brand
HAVING COUNT(*) > 1
```

"ORDER BY" clause can include items that do not appear in the SELECT clause, except when SELECT DISTINCT is specified or when a GROUP BY clause exists. When UNION is used, the column names or aliases must be those specified in the SELECT clause of the first part of the query. 

The ORDER BY clause **cannot be used in view entities without a LIMIT or an OFFSET clause**

 if OQL v2 is enabled, an ORDER BY clause cannot be used in subqueries without a LIMIT or an OFFSET clause because the order of the subquery results may not be retained in the outer query.

ASC specifies that the results must be returned in ascending order, from the lowest to the highest value. This is the default sort type, so results are equivalent to not specifying ASC.

You can apply ASC and DESC modifiers to each criterion separately:

```
SELECT FirstName, LastName
FROM Sales.SalesPerson
ORDER BY LastName DESC, FirstName ASC
```

OQL allows you to specify paths to attributes of associated entities in the ORDER BY clause.

```
SELECT LastName
FROM Sales.Customer
ORDER BY Sales.Customer/Sales.Request_Customer/Sales.Request/Number
```

With the LIMIT (specifies the maximum amount of rows to return) and OFFSET (specifies how many rows must be skipped before returning the result rows) clauses, you can specify that only a portion of the results of a query is returned.

Mendix recommends **combining LIMIT and OFFSET clauses with ORDER BY because the return order of rows without an ORDER BY clause is undefined and can lead to unpredictable output**.

UNION takes multiple select queries and combines their results into a single result set. The resulting set by default only includes distinct rows. The **ALL** keyword can be used to include all rows. Rows are considered distinct if the combination of the column values is distinct from all other rows

self union of a table, returning fewer rows than the original table, as only distinct rows are included in the result.

```
SELECT FirstName FName, LastName LName
FROM Sales.Customer
UNION
SELECT FirstName FName, LastName LName
FROM Sales.Customer
```

UNION can be chained to use more than 2 select queries as a source. This query collects all distinct first and last names into a single column in a single table:

```
SELECT FirstName AS Name FROM Sales.SalesPerson
UNION
SELECT FirstName AS Name FROM Sales.Customer
UNION
SELECT LastName AS Name FROM Sales.SalesPerson
UNION
SELECT LastName AS Name FROM Sales.Customer
```

Performing a UNION with columns that are associations is possible, given the columns refer to the same entity for all select clauses.

The query below combines associations to the Sales.Customer entity from 2 different source entities with duplicates:

```
SELECT Cust.LastName as CustomerName FROM (
    SELECT Sales.Request/Sales.Request_Customer as RequestAssoc
    FROM Sales.Request
    UNION ALL
    SELECT Sales.ExtraInfo/Sales.ExtraInfo_Customer as RequestAssoc
    FROM Sales.ExtraInfo
) AS Cust
```

A **subquery** is an OQL query nested inside another query. A subquery can contain the same clauses as a regular OQL query. The entities from the outer query can be referred to in a subquery. A subquery can be used in different parts of the query.

A subquery can be used as a column in the SELECT clause. It can refer to other tables and expressions in FROM.

```
SELECT
	Req/Number AS RequestNumber,
	(
		SELECT COUNT(*)
		FROM Sales.Customer AS Cust
		WHERE Cust/LastName = Req/CustomerName
	) AS CustomerCount
FROM Sales.Request Req
```

It is possible to use a subquery in FROM. 

Subqueries in FROM can be combined with other tables

It is possible to refer to other tables in the outer FROM clause from a subquery

JOIN is also supported

```
SELECT Cust/LastName, Req/Number
FROM
	Sales.Request Req
	LEFT JOIN
	(
		SELECT *
		FROM Sales.Customer
	) AS Cust
	ON Req.CustomerName = Cust.LastName
```

A subquery can be used in the WHERE clause.

```
SELECT Brand, City
FROM Sales.Location AS Location
WHERE
	Location.Stock = (
		SELECT MAX(Stock)
		FROM Sales.Location AS MaxStockLocation
		WHERE Location.City = MaxStockLocation.City
	)
```

A subquery can be combined with the IN keyword. In that case, the expression is true if a value in the outer query matches one of the results of the subquery. In this case, the subquery can return any number of rows, but it should always return exactly one column.

```
SELECT FirstName, LastName
FROM Sales.Customer Cust
WHERE
	Cust/LastName IN (
		SELECT CustomerName
		FROM Sales.Request Req
	)
```

A subquery can be combined with the EXISTS keyword. In that case, the expression is true if the subquery returns at least one row. In case of EXISTS, the subquery can return any number of rows and any number of columns.

```
SELECT FirstName, LastName
FROM Sales.Customer Cust
WHERE
	EXISTS (
		SELECT * FROM Sales.Request Req
		WHERE Req/CustomerName = Cust/LastName
	)
```

  Subqueries can be used in a HAVING clause the in same way they are used in WHERE: as a value or combined with IN or EXISTS clauses. For other cases, the same limitations apply to the subquery outcome.


```
SELECT COUNT(*) AS LocationCount, SUM(Stock) as CityStock, City AS City
FROM Sales.Location AS Location
GROUP BY City
HAVING
	SUM(Stock) <= (
		SELECT COUNT(*)
		FROM Sales.Location
	)
  ```

```
SELECT COUNT(*) AS LocationCount, City AS City
FROM Sales.Location AS Location
GROUP BY City
HAVING
	EXISTS (
		SELECT *
		FROM Sales.Location AS SubLocation
		WHERE
			Location/City = SubLocation/City
			AND SubLocation/Brand = 'Rekall'
	)
```

The same result can be achieved with IN:

```
SELECT COUNT(*) AS LocationCount, City AS City
FROM Sales.Location AS Location
GROUP BY City
HAVING
	Location/City IN (
		SELECT SubLocation/City
		FROM Sales.Location AS SubLocation
		WHERE SubLocation/Brand = 'Rekall'
	)
```

* Mendix doc [OQL Expressions](https://docs.mendix.com/refguide/oql-expressions/)

An OQL expression is a query building block that returns a value or a list of values. Expressions can be one of the following:
- a constant
- a function
- a system variable
- a subquery
- a combination of attribute names, constants, system variables, functions, and subqueries connected by operators

**Aggregations** are functions that reduce a list of values from a retrieved column (or columns) into a single value. They can be used :
- as an attribute in a SELECT clause
- as a condition in a HAVING clause

- AVG
- MAX and MIN : Boolean values are treated as 0 and 1, Strings are compared alphabetically, NULL values are ignored.
- SUM : NULL values are ignored
- STRING_AGG : Combines multiple string values from a specified column into a single string. Each value is separated from the next by a specified separator string.
This aggregate function is supported in View Entities and Datasets starting from Mendix 11.2.0, whereas previously it was only available in Java actions.

**Parameters** are external variables that are referenced to by name in an OQL query. To use a defined parameter in a query, prepend the $ sign to the name of the parameter.
If you use undefined in IN and LIKE comparison expressions, the condition always returns true. In other cases, undefined parameters cause an exception.

* Mendix doc : [OQL Syntax](https://docs.mendix.com/refguide/oql-expression-syntax/)

data types : 
- BOOLEAN	Boolean	TRUE	Conditional data, can be TRUE or FALSE
- DATETIME	Date and time	'2025-07-05 00:00:00'	Date and time data
- DECIMAL	Decimal	5.3	Floating point numeric data
- INTEGER	Integer/Long	5	Integer data
- LONG	Integer/Long	5	64 bit width integer data
- STRING

Literals represent values that are constant and are part of the query itself

- BOOLEAN	Conditional constants : TRUE, FALSE
- STRING	String literal 's*'
- INTEGER and LONG	Natural number literal d+
- DECIMAL	Real number literal d+.d+
- NULL

There is **no direct support for DATETIME literals**. For functions that take DATETIME as input, it can be represented with a **STRING in a ISO date time format** or a **LONG value representing Unix seconds**.

Most XPath system variables can be used in OQL

about using system variables in OQL:
- \[%CurrentObject%\] is not supported in OQL.
- The \[%CurrentUser%\] system variable contains an association with the System.User object.
- The \[%UserRole_<role name>%\] variable contains an association with the object of entity System.UserRole that corresponds to role <role name>.
- Both \[%CurrentUser%\] and \[%UserRole_<role name>%\] can be used only as references. They cannot be cast to other data types.

gets the Name from all Sales.Person objects that are owned by current user:
```
SELECT
	Name
FROM
	Sales.Person
WHERE
	System.owner = '[%CurrentUser%]'
```

Name from all Sales.Person objects that are owned by users with role Manager:
```
SELECT
	Name
FROM
	Sales.Person
WHERE
	System.owner/System.User/System.UserRoles = '[%UserRole_Manager%]'
```

The return type of all time-related \[system\] variables and expressions is Date and time. They can be used the same way as values of type Date and time.

```
SELECT
	BirthDate,
	DATEPART(YEAR, '[%BeginOfCurrentYear%]') AS CurrentYear,
	DATEDIFF(YEAR, BirthDate, '[%CurrentDateTime%]') AS Age,
	'[%BeginOfCurrentDay%] - 3 * [%YearLength%]' AS TodayThreeYearsAgo
FROM
	Sales.Person
```

Binary operations perform **type casting** when operands have different types ; The resulting type will be the operand type with the highest precedence DECIMAL > LONG > INTEGER

Other Operators
- LIKE	Matches a string to a specified pattern (wildcard characters : % = Matches zero or more of any character; _ = Matches one of any character ; special characters should be escaped with the \ escape character)

ex : string that has 4 of any character ending with "ment":
```
Select PropertyType FROM RealEstate.Properties WHERE PropertyType LIKE '____ment' 
```
  
- IN	Matches any value in a subquery or a list of expression values.

```
SELECT LastName, FirstName
FROM Sales.Customer 
WHERE LastName IN
    (SELECT subq.LastName 
    FROM Sales.Order subq
    WHERE subq.Number > 3)
```


- EXISTS	Test for the existence of any rows when executing the subquery (Returns TRUE if a subquery returns at least one row) ; can be used to check if an entity contains any object matching a condition

test if customer with last name Mose
```
EXISTS (SELECT * FROM Sales.Customer WHERE LastName = 'Mose')
```

get all customers that also have orders placed:
```
SELECT *
FROM Sales.Customer customer
WHERE EXISTS
    (SELECT *
    FROM Sales.Order order
    WHERE order.LastName = customer.LastName)
```

- IS	Tests if a value is NULL ; ex. : filter out rows with values that are NULL.
```
	SELECT Revenue, Cost FROM Sales.Finances WHERE Revenue IS NOT NULL 
```

- CASE conditional expression

If the result of a following WHEN condition is TRUE, the value of the CASE expression is the result that follows the condition and the remainder of the CASE expression is not processed. If the result is not TRUE, any subsequent WHEN clauses are examined in the same manner. If no WHEN condition yields TRUE, the value of the CASE expression is the result of the ELSE clause. If the ELSE clause is omitted and no condition is TRUE, the result is null.

2 ways to use it 

1) simple : input_expression will be compared to when_expression. If input_expression matches when_expression, the result of the whole CASE expression will be result_expression given after THEN. The data types of input_expression and when_expression must tch.
   ```
 	CASE input_expression
	{ WHEN when_expression THEN result_expression } [ ...n ]
	ELSE else_result_expression
	END
```

Ex. :

```
SELECT
	LastName,
	Number,
	CASE Number
		WHEN 7 THEN True
		ELSE False
		END AS IsLuckyNumber
FROM Sales.Order
```

3) extended : boolean_expression is evaluated and if it is TRUE, the result of the whole CASE expression will be result_expression given after THEN. boolean_expression must have return type BOOLEAN.


```
	CASE
	{ WHEN boolean_expression THEN result_expression } [ ...n ] 
	ELSE else_result_expression
	END
```

Ex. :

```
SELECT
	LastName,
	Number,
	Price,
	CASE
		WHEN Price > 7 THEN 'Priority'
		WHEN Number = 7 THEN 'Lucky'
		ELSE 'Regular'
		END AS OrderType
FROM Sales.Order
```

In both instances, else_result_expression is the result of the whole CASE expression, when no previous when_expression matched or no previous boolean_expression returned TRUE.


currently supported **functions**:

- CAST : converts an expression to a specified data type
- COALESCE : Returns the value of the first expression that is not NULL. Ex. : Selecting a non-null name for a customer, ignoring if it is the first name or last name
	
```
SELECT COALESCE(LastName, FirstName) AS Name FROM Sales.CustomerInfo
```
- DATEDIFF :  the difference between two given DATETIME expressions. The difference is given in the specified unit.
- DATEPART : retrieves a specified element from DATETIME values. The return type is INTEGER.
- LENGTH returns the length in characters of the result of a string expression.
- LOWER Converts all uppercase characters in a given string to lowercase.
- RANGEBEGIN Extracts the initial value of a range parameter. Ex. : This query uses $range_future to retrieve all periods that end in the future:

```
SELECT End, Revenue FROM Sales.Period
WHERE End > RANGEBEGIN($range_future)
 ```

- RANGEEND : Extracts the end value of a range parameter. Ex. : retrieve all periods that ended before the end date of $range_past

```
SELECT End, Revenue FROM Sales.Period
WHERE End < RANGEEND($range_past)
```

- REPLACE : takes an input string and replaces all occurrences of a specified string within it with another string. The behavior of the REPLACE function relies on underlying database implementation, which varies by database vendor. For most supported databases, the default behavior of REPLACE is case-sensitive
- ROUND : Rounds a numeric expression by reducing precision after the decimal point.
- UPPER : Converts all lowercase characters in a given string to uppercase




{% include links.html %}

