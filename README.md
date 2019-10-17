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
   
   
  

  
