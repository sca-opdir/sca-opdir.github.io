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

{% include links.html %}

