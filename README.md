# Job-Search-Portal-Database

🔍 This project ...

## Objectives

## Entities
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
   - age
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
