# salesforce

-SF supports standard objects, custom, external, big objects, platform events.
-Objects are containers for your information, but they also give you special functionality. For example, when you create a custom object, the platform automatically builds things like the page layout for the user interface.
-Object relationships are a special field type that connects two objects together.
-Lookup Relationship: links two objects together so that we can lookup one object from the related items on another object. it can be one-one or one-many. Objects in lookup relationships usually work as stand-alone objects and have their own tabs in the UI.
-Master-Detail : one object is master and another is detail. Master object controls certain behaviors of the detail object, like who can view the details data. In this relationship , detail object doesn't work as standalone, highly dependent on master. if a recoed in master is deleted all its related detailed records gets deleted. We always create relationship field on the detail object.
-Hierarchical relationship: special type for lookup relationship. main differnce is only available on the user object. creating management chains between users.
-Data Import Wizard: less than 50000, no need of automating import process, objects need to import are supported by import wizard.
-Data Loader: 50000 to 5 million record we can import, morethan 5 million we need to use AppExchange, schedule the regular data loads, if the objects are not supported by import wizard. Uses SOAP API to process records, to make it faster we can use Bulk API as it does parallel processing and fewer network round-trips.
-Data Export: manually/automatically we can export once every 7 or 29 days.
-Data Security: Orh level, Objects, Field, Record ..
-Record level access can be managed in 4 ways:
  Org-wide defualts: lock down data to most restrictive level, then use other record-level secuirty and sharing tools to selectively give access to users.
  Role Hierarchies: access to high level hierarchy user to access user info under him. no need to match to org chart exactly , instead each   role in the hierarchy should represent a level of data access the user needs.
  Sharing rules: automatic exceptions to org-wide defaults for particular groups of users, so they can get to records they don't own. used   to give additional access to records. less restricted than org-wide
  Manual sharing: record owners can share info with other users.
-Audit system: Auditing provides imp info for diagnosing potential security issues. Look for changes in Record modification fields, LOgin    history, field history tracking, setup audit trail.
-Manage Object Permissions: A user can have one profile and many permission sets.
   - User profile determines the objects they can access and things they can do with any object record.
   - Permission sets grant additional permissions and access settings to a user.
   - Use profiles to grant minimum permissions and settings and then use permission sets to grant more.
   - A profile can be assigned to many users but a user can have only one profile.
   - WIth standard profile we can't edit object permissions 
   
The page layout editor lets you:
Control which fields, lists of related records, and custom links users see
Customize the order that the fields appear in the page details
Determine whether fields are visible, read only, or required
Control which standard and custom buttons appear on records and related lists
Control which quick actions appear on the page

Custom links can link to an external URL, such as www.google.com, a Visualforce page, or your company’s intranet. Custom buttons can connect users to external applications, such as web pages, and launch custom links

Object-specific actions : Object-specific actions have automatic relationships to other records and let users quickly create or update records, log calls, send emails, and more, in the context of a particular object.
Object-specific Create actions create records that are automatically associated with related records.
Object-specific Update a Record actions make it easy for users to edit records. You can define the fields that are available for update.
Object-specific Log a Call actions let users enter notes about calls, meetings, or other interactions that are related to a specific record.
Object-specific custom actions invoke Lightning components, flows, Visualforce pages, or canvas apps that let users interact with or create records that have a relationship to an object record. If you’re new to Visualforce, don’t worry. You can learn all about it in another module. For now, remember that Visualforce pages allow you to do really cool customizations in your actions.
Object-specific Send Email actions, available only on cases, give users access to a simplified version of the Case Feed Email action in the Salesforce mobile app. You can use the case-specific Send Email action in Salesforce Classic, Lightning Experience, and the Salesforce mobile app

Global actions
You create global actions in a different place in Setup than you create object-specific actions. They’re called global actions because they can be put anywhere actions are supported. Use global actions to let users log call details, create or update records, or send email, all without leaving the page they’re on.
Global actions live on a special layout of their own, known as the global publisher layout. It isn’t associated with an object, and it populates the global actions menu in Lightning Experience. Users can access the global actions menu by clicking Global Actions menu icon in the Salesforce header.

Quick Actions: They offer a fast way for mobile users to launch a specific workflow in the Salesforce mobile app, like creating records, logging calls, or sharing files

Compact Layouts
When you open a record in the Salesforce mobile app, you see highlights about that record in the header of the page. Compact layouts control which fields appear in the header. For each object, you can assign up to four fields to display in that area

 --While formula fields calculate values using fields within a single record, roll-up summary fields calculate values from a set of related records, such as those in a related list
 
 --Validation rules verify that data entered by users in records meet the standards you specify before they can save it. A validation rule can contain a formula or expression that evaluates the data in one or more fields and returns a value of “True” or “False.” Validation rules can also include error messages to display to users when they enter invalid values based on specified criteria
 
-- Picklist:
We have three types of picklists:
Standard
Custom
Custom Multi-Select
And picklist fields can have the following properties:
Restricted
Dependent or Controlling

--For standard picklists, each value can have up to 255 characters, not including line breaks and returns. This applies to single-select and multi-select picklists

Limits for Custom Picklists
Custom single-select picklists can have:

Up to 1,000 values
Up to 255 characters per value
Custom multi-select picklists can have:

Up to 500 values
Up to 255 characters per value
---
Functional Limitations for Custom Picklists
You can make a custom single-select picklist field into a restricted picklist only if the picklist has fewer than 1,000 values (or entries). You can make a custom multi-select picklist field into a restricted picklist only if the picklist has fewer than 500 values (or entries). A restricted picklist’s values are limited to only those values defined by a Salesforce admin. This prevents users from loading redundant or erroneous values through the API.
Global picklist value sets are always restricted picklists. This is a good thing, as it preserves data integrity. (Global value sets are shared across objects. Reuse the value set for any custom picklist field.)
For custom picklist fields that use a global picklist value set, you can change from a single-select to multi-select picklist and vice versa. However, you can’t change the picklist to a different field type such as checkbox, currency, or text.
You can’t undo a custom picklist field’s association with a global value set. If you need a picklist field to use a different global value set, or different individual values, delete the custom picklist field and create a new one in its place.

--Dependent Picklists
Guide users, save UI space, and further improve data integrity with a dependent picklist. A dependent picklist filters values for one picklist based on a selection from another picklist or a checkbox (the controlling value) on the same record.

	                           Standard Picklist	Custom Picklist	Custom Multi-Select Picklist
Add/Remove from Page Layouts	yes              	yes	             yes
Delete from Your Org		      No                  yes	             yes
Set a Default Value	          yes	yes	yes
Use a Formula for a Default Value		No yes	yes
Can Select Multiple Values		No	yes  No
Can Add Values via Apps or API	yes	yes	yes
Can Be Restricted		No yes	yes
Can Be a Dependent Picklist		No yes	yes

--Decide whether to replace the value or leave it blank. If you replace it with a blank value, existing records will not display the value anymore. To keep the value on existing records, use Deactivate, instead of Del.
--If you replace a parent value in a controlling picklist, the picklist dependency on that value is lost. After replacing the parent value, re-create the dependency using the new parent value.
--Global value sets let you share the same picklist values with more than one picklist field.
--AppExchange is the marketplace for all things Salesforce, including apps, Lightning components, Flow solutions, and more.

--What Is External Services?
With External Services, you use declarative tools to import Swagger or Interagent-based API definitions right into Salesforce using a schema. Once you import the definitions, you can create a flow based on the Apex classes generated from your External Services registration


 
