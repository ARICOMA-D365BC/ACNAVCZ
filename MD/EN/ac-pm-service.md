---
title: "AC Promis - Service"
author: Autocont
ms.custom: na
ms.date: 07/18/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: dynamics-nav-2018
ms.translationtype: Human Translation
ms.sourcegitcommit: 
ms.openlocfilehash: 
ms.contentlocale: en
ms.lasthandoff: 

---


# <a name="ac-pm-service"></a>Service

This chapter describes the process of processing a service order focused on the specifics of the means of transport. The standard functionality of the Servis module is not described.

## MODULE SERVICE KNOB DATA
### SERVICE MODULE MANAGEMENT
#### Setting up a service
##### General

- Safe break. reporting time - In the field, the default period is set before the expiry date for the service activity. With this in advance, service activities will be advised to implement; it is therefore a time limitation in the future in which the system tests the service activities to be performed.
- Safe break. job time - In the field, a timeout is set for the planning of delayed service activities. Then the date of commencement of a service order for delayed service activities will be proposed as Working Date + Safe Pass. order time.
- Default power unit - In the field, the unit of measurement for which the performance delay specified for service performance is tested
- Condition for cars. Vehicle PS based - Vehicle / freight wagon status will be set in the field to achieve synchronized service subject

##### Required fields

In addition, some special fields are mentioned that affect the behavior of the system in the service area

Parameter

- Obligatory vendor - enforces vendor control in service documents (also a holder of the center dimension)
- Required recipient code - enforces the Recipient Code entry in service document headers if there is at least one entry in the Recipient Address table in customer relationship. This setting checks the use of the correct postal address on the service documents.

### SERVICE SOURCES MANAGEMENT
#### Source for service activities

- Required service activity - the field activates charging of service line and charging of service activity item; the service code must also be entered in the service line.

### FLEET MANAGEMENT
#### Service Dates Templates

The diary organization of service planning allows multiple users to work in parallel. It is necessary for the user to define the required servicing activity logs. Templates allow access to diaries.

#### Setting up a service log
- Liability Center - Each log should be assigned a responsibility center. This parameter is then transferred to service headers and affects the display of service documents for users whose filter service center is set.

#### Service activities
The table is intended to set the service activities to be monitored and reported on vehicles / lorries.

- It is possible to set the service activity for another unit of measurement than km (eg hourly hours).
- Next, it is possible to set up service system - if Service option is set, service activities are primarily carried out through service orders; if the Purchase option is set, then the service is outsourced by purchasing the service. It is also possible to set up an external service provider.
- Tracking power type - When Position is selected, then the system automatically offers to record the mileage obtained from the 4056891 Vehicle Position Entry table, for power service activity. mileage obtained from external telematics systems. For other service activities that depend on performance other than the distance traveled (Position) - such as hourly hours, the field must be left blank.
- Resource number - In the field, the source number with which the service activity is charged through the service order is indicated.

#### Groups of service activities
A service group dial allows grouping service activities into groups. The purpose is to reduce administration and allow more service activities to be assigned to vehicles / trucks through a group of service activities.
#### Assigning service activities
Individual service activities can be assigned to a service group to help set up the Service Assignment Assignment
#### Relation between the subject of the service object and the group of transport equipment
The settings are used to control the automation of creating records of service items from vehicle records and freight wagons.

- Automatically create a service item - Selecting the field automatically activates the service subject according to the vehicle / truck wagon. The startup activation time is defined as the vehicle / truck card state (see Service Settings).
    *<empty> - by auto setting is off.
    *Internal - service subject only when the car / truck card is internal.
    *All - The subject of the service is created for the car / freight wagon, both internal and external.

- Service Object Component - The choice also establishes the freight wagon as a component to the superior service item (wagon). There is no point setting for semi-trailers / trailers, turning on the parameter is only practical for fixed-wagon trucks.

#### Setting the safe performance
Table settings are used to plan performance service activities. Allows you to define the remaining power within the specified service limit. If the current remaining performance is less than safe, the corresponding service activity is designed in the service workbook.
#### Registration Synchronization Vehicle / Truck <-> Subject of service
After the link is created, the changes made to one of the records in the second record are synchronized:
- Name <-> Description
- Name 2 <-> Description 2
- Search Name <-> Search Name
- Registration mark (license plate) <-> Registration mark (license plate)
- Operator number <-> Customer ID

