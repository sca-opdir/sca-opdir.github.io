---
title: SAP webi
keywords: BI
last_updated: June 18, 2024
tags: [BI]
summary: "diverses infos sur SAP webi"
sidebar: mydoc_sidebar
permalink: SAPwebi_autres_infos.html
folder: mydoc
---

### Concaténation de chaines

Par ex: pour agréger en concaténant City par State

[source](https://community.sap.com/t5/technology-blogs-by-members/string-aggregation-on-webi-report-level/ba-p/13168326)

To achieve the result follow the steps:

1) First drag State & City objects on report and sort result by State and City in ascending order.

2) Create dimension like

Cities =[City]+";"+Previous(Self;([State]))

3)Create measure like
