# Job-Search-Portal-Database

🔍 This project aims to design an integrated database system that supports the digitalization of recruitment processes, from managing job listing information to candidate selection.

## Objectives
1. Assist job seekers with an efficient job search feature, equipped with customizable filters based on their needs.
2. Help companies effectively promote job opportunities to qualified candidates.
3. Manage job-related information such as job descriptions, salaries, and other company offers.
4. Support interview process and selection workflow by providing structured and comprehensive information related to job seekers and job listings.

## Database Design
### 1st Normal Form (1NF)
1. `Company`: Stores information about companies that post job listings.
   - company_id (PK)
   - name_com
   - location
   - email_com
   - password_com
2. `Jobseeker`: Stores personal data and information about job seekers.
   - jobseeker_id (PK)
   - name_js
   - phone_number
   - address
   - email_js
   - password_js
   - education
   - birth_date
3. `Job`: Stores details about job positions offered by companies.
   - job_id (PK)
   - title
   - date
   - type
   - description
   - requirement
   - qualification
   - salary
   - company_id (FK)
   - deadline
4. `Resume`: Stores resume data submitted by job seekers.
   - resume_id (PK)
   - link_file
   - jobseeker_id (FK)
5. `Interview`: Stores date and time information for scheduled interviews.
    - interview_num (PK)
    - job_id (FK)
    - date
    - time
    - jobseeker_id (FK)
6. `Result`: Stores selection results from the company regarding job applications.
    - result_id (PK)
    - jobseeker_id (FK)
    - job_id (FK)
    - status

### 2nd Normal Form (2NF)
1. Company
2. Jobseeker
3. Resume
4. Interview
5. Result
6. Job
   - job_id (PK)
   - title
   - date
   - type
   - description
   - salary
   - company_id (FK)
   - deadline
7. Qualification
   - qualif_id (PK)
   - qualification
8. Requirement
    - req_id (PK)
    - requirement
9. Bridge Job-Qualification
    - job_id (FK)
    - qualif_id (FK)
10. Bridge Job-Requirement
    - job_id (FK)
    - req_id (FK)
11. Bridge Job-Jobseeker
    - job_id (FK)
    - jobseeker_id (FK)

### 3rd Normal Form (3NF)
1. Company
   - company_id (PK)
   - name_com
   - location
   - account_id (FK)
2. Jobseeker
   - jobseeker_id (PK)
   - name_js
   - phone_number
   - address
   - education
   - birth_date
   - account_id (FK)
3. Account
   - account_id (PK)
   - email
   - password
4. Resume
5. Interview
6. Result
7. Job
8. Qualification
9. Requirement
10. Bridge Job-Qualification
11. Bridge Job-Requirement
12. Bridge Job-Jobseeker