## SERVICE OBJECTION EVIDENCE
### AUTOMATIC FOUNDATION OF A NEW SUBJECT OF SERVICE
The process runs on the Vozu res. Freight wagon. Once the registration parameters have been set, the status will be switched to Preparation (according to the service settings):
### ADDITIONAL FOUNDATION OF THE SUBJECT OF SERVICE
The process is started on the Vehicle / Truck. Typically, it concerns external cars, for which it is not necessary to automatically create a service card for the vehicle card. The Service Object Card is established only when the first service order is performed.
- Action Create Service Item - The event creates a new service subject card regardless of the Vehicle / Freight Card status
### CONNECTING / DISCONNECTING THE SUBJECT OF SERVICE
The actions are more likely to be used for exceptional uses where, for some reason, a service item is established independently of the Wagon / Freight Wagon or, on the other hand, it is necessary to separate and unsynchronize both.
## TRADING SERVICE ACTIVATION
### CLASSIFICATION OF GROUPS OF SERVICE ACTIVITIES
By assigning one or more service groupings, the service activities contained in the following groups are assigned to the vehicle / freight wagon:
## PLANNING SERVICE ACTIVITIES
The service activities log is intended to provide service and service planning requirements.
### WORKFLOW REFLECTION OF SERVICE REQUIREMENTS
In order to generate new document outputs or reschedule existing documents from the Service Log, a reconciliation procedure needs to be implemented for that line. The reconciliation features 3 roles:
- Dispatcher - defines the "window" in which the service is to be performed; the window is defined by the date and time of the start of the service and analogy is defined by the end of the service
- Fleet Manager - Defines the date for service from your perspective; ideally it should be designed within the time period defined by the dispatcher, but it can be set arbitrarily
- Service - Defines a date analogously to a fleet manager, but from a service point of view

If all data is within the interval defined by the dispatcher and the date of the administrator and the service is the same, the service term is agreed. Schematically, the reconciliation is shown in the following figure:
- the first line (green) has passed the reconciliation procedure and can go into the next phase of the process
- The second line (red) did not pass the procedure as the fleet manager set the date for service outside the scheduling window. Conflict now needs to be resolved by dispatcher and service. Reconciliation can take place in any number of iterations and will continue until agreement is reached as in the first line. Achieving Term Match is indicated in the Done Field field.

Representatives of the roles listed above will receive service rows that require their attention by filtering them by field
- Dispatching term = Yes (dispatcher role)
- Date spr. car. park = Yes (manager role)
- Service Term = Yes (Roll Service)
### CREATING A REQUIREMENT FOR SERVICE ACTIVITIES
Service requirements are entered into the so-called Service Activity Log. The process consists of the following steps:
- Vehicle insertion
- Setting the service method
- Internal - service performed at your own service center must be set to Document type = Service.
- External - Service performed externally must be set to Document type = Purchase and filled Supplier number.
- Specifying required service activities (Ribbon Service Routine)

Service tasks can be generated by the Update Service Line feature. an activity that, according to the specified parameters, establishes one or more rows of service activities.
The function parameters are:
- Safe Runtime - refers to time servicing activities and is a time-out in advance of the design before the deadline
- Use the safe reporting power - the parameter turns on the use of the safety parameters. performance.
- Use Alternate Main Power Safety - The parameter allows you to define a different safe power for the calculation than set in the setting; if this parameter is on, you still need to define it
- Safe performance
- Performance code

### GENERAL GENERATION OF REQUIREMENTS UNDER SERVICE ACTIVITIES
Bulk request generation includes advanced planning features that evaluate:

- the state of the service activities of the means of transport
- state of completion of documents (elements of dynamic planning)
- the need to initiate evidence for new means of transport

The output is filled with service activities log, including the so-called Event Notification when the system informs about the type of action to be performed with the given line of service activities.

The diary lines are filled by launching the Get action report action. Once the action is started, a form for entering the calculation parameters is displayed.

The result of the calculation is the proposed rows of service logs with a reported action and a mnemonic description of service activities compiled from the data of a detailed line of service activities.

    Meaning of event announcement:

   - *New* - The system proposes to create a new document whose type is specified in the Document Type box
