# Brief App Description:

This Streamlit-made CSV validator checks regular file with employee insurance coverage info on a bunch of inconsistencies:

- if headers in the file are duplicated
- if there are blank headers
- if there are empty values in the columns that must not contain empty values
- if all the dependents are tied to their employee
- if date_of_birth column contains invalid values
- if SSN = Member ID (which is not allowed by the US PHI norms)
- if coverage expiration date < coverage effective date

All of these checks automated by matching headers from the original CSV (using *rapidfuzz* module) with the number of typical headers from the database

If some of the headers from the current CSV have not been matched due to their uniqueness, it's possible to rename them in **"Matched Headers"** section, so that they could be matched without correcting current CSV manually

---

In the section **"Try Sample Files"** you can find two downloadable CSVs which have been populated with fake data:

- The first one (***Messed-Up File***) holds number of inconsistencies so that one could see how each of the checks in this validator works 
- The second one (***Corrected File***) is totally correct file which shows how validator works when there are no issues with the file
