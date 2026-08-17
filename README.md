## Main idea of the project

Working in the US healthcare company, my primary goal is to <ins>implement client's file with its employees' info into our system</ins>.  
  
As those files we typically receive may be messy from time to time, we need to validate them manually in Google Sheets. However,  
this process may be complicated and time consuming. When the file we are working with is large enough, it's also not a big deal  
to **miss some inconsistency** and load inappropriate or invalid info into the app.  

> This checker automates the verification process for bigger part of the files, making it easier to spot the invalid info and reach\
back to the client for the clarification

## Brief App Description:

This Streamlit-made CSV validator checks regular file with employee insurance coverage info on a bunch of inconsistencies:

- if headers in the file are duplicated
- if there are blank headers
- if there are empty values in the columns that must not contain empty values
- if all the dependents are tied to their employee
- if date_of_birth column contains invalid values
- if SSN = Member ID (which is not allowed by the US PHI norms)
- if coverage expiration date < coverage effective date

All of these checks automated by matching headers from the original CSV (using *rapidfuzz* module) with the number of typical headers from our SQL database

If some of the headers from the current CSV have not been matched due to their uniqueness, it's possible to rename them in **"Matched Headers"** section, so that they could be matched without correcting current CSV manually

---

In the section **"Try Sample Files"** you can find two downloadable CSVs which have been populated with fake data:

- The first one (***Messed-Up File***) holds number of inconsistencies so that one could see how each of the checks in this validator works 
- The second one (***Corrected File***) is totally correct file which shows how validator works when there are no issues with the file
