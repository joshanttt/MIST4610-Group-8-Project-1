# MIST4610-Group-8-Project-1
Problem Description
As a group, we were tasked with building a relational database for the various entities within an emergency health-care clinic. At the clinic, patients can receive various types of medical services and are treated by professionals. Our model aims to visual portray the relationships present between the various entities of a health-care clinic. Our goal is to populate sample data and possible queries that may serve as an asset to the clinic, helping to store and analyze needed data. Our hope is that the model will improve day-to-day functions and overall efficiency for the clinic.

Data Model:
Data Model Description:

Our data model is based on the services of a health-care clinic. First off, our clinic services patients, within this entity, patients are identified by a unique patient id. In addition, other attributes about patients include, patient name, date of birth, gender, contact information and medical history. Meds are available at this clinic, identified by their medID. As there are many patients seen at the clinic, many meds are available as well, the entities Patients and Meds share a many-to-many relationship with their associative entity being Prescriptions. Prescriptions capture the relationship of which patients are prescribed which medications. Each patient can have multiple prescriptions and each medication can be prescribed to multiple patients. Prescriptions are identified by PrescripID.

The MedStaff table shares a one to many relationship with the Prescriptions table. This means that Medical Staff members can write many different prescriptions, but each prescription is only written by one staff member. The MedStaff table is composed of medStaffID, serving as the unique identifier, followed by attributes: name, position, and contact. Position being the title they hold (Doctor, NP, Nurse, CRNA). In addition, MedStaff shares a many-to-many relationship with Patients, their associative entity being Appointments. Appointments capture the relationship of which patients are seen by which medical staff at specific times. Each patient can have multiple appointments with different medical staff members and each medical staff member can have multiple appointments with different patients. The Appointments table is identified by a specific apptID, unique to each individual appointment. The entity MedRecord is used to record medical information from an appointment and shares a one-to-one relationship with appointments, meaning that there is one medical record associated with each appointment. The Billing table also shares a one-to-one relationship with Appointments meaning for each appointment, there is one bill. Billing also shares a many-to-many relationship with Insurance, with the associative entity being InsuranceBilled. InsuranceBilled captures the relationship of which billing entries are associated with which insurance policies. This relationship demonstrates that each billing entry can be associated with multiple insurance policies and each insurance policy can be associated with multiple billing entries.

The entity, Insurance, is used to record insurances accepted by the clinic, table is identified by a unique providerID which is the specific insurance provider code. Insurance shares a many-to-many relationship with Patient, the associative entity being InsurancetType. The associative entity Insurance Type captures the relationship of which patients are associated with what insurance policies and the specific type of insurance for each patient. The relationship shows that each patient can have different insurance policies, and each insurance provider can offer many different insurance plans/options. Lastly is the Service table, used to define the type of service performed at an appointment. Service shares a many-to-many relationship with appointments, connected through the associative entity, AssignedService. AssignedService defines the relationship between which service is being performed at a specific appointment. Assigned service is identified by a unique assignmentID. Overall, this relationship demonstrates that for each appointment many services are available to perform, and many services can be assigned to appointments.

image

Data Dictionary:
Screenshot 2024-03-27 at 10 13 38 AM Screenshot 2024-03-27 at 10 13 58 AM Screenshot 2024-03-27 at 10 14 18 AM Screenshot 2024-03-27 at 10 14 40 AM Screenshot 2024-03-27 at 10 14 56 AM Screenshot 2024-03-27 at 10 15 21 AM Screenshot 2024-03-27 at 10 15 36 AM Screenshot 2024-03-27 at 10 16 02 AM Screenshot 2024-03-27 at 10 17 59 AM Screenshot 2024-03-27 at 10 18 15 AM Screenshot 2024-03-27 at 10 18 28 AM Screenshot 2024-03-27 at 10 18 40 AM
Queries:
Screenshot 2024-03-27 at 10 12 05 AM
Query 1 lists the ID's and names of Medical Staff who have treated more than 2 patients. image
Explain: This query allows the clinic to decipher which medical staff have serviced more than 2 patients, informing them on how many patients each member of the medical staff are attending to over a period of time. Being able to track medical staff and how many patients they are seeing is essential in an emergency health clinic for organizational and efficiency purposes.

