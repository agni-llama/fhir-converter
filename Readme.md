# This is sample code to convert simple json to ABDM compatible FHIR json

## How to install

```
pip install git+https://github.com/agni-llama/fhir-converter   
```


## How to use

```
from fhir_converter import create_fhir_bundle_discharge_summary
input_json = {
    "patient": {
        "patient_id": "1234567890",
        "name": "Aman",  # mandatory
        "gender": "Male",  # mandatory
        "base64_file": "sample text",
        "dob": "sample text",
        "phone": "sample text",
    },
    "section": {
        "chief_complaints": "sample text",
        "physical_examination": "sample text",
        "allergies": None,
        "medical_history": None,
        "family_history": None,
        "investigation_advice": None,
        "medications": None,
        "follow_up": None,
        "procedure": None,
        "referral": None,
        "other_observations": None,
        "document_reference": None,
    },
    "meta": {
        "discharge_date": "2020-07-09T15:32:26.605+05:30",
        "status": "final",  # final | amended | entered-in-error | preliminary
    },
}

fhir_bundle = create_fhir_bundle_discharge_summary(input_json)
print(fhir_bundle)
```
