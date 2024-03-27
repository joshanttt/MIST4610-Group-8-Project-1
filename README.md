# MIST4610-Group-8-Project-1
Problem Description
As a group, we were tasked with building a relational database for the various entities within an emergency health-care clinic. At the clinic, patients can receive various types of medical services and are treated by professionals. Our model aims to visual portray the relationships present between the various entities of a health-care clinic. Our goal is to populate sample data and possible queries that may serve as an asset to the clinic, helping to store and analyze needed data. Our hope is that the model will improve day-to-day functions and overall efficiency for the clinic.

Data Model:
Data Model Description:

Our data model is based on the services of a health-care clinic. First off, our clinic services patients, within this entity, patients are identified by a unique patient id. In addition, other attributes about patients include, patient name, date of birth, gender, contact information and medical history. Meds are available at this clinic, identified by their medID. As there are many patients seen at the clinic, many meds are available as well, the entities Patients and Meds share a many-to-many relationship with their associative entity being Prescriptions. Prescriptions capture the relationship of which patients are prescribed which medications. Each patient can have multiple prescriptions and each medication can be prescribed to multiple patients. Prescriptions are identified by PrescripID.

The MedStaff table shares a one to many relationship with the Prescriptions table. This means that Medical Staff members can write many different prescriptions, but each prescription is only written by one staff member. The MedStaff table is composed of medStaffID, serving as the unique identifier, followed by attributes: name, position, and contact. Position being the title they hold (Doctor, NP, Nurse, CRNA). In addition, MedStaff shares a many-to-many relationship with Patients, their associative entity being Appointments. Appointments capture the relationship of which patients are seen by which medical staff at specific times. Each patient can have multiple appointments with different medical staff members and each medical staff member can have multiple appointments with different patients. The Appointments table is identified by a specific apptID, unique to each individual appointment. The entity MedRecord is used to record medical information from an appointment and shares a one-to-one relationship with appointments, meaning that there is one medical record associated with each appointment. The Billing table also shares a one-to-one relationship with Appointments meaning for each appointment, there is one bill. Billing also shares a many-to-many relationship with Insurance, with the associative entity being InsuranceBilled. InsuranceBilled captures the relationship of which billing entries are associated with which insurance policies. This relationship demonstrates that each billing entry can be associated with multiple insurance policies and each insurance policy can be associated with multiple billing entries.

The entity, Insurance, is used to record insurances accepted by the clinic, table is identified by a unique providerID which is the specific insurance provider code. Insurance shares a many-to-many relationship with Patient, the associative entity being InsurancetType. The associative entity Insurance Type captures the relationship of which patients are associated with what insurance policies and the specific type of insurance for each patient. The relationship shows that each patient can have different insurance policies, and each insurance provider can offer many different insurance plans/options. Lastly is the Service table, used to define the type of service performed at an appointment. Service shares a many-to-many relationship with appointments, connected through the associative entity, AssignedService. AssignedService defines the relationship between which service is being performed at a specific appointment. Assigned service is identified by a unique assignmentID. Overall, this relationship demonstrates that for each appointment many services are available to perform, and many services can be assigned to appointments.

![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/5115cb93-65e1-465e-82f6-fa38a5497c05)


Data Dictionary:
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/08b13668-cedd-43fb-a979-348f5d051b8e)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/36d84be5-c41c-4624-bce3-9887ab77d6a1)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/cdcc3260-c64b-4bd4-a48b-fa5479950a54)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/eba3df90-95b5-433f-a0da-fc5e6d41e267)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/31fbf1e8-a20c-465e-ac5d-c788019b8562)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/e599dfc2-05af-4cfb-907d-01f1da0c72c9)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/0246ccd7-d4cf-4bb6-81f3-ff0abce2c764)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/176c0a25-0e04-4642-a03a-09a0fb45f69c)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/f74becc8-fff1-4d68-8126-1d137d38758a)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/4df145da-f281-464d-a2b6-d0bfa04a66b3)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/6132902a-dcbe-40a8-98f4-329eb01aee23)
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/55cd56fb-649c-4367-9791-9eeecdc843f0)


Queries:
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/ff41f09b-9ca1-47d3-8efa-0b71a6830d37)

Query 1 lists the ID's and names of Medical Staff who have treated more than 2 patients.![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/6dccd67f-0789-4f74-82f0-f1e5425f8833)

Explain: This query allows the clinic to decipher which medical staff have serviced more than 2 patients, informing them on how many patients each member of the medical staff are attending to over a period of time. Being able to track medical staff and how many patients they are seeing is essential in an emergency health clinic for organizational and efficiency purposes.

