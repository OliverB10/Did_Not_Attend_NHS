### Patient Attendance in the NHS
Every year the National Health Service (NHS) in the UK books around 122 million appointments with patients covering an expansive list of health conditions, outpatient check-ups and routine appointments. 
From the 122 million, around 6.4% of appointments were missed with a cost of £216 million to the NHS, and the figures show that each missed appointment can cost between £30 - £150 to the provider. The NHS definition of a Did Not Attend (DNA) is where a patient “does not turn up for the appointment and does not contact the surgery with enough time in advance to cancel/change appointment”. 
A large number of factors are said to affect patients who didn’t attend appointments, including income, ethnicity, sex, and access to transport. 


# Table of Content
1. [ Data ](#data)
2. [ Basic Data Information ](#Information)
3. [ Data Cleansing ](#Cleansing)
4. [ Exploratory Data Analysis ](#Analysis)
5. [ Creating a Model for Appointments DNACode ](#model)

## 1. Data
The dataset is from the NHS Trusts patient record system and has been anonymized however for data protection purposes I won't share it. 
However the headings are standard across all Hospitals and are shown below 

![Data Info](https://raw.githubusercontent.com/OliverB10/Did_Not_Attend_NHS/77808fccfa3bbbfafb52aa80a6d70f85187f304d/Column%20Info.jpg)

The dataframe is composed of 1,048,575 medical appointments and 17 features

# Data Dictionary 
														
* PatientID: patient unique ID
* FirstAttendanceCode: Is it a first appointment or a follow up.
* AppointmentTime: When the appointment takes place.
* TreatmentFunctionCode: Code for the treatment type.
* ReportingMainSpecCode: Code for Specialisation.
* AgeOnAppointment: Age of the patient.
* DNACode: Shows if the patient attended the appointment 
* DateAppointmentBooked: Date when the patient booked an appointment
* AppointmentType: What is the appointment regarding and is it New/Follow-up
* IMDDecile: Deprivation index. 
* EthnicCategoryCode: What Ethnicity is the the patient.
* LocalAuthorityName: What is the local authority of the patient.
* SiteCode: Site code for the Clinic/Hospital
* SiteCategory: Which site did they attend?
* ResourceCode: Code for the resource
* ConsultantCode: Code for the Consultants
* InternalAppointmentSK: Skew for the Appointment
* ProcedureRecorded: Was the procedure recorded?


# 2. Basic Data Information

**Null/Missing Values **
Null data analysis of the data shows that there are about 45,000 missing records across 5 different columns. 
<img src="[images/example.png](https://github.com/user-attachments/assets/534d59ea-6f18-4b73-b585-3d70b7fc88d5)" width="100" height="200" />
#![image](https://github.com/user-attachments/assets/534d59ea-6f18-4b73-b585-3d70b7fc88d5)

This contributes a very small amount of data when compared with the more than 1 million records provided and it would be easier to remove them from the data set than fill these values with a statistical process. 
Following the removal of the missing data, the data size is 1,022,807.


**Data Information**
The table below shows basic information about the data.

![image](https://github.com/user-attachments/assets/eb95afe1-7874-44cd-ab20-910d23bb2322)

The table shows the Means for the numerical values. Average AgeOnAppointment is 5 (4.96) and 4 (4.4) for DNACode and 4.7 for IMDDecile.
ConsultantCode has a negative value for for it's mean which is something that I'll look at later. 


**Charts Analysis**

First chart shows the **IMDDecile against DNACode**, however I only want to focus on the DNACode of 3 and 7 which are the no-show results. 
The scale goes from 1 - 10, with 1 show patients in the poorest areas and 10 in the most affluent.

![image](https://github.com/user-attachments/assets/66e9c7d4-eb51-4de6-926d-0e14d8da7037)

The higest IMDDecile counts are in 1 - 4, which was expected. 

Second chart shows **First Attendance counts against DNACode**, which are explained below:
Code	Description
1	First attendance face to face
2	Follow-up attendance face to face
3	First telephone or Telemedicine consultation
4	Follow-up telephone or Telemedicine consultation

![image](https://github.com/user-attachments/assets/c7c27ac4-b1e2-4388-9dd3-2bd858afc59f)

The data shows that 1 and 2 are have the higest no-shows.

Third chart shows looks at AgeOnAppointment against DNACode of 3 and 7 as before. 

![image](https://github.com/user-attachments/assets/a6ca6a10-9c19-4566-8be6-4e20c9f6c405)

Interestingly the highest count is in the 0 category, which will be new borns and infants, something to consider later.
Generaly the distribution is inkeeping with what I expected, younger people tend to miss their appointments while older populations go to their appointments.













