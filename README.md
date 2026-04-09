# Revolutionizing Agriculture with AgriEdge Or-Mange Ltd

## A Salesforce-Driven Order Management Solution

---

## Project Overview

AgriEdge is a Salesforce-based Order Management System designed to streamline agricultural business operations. It enables efficient handling of orders, inventory, shipments, and customer interactions using automation and secure data management.

This project demonstrates the use of Salesforce features such as:

* Custom Objects and Fields
* Role-Based Access Control
* Process Builder Automation
* Apex Programming

---

## Objectives

* Automate order processing workflows
* Maintain inventory and shipment tracking
* Ensure secure data access using profiles and roles
* Improve efficiency using Salesforce automation tools

---

## System Architecture

The system is built using Salesforce CRM components:

* Custom Objects

  * AgriEdge Orders
  * AgriEdge Order Items
  * AgriEdge Inventory
  * AgriEdge Shipment

* Automation

  * Process Builder triggers Apex class

* Backend Logic

  * Apex Class for task creation

---

## Data Model

### AgriEdge Orders

* Order Number (Auto Number)
* Customer (Lookup to Account)
* Order Status (Picklist)
* Order Date (Date/Time)
* Total Amount (Currency)
* Payment Status (Picklist)
* Shipping Address (Text Area)
* Discounted Total (Formula)

---

### AgriEdge Order Items

* Order (Lookup)
* Product (Lookup)
* Quantity (Number)
* Unit Price (Currency)
* Total Price (Formula)

---

### AgriEdge Inventory

* Product (Lookup)
* Stock Quantity (Number)
* Reorder Level (Number)
* Warehouse Location (Text)
* Stock Status (Formula)

---

### AgriEdge Shipment

* Order (Lookup)
* Tracking Number (Text)
* Carrier (Picklist)
* Status (Picklist)

---

## Security Implementation

* Profiles Created

  * Platform 1
  * Platform 2
  * Platform 3

* Roles Hierarchy

  * CEO
  * Sales Representative
  * Warehouse Manager
  * Finance Team

* Field-Level Security

  * Restricted fields such as Payment Status, Total Amount, and Discount Total

---

## Automation

### Process Builder

* Trigger: When AgriEdge Order is created
* Action: Calls Apex Class

### Apex Class

```apex
public class OrderTaskCreator {

    @InvocableMethod
    public static void createTaskForOrder(List<AgriEdge_Orders__c> orders) {

        List<Task> tasks = new List<Task>();

        for(AgriEdge_Orders__c ord : orders) {

            Task t = new Task();
            t.Subject = 'Follow up on Order';
            t.Status = 'Not Started';
            t.Priority = 'Normal';
            t.WhatId = ord.Id;

            tasks.add(t);
        }

        if(!tasks.isEmpty()) {
            insert tasks;
        }
    }
}
```

---

## Features

* Automated Task Creation
* Role-Based Data Access
* Inventory Monitoring
* Shipment Tracking
* Order Lifecycle Management

---

## Demo

The demonstration includes:

* Creating a new order
* Automatic task creation
* Role-based field visibility

---

## Technologies Used

* Salesforce CRM
* Apex Programming
* Process Builder
* Lightning Experience

---

## Future Enhancements

* Integration with IoT devices for real-time monitoring
* AI-based demand prediction
* Migration to Flow Builder

---

## Author

Rupesh M
Salesforce Developer

---

## Conclusion

AgriEdge demonstrates how Salesforce can be effectively used to build scalable, secure, and automated solutions for agricultural businesses, improving productivity and operational efficiency.