Query 2 lists the top 10 most frequently used medications by their names and the number of patients currently taking the medicine in descending order
image

Explain: This query generates the number of patients currently using one of the top 10 medications provided by the clinic. Identifying the most used medications can help the clinic track which medications they may need to order soon or on a more frequent basis.

Query 3 lists the names of patients with a balance due on their account and the amount due. image
Explain: This query generates the names of patients who have an "unpaid" status listed on their account and the amount they owe. This information is important because it notifies the clinic of which patients they need to contact about paying outstanding bills. It is also important for insurance purposes, as many patients may use co-pay or may change insurances and be unaware that certain charges may not be covered based on their plans. Lastly, if bills are not eventually paid, the clinic will need this information to report the outstanding bill to collections.

Query 4 lists the names of medical staff who are doctors image
Explain: For an emergency health clinic, it's crucial to quickly identify which doctors are available to provide immediate care. Knowing the names and availability of all doctors enables clinic staff to respond promptly to emergency situations.

Query 5 lists the average deductible of female patients whose insurance plan type begins with T image
Explain: The health clinic might need to use this query to assess the financial burden on female patients with specific insurance plans. Understanding the average deductible for a certain demographic can aid in financial planning, resource allocation, and more to ensure fair access to healthcare services for female patients with particular insurance plans. Such insights can inform decision-making processes aimed at enhancing the overall patient experience and ensuring that healthcare remains accessible and affordable for all.

Query 6 lists the medicine name and the percentage of patients who are taking a med with a dosage less than 100mg image
Explain: Understanding which medications patients are using allows the clinic to monitor the effectiveness of treatments. If a significant percentage of patients are taking a particular medication but not showing improvement, it may indicate that the treatment protocol needs adjustment.

Query 7 lists the patient name and their amount of insurance billed that is greater than the average amount of insurance billed to all patients.
image

Explain: The health clinic may want to know the patients who have paid more than the average for all patients can help ensure quality care and identify bill errors or fraud. Being able to identify patients who pay more than the average amount allows the health clinic to conduct quality checks with surveys to ask the patients if they are satisfied with the service and bill they were provided. Also, this allows the health clinic to check for any potential fraud errors to discover the reason why these patients are being billed more than average

Query 8 lists the number of appointments attended by patients under each insurance provider. image
Explain: Health clinics may want to know the number of appointments attended by patients based on insurance providers to determine which insurance providers are best and which ones may be the worst. Many appointments with the same provider may imply that that specific insurance provider may be best for patients because they offer a good plan for patients, are affordable, and show care for their customers. Meanwhile, providers with not many appointments may imply those providers don’t have good plans for patients, making it difficult for patients to make appointments.

Query 9 lists the insurance plan type and average deductable amount for each insurance plan. image
Explain: Being able to know the average deductible for each insurance plan type, the health clinic may help patients avoid potential barriers and conflicts due to their insurance plan. The clinic could look ahead to see the insurance the patients have and create the most affordable plan for the treatment they will receive. This information will also help the financial planning aspect of the clinic so they will be prepared for the amount that patients will be paying after insurance. It will also allow for the health clinic to provide insurance insight on which plan type the patient should choose that will be most beneficial for their treatments and medications.

Query 10 lists the name of patients and the date of the appointment for those who are receiving a type of drainage service.
image

Explain: The health clinic may want to know the names and date of their patients appointments to ensure they are arriving on time and on the correct date. This would also ensure that there is enough staff on that day and that each patient is receiving the correct service, which in this case is a drainage service. Having access to this information also allows for staff specializing in a type of drainage service to know what days they have to go into the health clinic and who they are operating this service on.

Database Information:
Name of the database: ns_Sp24_47114_Group8

Additional Information:
