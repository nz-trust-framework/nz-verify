# NZ Verify (Production) - Verifier Templates

## Verifier Templates
NZ Verify is currently configured to support verification of mobile driver licences and data attributes associated with that namespace (org.iso.18013.5.1). These are detailed below:

**Age Verification (18+)**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  portrait
-  age_over_18
```

**Age Verification (Date of Birth)**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  portrait
-  birth_date
```

**Driver Licence**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  sex
-  portrait
-  birth_date
-  given_name
-  family_name
-  issue_date
-  expiry_date
-  issuing_authority
-  issuing_country
-  document_number
-  administrative_number
-  driving_privileges
```

**Proof of ID (Basic)**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  portrait
-  given_name
-  family_name
```

**Proof of ID (Customer Due Diligence)**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  portrait
-  birth_date
-  given_name
-  family_name
-  resident_address
-  resident_city
-  resident_state
-  restident_postal_code
-  resident_country
-  signature_usual_mark
```