Query 2 lists the top 10 most frequently used medications by their names and the number of patients currently taking the medicine in descending order
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/86d2cd38-21d7-4bac-b59e-51b22024340f)


Explain: This query generates the number of patients currently using one of the top 10 medications provided by the clinic. Identifying the most used medications can help the clinic track which medications they may need to order soon or on a more frequent basis.

Query 3 lists the names of patients with a balance due on their account and the amount due. ![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/35fd454f-ada5-48af-b8d2-d494bf340610)

Explain: This query generates the names of patients who have an "unpaid" status listed on their account and the amount they owe. This information is important because it notifies the clinic of which patients they need to contact about paying outstanding bills. It is also important for insurance purposes, as many patients may use co-pay or may change insurances and be unaware that certain charges may not be covered based on their plans. Lastly, if bills are not eventually paid, the clinic will need this information to report the outstanding bill to collections.

Query 4 lists the names of medical staff who are doctors ![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/970dd96b-9b70-4a1c-b9e5-308608d280a4)

Explain: For an emergency health clinic, it's crucial to quickly identify which doctors are available to provide immediate care. Knowing the names and availability of all doctors enables clinic staff to respond promptly to emergency situations.

Query 5 lists the average deductible of female patients whose insurance plan type begins with T ![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/38b90d0c-fd12-45ce-aa1f-9a640292f7cf)

Explain: The health clinic might need to use this query to assess the financial burden on female patients with specific insurance plans. Understanding the average deductible for a certain demographic can aid in financial planning, resource allocation, and more to ensure fair access to healthcare services for female patients with particular insurance plans. Such insights can inform decision-making processes aimed at enhancing the overall patient experience and ensuring that healthcare remains accessible and affordable for all.

Query 6 lists the medicine name and the percentage of patients who are taking a med with a dosage less than 100mg ![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/d22af6b0-a712-4c15-bbdb-4cba922fd2de)

Explain: Understanding which medications patients are using allows the clinic to monitor the effectiveness of treatments. If a significant percentage of patients are taking a particular medication but not showing improvement, it may indicate that the treatment protocol needs adjustment.

Query 7 lists the patient name and their amount of insurance billed that is greater than the average amount of insurance billed to all patients.
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/1e9d7e70-8d5f-4e19-8021-da8b680c1015)


Explain: The health clinic may want to know the patients who have paid more than the average for all patients can help ensure quality care and identify bill errors or fraud. Being able to identify patients who pay more than the average amount allows the health clinic to conduct quality checks with surveys to ask the patients if they are satisfied with the service and bill they were provided. Also, this allows the health clinic to check for any potential fraud errors to discover the reason why these patients are being billed more than average

Query 8 lists the number of appointments attended by patients under each insurance provider. ![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/c762e3c5-2887-4492-8da4-26f171ee67d0)

Explain: Health clinics may want to know the number of appointments attended by patients based on insurance providers to determine which insurance providers are best and which ones may be the worst. Many appointments with the same provider may imply that that specific insurance provider may be best for patients because they offer a good plan for patients, are affordable, and show care for their customers. Meanwhile, providers with not many appointments may imply those providers don’t have good plans for patients, making it difficult for patients to make appointments.

Query 9 lists the insurance plan type and average deductable amount for each insurance plan. ![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/87be1699-d01f-4a13-872f-0865f84d9e4c)

Explain: Being able to know the average deductible for each insurance plan type, the health clinic may help patients avoid potential barriers and conflicts due to their insurance plan. The clinic could look ahead to see the insurance the patients have and create the most affordable plan for the treatment they will receive. This information will also help the financial planning aspect of the clinic so they will be prepared for the amount that patients will be paying after insurance. It will also allow for the health clinic to provide insurance insight on which plan type the patient should choose that will be most beneficial for their treatments and medications.

Query 10 lists the name of patients and the date of the appointment for those who are receiving a type of drainage service.
![image](https://github.com/joshanttt/MIST4610-Group-8-Project-1/assets/163002960/8129f617-e13d-4cb3-bdc6-87b843ad8b32)


Explain: The health clinic may want to know the names and date of their patients appointments to ensure they are arriving on time and on the correct date. This would also ensure that there is enough staff on that day and that each patient is receiving the correct service, which in this case is a drainage service. Having access to this information also allows for staff specializing in a type of drainage service to know what days they have to go into the health clinic and who they are operating this service on.

Database Information:
Name of the database: ns_Sp24_47114_Group8

Additional Information:
