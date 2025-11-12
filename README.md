### Brief App Description:

This Streamlit-made CSV validator checks regular file with employees' insurance coverage info on a bunch of inconsistencies

The core idea is to match headers from the original CSV (using *rapidfuzz* module) with the number of typical headers from the historical CSVs so that all the checks could be automated

If some of the headers from the current CSV have not been matched due to their uniqueness, it's possible to rename them in **"Matched Headers"** section, so that they could be matched without correcting current CSV manually

In the section **"Try Sample Files"** you can find two downloadable CSVs which have been populated with fake data:

- The first one (***Messed-Up File***) holds number of inconsistencies so that one could see how each of the checks in this validator works 
- The second one (***Corrected File***) is totally correct file which shows how validator works when there are no issues with the file
