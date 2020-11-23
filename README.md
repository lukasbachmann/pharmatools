# PharmaTools
Contains functions to interact with ClinicalTrials.gov and PubMed APIs

Please set environment variables PUBMED_API_KEY and PUBMED_EMAIL before using the PubMed functions.

## Example use case
### ClinicalTrials.gov API
```python
from pharmatools.clinical_trials import get_trial_data

drug = "rivaroxaban"
indication = "pulmonary embolism"
date_latest = "2018-01-01"
get_trial_data(drug, indication, date_latest)

{'n_trials': 118,
 'status': {'Not yet recruiting': 8,
  'Recruiting': 24,
  'Enrolling by invitation': 1,     
  'Active, not recruiting': 9,      
  'Suspended': 1,
  'Terminated': 4,
  'Completed': 57,
  'Withdrawn': 2,
  'Unknown status': 12},
 'organizers': {'FED': 0,
  'INDIV': 0,
  'INDUSTRY': 44,
  'NETWORK': 0,
  'NIH': 0,
  'OTHER': 72,
  'OTHER_GOV': 2},
 'phases': {'Early Phase 1': 0,
  'Not Applicable': 10,
  'Phase 1': 1,
  'Phase 2': 15,
  'Phase 3': 41,
  'Phase 4': 14}}
```

### PubMed API
```python
from pharmatools.pubmed import get_pubmed_data

get_pubmed_data("remdesevir", "covid-19", datetime.datetime(2020, 5, 17))
```
returns a tuple: a string with all the matching abstracts and the number of search results
