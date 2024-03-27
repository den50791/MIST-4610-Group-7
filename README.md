# MIST 4610 Project 1

# Team Name
47114 Group 7

## Team Members:
1. Leif Hurdal ([@leifhurdal](https://github.com/leifhurdal))
2. Amy Morales ([@amymorales](https://github.com/amyfrmorales))
3. Dung Nguyen ([@dungnguyen](https://github.com/den50791))
4. Vivian Pham ([@vivianpham](https://github.com/vivianxpham))
5. Ben Williams ([@benwilliams](https://github.com/bendeanwilly))

# Problem Description 

MIST 4610 students created a relational database that described a healthcare clinic business. The clinic provides several services, including Emergency Medical Care, Diagnostic Services, urgent care, and prescription services. The Clinic needed to capture information about each patient, the facilities, billing information, appointments, providers, equipment, and maintenance history of the equipment. The goal is to maintain relevant data on patients that is important for healthcare providers and to efficiently track queues for appointment making. 

## Data Model

<img width="605" alt="Screenshot 2024-03-26 at 11 25 08 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/01ac4072-20ec-43d6-8001-dff6af3b4870">

Explanation of data model:

Our data model seeks to organize the above-described emergency clinic. The core of the model is the Appointment entity, which is the instance in which a Patient meets with a Healthcare Provider. The Appointment entity includes information about where and when the Appointment takes place. Five relational branches stem from an appointment.

The first branch that comes from the Appointment is Patient. Each Patient can book many Appointments over the course of their life, hence the one-to-many relationship between them. As the name suggests, the Patient table includes critical information about each Patient, including a Unique Identifying ID, Name, Number, Gender, and Date of Birth.
The Patient table itself has two additional relationships with other entities. Each Patient will have a unique Medical History associated with him/her (one-to-one relationship). This history will include Immunization, Medical Conditions, Medications, etc. The other branch for Patient is Prescription. At the clinic, each Patient can receive many Prescriptions (one-to-many relationship). 

Additionally, each Prescription comprises many Medications, and many different Prescriptions will use the same kind of Medication. Prescription and Medication are joined using the associative entity of Prescription Order. Prescription includes information on the Name, Frequency, and Issue Date of the Prescription. Medication consists of the Name, Type, and Description of the medication. PrescriptionOrder includes the amount and refills of each Medication.

The second branch, which comes from Appointment, is Healthcare Provider. Similarly to the previous relationship, one Healthcare Provider will have many Appointments over their career (helping Patients), leading to another one-to-many relationship. The Healthcare Provider table provides information on them such as Name, Specialization, Schedule, etc.

The third branch is Billing. At the end of each Appointment there will be one bill to pay, hence the one-to-one relationship between Billing and Appointment. The Billing table has information to keep track of the payment such as Date, Amount, etc.

The fourth Branch is Appointment Type. Each Appointment - of the many Appointments that take place - will be classified by an Appointment Type. This relationship will mean there is a one Appointment Type that classifies many Appointments (one-to-many relationship). Having a categorization for Appointments will provide additional organization for the clinic. The Appointment Type entity includes the appointment type Name, Detail and Service Hours.

The fifth and final branch off of Appointment is Diagnostic Tests. During an Appointment there can be many Diagnostic Tests facilitated by a Healthcare Provider. This means there is a one-to-many relationship between them. The Diagnostic Test table includes information such as the name of the test, the description of it, and the result.
	
Each Diagnostic Test requires many pieces of Equipment can be used and each piece of Equipment can be used in many different kinds of Diagnostic Tests. These two are connected by the associative table of EquipmentUsed which includes the condition and quantity of the Equipment. The Equipment table stores the Name, Type, Condition, and Maintenance History.
   
## Data Dictionary 

<img width="630" alt="Screenshot 2024-03-26 at 10 47 47 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/9008600e-091e-4a43-bc48-4f1b6d499ceb">

<img width="641" alt="Screenshot 2024-03-26 at 10 48 06 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/2f12beaf-7194-45c3-9ed9-91c37b674498">

<img width="642" alt="Screenshot 2024-03-26 at 10 49 00 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/6986ba92-7559-48c7-ab04-6803ea11b487">

<img width="651" alt="Screenshot 2024-03-26 at 10 49 16 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/9e5298ab-6b7b-402d-8fe1-9f21dd2e7ff7">

<img width="632" alt="Screenshot 2024-03-26 at 10 49 23 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/6543a35e-e443-4f9b-bc5f-dd5ec2dd25f2">

<img width="651" alt="Screenshot 2024-03-26 at 10 49 29 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/58ec452e-a876-4b2e-9c30-1c134c7969f0">

<img width="639" alt="Screenshot 2024-03-26 at 10 49 40 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/72d417f5-099e-4912-9b32-c36c9586e6e6">

<img width="645" alt="Screenshot 2024-03-26 at 10 49 46 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/04049f89-2624-42c4-96dc-e37ba415967e">

<img width="632" alt="Screenshot 2024-03-26 at 10 49 56 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/3118b854-530e-45a4-a497-549ef6f4f14c">

<img width="656" alt="Screenshot 2024-03-26 at 10 50 09 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/933b4616-4a9d-427a-a02d-942effb919d7">

<img width="649" alt="Screenshot 2024-03-26 at 10 50 17 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/93069453-084a-49d1-8b17-09f02d82eb63">

<img width="677" alt="Screenshot 2024-03-26 at 10 50 24 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/26ef5ecc-373d-40ce-9870-8669d9f83a38">


## Queries

<img width="618" alt="Screenshot 2024-03-26 at 11 29 11 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/7f07582f-f4fb-48a1-b888-9b1bc5e061da">
<img width="618" alt="Screenshot 2024-03-26 at 11 15 56 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/bf50df3d-f4f1-44f3-8a31-8b9e38685e15">

<img width="527" alt="Screenshot 2024-03-26 at 10 20 27 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/48b0a5db-5199-4ac6-8bc4-920f86d27ea8">

Justification: By gaining insights into the gender distribution of their patients, the manager of the clinic can gain valuable information to optimize services, and provide data for research and health patterns.

<img width="625" alt="Screenshot 2024-03-26 at 10 21 06 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/4ac07136-681d-475e-a118-5354d6dcb97a">

Justification: The manager will be able to look into the specifics of the bills greater than the average bill amount to determine what charges are increasing revenue for the clinic.

<img width="620" alt="Screenshot 2024-03-26 at 10 21 36 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/3540896a-a651-4f8d-89eb-f29f9491b254">

Justification: Managers will be able to prepare financial audits to determine which type of appointment generates the most revenue for the clinic.

<img width="626" alt="Screenshot 2024-03-26 at 10 22 19 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/c203eae4-6641-49fa-acb9-de9b99d263ce">

Justification: Managers can utilize the list of provider’s name and specializations to effectively match a patient’s needs to an accredited doctor who is the VP within their credentials to ensure appropriate treatment.

<img width="625" alt="Screenshot 2024-03-26 at 10 23 00 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/e3423505-405f-462a-8f56-e3d6ea81fe39">

Justification: The manager will be able to track the revenue generated by the clinic and identify trends or peak billing periods. The manager will be able to use this data and formulate decisions to optimize revenue in the future and contribute to the overall performance of the clinic.

<img width="536" alt="Screenshot 2024-03-26 at 10 36 52 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/7bddea92-5287-4284-9c27-eb3c456b2665">

Justification: A manager will be able to facilitate appointments and scheduling concerns in order to optimize healthcare provider availability when scheduling appointments. The manager can have a general overview of what staff is ON or OFF duty. 

<img width="608" alt="Screenshot 2024-03-26 at 10 37 39 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/b9f5e5f8-d345-4e63-857b-edc92bddd9f2">

Justification: The manager will gain valuable information to the frequently prescribed medication in which the manager and healthcare providers can identify patterns and diagnose their patients properly. In terms of medication management, the manager can allocate the resources effectively when managing inventory.

<img width="559" alt="Screenshot 2024-03-26 at 11 38 42 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/53f165e6-0da9-49e9-ab09-b900699b8b47">

Justification: In this query, the manager recognizes a pattern of people searching for young, experienced annual check-up providers. This led to a need for REGEXP to limit results based on specific providerID patterns of smaller ID numbers and a COUNT(*) function that captures providers with multiple past experiences. 

<img width="604" alt="Screenshot 2024-03-26 at 10 38 34 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/8a2ad2a7-fbfe-40fb-a2c0-c29a1c59815c">

Justification: A manager will be able to populate data that focuses on specific types of medications and focus on treatment towards that. Medication management will be a priority for the Manager as well as providing valuable data to improve the clinic’s overall quality.

<img width="596" alt="Screenshot 2024-03-26 at 10 38 58 PM" src="https://github.com/den50791/MIST-4610-Group-7/assets/163002845/0b21e25e-95ec-4707-a0e4-decaab21b477">

Justification: The manager will be able to assess which patients do not have appointments to then plan on ways to, of course, prioritize the patients healthcare needs and then optimize clinic resources, maximize revenue, provide proper quality healthcare services. 

## Database Information
Name of the database: ns_Sp24_47114_Group7

