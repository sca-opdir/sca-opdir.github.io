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

* Medium article : [Convert a Mendix Page to PDF](https://medium.com/mendix/how-to-convert-a-mendix-page-to-pdf-using-the-document-generation-module-a63714472cc4)
-> Using the 'Document Generation' Module

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



{% include links.html %}

