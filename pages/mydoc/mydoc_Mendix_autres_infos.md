---
title: Diverses infos Mendix
tags: [Mendix]
last_updated: June 12, 2025
keywords: Mendix
summary: "infos diverses et tips Mendix"
sidebar: mydoc_sidebar
permalink: Mendix_autres_infos.html
folder: mydoc
---


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


{% include note.html content="infos diverses sur FME" %}