- *Redesigned* - The system proposes to reschedule an existing document whose identification is indicated in the Document Type and Document Number fields
- *Cancel* - The system proposes to cancel an existing document because, according to the state of planning parameters, it has evaluated it as redundant

- *Accounting for activities* - concerns in particular the initiation of service cycles for newly introduced means of transport; it can also be used to record purchased service activities for which records can not be used for service orders. By charging for service activities, only service items are recorded, not service items.

    The reported actions can be manually changed in certain cases.

The actual operation of the reported action can be performed by Performing reported actions ... if the service log lines are set correctly.
In particular, it concerns:

- Achieving compliance at the planning date - Date agreed = Yes
 - The event report announces the action to be performed with the service journal line
 - Accept Received Actions = Yes field
  - Depending on the reported action, the appropriate document type (Service Order, Purchase)

The result is the implementation of the reported action - most frequently the new Service Order and the deletion of the service activity log line.
## SERVICING
A service order is the basic document for service records. These may be generated from the service log (see chapter 5.4 Schedule Service Activities) or may be created manually.
### RECEIVE SERVICE
If the service order has been generated from the service log, it is still necessary to check and complete other necessary parameters after creating the documents.
#### Inspection / modification of service activities
The lines of service activities to be performed for the service subject are accessed from the Rows tab by selecting Service Activity. You can edit the list of service activities - delete service activities.
#### Accept
To receive the subject of the service, the form of the subject of the service subject is determined.
Vehicle equipment is entered on the Equipment tab.

Tank content and km state are entered on the Status tab. The km state is preloaded according to telematics data. If there is no (external vehicle) or if the telematics data is defective, it can be modified

### SERVICING
Service commencement, as well as other service progress, is recorded in the Repair Status Code field.

The record of the service activities itself is entered manually or by the help of the Insert Service:
In addition, all materials consumed and the work of the technicians are entered in the paper.

The user can charge or execute the rows directly by the authorized person before closing and billing the order.

Once entered, the rows will be marked for posting and your own posting will be triggered. For the**Material and Resource**(work)**consumption, the option**Add**or**Add and Billing**will be selected.

The Add and Consume option will be triggered for service performance registration.

### CHECKING THE STATUS OF SERVICE CYCLES
Once the service activities have been posted, it is possible to check the status of the service cycles of the vehicle. The vehicle's service card statistics are displayed in which:
- the date of the last servant is recorded. cycle and power condition,
- the expected power level for servicing is calculated,
- the remaining power is calculated until servicing; this figure is calculated with each view of statistics by telematic data items,
- the value in the Number of Served Servers column is increased. Cycles (by clicking can be expanded details in the form of items of service activity).

#### Service Journal
When charging service activities (from a service log or from a service order), it is recorded in the Service Log.
Each log associates items from one billing.
These include in particular:
- Performance status when properly serviced - What performance should be performed properly
- Service performance status - What performance was actually performed by the service
- Date of regular service - when the service should have been properly performed
- Settlement date - when the service activity was actually performed
## SERVICE RECORDING ACTIONS
The system includes support for and control of service call actions. The Service Call Action Card has a defined name and the beginning and end of validity. All the vehicles for which the call is assigned are listed in the rows.
Lines can be entered either manually or by hand. import functions.
#### Connect a service call action

Service call actions are checked and assigned to the Vehicles in the Service Logs when the Get Actions Report is started. When a service action is assigned, the service activity log line is marked with the Service Action flag exists. The assignment details can then be displayed through the Ribbon Action action from the ribbon.

In a service order, the service request is checked after the service item has been placed in the service order line. The user will see the assignment information along with a list of up to 3 assigned actions.

Notification of service call actions is deactivated after assignment or posting. By posting the service order picker (service order), a service call action item is created. In the case of a credit, the compensation service charge is charged. This will cause the service call for the vehicle to become active again.
#### Entry Event Items

By posting Service Delivery, you can also receive service call acceptance items.
The value in the Executed field indicates a positive (delivery) or negative (delivery return) service charge. action.

The sum of these values ​​for service a call action with the same action number, type and vehicle number, then the state of execution of the service call action (0 - not executed, 1 - performed).

## <a name="see-also"></a>See Also  
[AC ProMIS](ac-pm-promis.md)