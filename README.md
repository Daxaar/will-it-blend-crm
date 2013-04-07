will-it-blend-crm
=================

Code samples answering questions that come to mind during CRM 2011 Development.

- Q1. Can shared variables be passed from a sync to async plugin?
-  A. Yes they can - if you set the SharedVariable in a pre-operation plugin you must access it in the async plugin using the ParentContext.  Basic code sample to follow.
