# Boat-Database
Project on boat database using SQL with detail business rules, EER and normalization

<img src="https://vizboat.com/wp-content/themes/yootheme/cache/440RS-chrome-black-361f94fb.jpeg" align="right"
     alt="Size Limit logo by Anton Lovchikov" width="500" height="300">

## Business Rules of BOAT Database

Boat database keeps the track of types of boats and their Services, Owners and Employees. Name of the database is boats with several entities like BOAT, HARBOUR, CRUISE SERVICES (WEAK ENTITY), CRUISE TYPE, EMPLOYEE, OWNER.

BOAT is the entity with attributes Register Number (Primary Key), Size, Boat Type. Each boat is registered with Register Number, a boat must be exactly one of “Boat Type” subtypes like YACHT_BOAT, CRUISE_BOAT. The attributes of YACHT_BOAT is Length, Height, Area, where Area is the derived attribute of multiplication of Length, Height. YACHT_BOAT is stored in particular HARBOUR. But in every HARBOUR, at most YACHT_BOAT is stored. The attributes of HARBOUR are sector number as Number (Primary Key) and Location.

CRUISE_BOAT, the other Boat Type is with attribute Engine ID. Within CRUISE_BOAT there are CRUISE SERVICES. Each CRUISE BOAT which may undergoes many CRUISE SERVICES or may not undergoes any CRUISE SERVICES. Every CRUISE SERVICE belongs to exactly one CRUISE BOAT. Among Date, Work, Hours attributes of CRUISE SERVICES, Date is the partial Identifier. The CRUISE_BOAT with existing Engine ID have exactly one CRUISE TYPE with Model (Primary Key), Capacity, and Weight attributes. CRUISE TYPE may have many existing Engine ID or may not have any.


In every CRUISE TYPE at least one EMPLOYEES works, in similar way every EMPLOYEE works in at least one CRUISE TYPE depending upon their multi skills, Salary, Shifts in duty with unique Employee ID (Primary Key). Every EMPLOYEE maintains to at least one CRUISE SERVICE. Most CRUISE SERVICEs will have more than one EMPLOYEE working on them, but some new CRUISE SERVICEs have no EMPLOYEEs working on them.

Each and every OWNER with composite attributes like Name (FName, LName), Address (Street, Pin), Phone (Area Code, Local Num), OWNS at least one CRUISE TYPE with purchase date (Pdate as Primary Key), whereas CRUISE TYPE may have many OWNERs or may not have any OWNER.


An OWNER may or may not be one of subtypes like CORPORATION, PERSON, LOCAL BUSINESS. On the other hand, an OWNER may be any two (or even three) of these subtypes at the same time. LOCAL BUSINESS attributes similar to its super type OWNER but CORPORATION and PERSON subtypes differ by Company ID and Ssn attributes respectively.
