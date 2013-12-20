will-it-blend-crm
=================

Code samples answering questions that come to mind during CRM 2011 Development.

- Q1. Can shared variables be passed from a sync to async plugin?
- A. Yes they can - if you set the SharedVariable in a pre-operation plugin you must access it in the async plugin using the ParentContext.  Basic code sample to follow.

- Q2. How do I load related entities when using the OrganizationServiceContext?
- A. Use the LoadProperty method of the OrganizationServiceContext passing in the entity ( which must be attached ) and the name of the relationship.  You can get the latter by looking for the relationship name on the typed entity. 
