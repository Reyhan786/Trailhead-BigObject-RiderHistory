# Salesforce Custom Big Object: Rider History

## Overview
This project demonstrates how to create, define, and deploy a **Custom Big Object** in Salesforce to store large volumes of data for a car-sharing service. The Big Object allows tracking rider trips, ratings, and service types efficiently.

**Key Features:**
- Stores millions of records efficiently
- Supports querying using indexed fields
- Can be populated via CSV, Bulk API, or Apex

---

## Big Object Definition

**Object Name:** `Rider_History__b`  
**Label:** Rider History  
**Plural Label:** Rider Histories  
**Deployment Status:** In Development (change to Deployed after creating index)

---

## Custom Fields

| Field Name                  | Data Type   | Field Label                  | Required | Length / Decimal Places |
|------------------------------|------------|-------------------------------|---------|-----------------------|
| Start_Location_Latitude      | Number     | Start Location Latitude       | No      | 7, 4                  |
| Start_Location_Longitude     | Number     | Start Location Longitude      | No      | 7, 4                  |
| Start_Time                   | Date/Time  | Start Time                    | Yes     | -                     |
| End_Time                     | Date/Time  | End Time                      | No      | -                     |
| Service_Type                 | Text       | Service Type                  | No      | 16                    |
| Rider_Account                | Text       | Rider Account                 | Yes     | 16                    |
| Rider_Rating                 | Number     | Rider Rating                  | No      | 2, 1                  |

---

## Big Object Index

**Label:** Rider History Index  
**Name:** Rider_History_Index  

| Index Position | Field               | Direction   |
|----------------|-------------------|------------|
| 1              | Rider_Account__c    | Descending |
| 2              | Start_Time__c       | Descending |

*The index allows efficient queries on rider accounts and trip start times.*

---

## Deployment

1. Navigate to **Setup → Big Objects** in your Salesforce org.
2. Create the `Rider_History__b` object.
3. Add the custom fields listed above.
4. Create the index `Rider_History_Index`.
5. Change deployment status to **Deployed**.

---
## Video Demo 
/videos/Big Object.mp4 ([./videos/Big Object.Mp4](https://github.com/Reyhan786/Trailhead-BigObject-RiderHistory/blob/f07ef7819c325beab2cb08df61d2aada06b7143b/Big%20Object.mp4))



