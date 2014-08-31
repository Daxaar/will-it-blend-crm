will-it-blend-crm
=================

Code samples answering questions that come to mind during CRM 2011 Development.

- Q1. Can shared variables be passed from a sync to async plugin?

Yes they can - if you set the SharedVariable in a pre-operation plugin you must access it in the async plugin using the ParentContext.  Basic code sample to follow.

- Q2. How do I load related entities when using the OrganizationServiceContext?

Use the LoadProperty method of the OrganizationServiceContext passing in the entity ( which must be attached ) and the name of the relationship.  You can get the latter by looking for the relationship name on the typed entity. 

- Q3. Does an update to the Target within a Post Operation plugin get saved to the database?

No because the data change operation has already been applied to the database (although not yet committed).

- Q4. Does throwing an exception in a Post Operation plugin prevent the data change operation?

Yes because although the POST plugin cannot participate in the data change operation transaction.  That same transaction hasn't yet been commited to the database.  Any exception thrown in the plugin execution pipeline causes the transaction to rollback.

- Q5. Does a Post Image contain the latest target attribute values?  For example, if the firstname attribute is updated on the contact record, will the updated value be available in the Post Image or will it still hold the original value as it would be in a Pre Image?

Post Image contains the final value committed to the database.  That is to say that even if the value is updated in a Pre Operation plugin this value will be seen in the Post Image.
