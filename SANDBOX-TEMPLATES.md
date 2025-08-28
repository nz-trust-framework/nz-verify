# NZ Verify (Sandbox) - Verifier Templates

## Verifier Templates
NZ Verify (Sandbox) is currently configured to support a number of test credentials across various namespaces. These are detailed below:

> [!WARNING]
> The verifier templates below are pending an update in the app. This is expected in the coming days.

**Age 18+ (Mobile Driver Licence)**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  portrait
-  age_over_18
```

**Age 18+ (Photo ID)**
```
docType:    org.iso.23220.photoID.1
namespace:  org.iso.23220.photoID.1
-  portrait
-  age_over_18
```

**Driver Licence**
```
docType:    org.iso.18013.5.1.mDL
namespace:  org.iso.18013.5.1
-  portrait
-  birth_date
-  given_name
-  family_name
-  issue_date
-  expiry_date
-  issuing_authority
-  document_number
-  administrative_number
-  driving_privileges
-  signature_usual_mark

namespace: nz.govt.dia.driverlicence.test.1
- driving_privileges
- conditions
- exemption
- donor_status
```

**Photo ID**
```
docType:    org.iso.23220.photoID.1
namespace:  org.iso.23220.photoID.1
-  portrait
-  given_name_latin1
-  family_name_latin1
-  birth_date
-  expiry_date
-  issuing_authority_unicode
-  document_number
```

**Verified Bank Account**
```
docType:    nz.govt.dia.bankaccount.test.1
namespace:  nz.govt.dia.bankaccount.test.1
-  account_number
-  currency
-  account_name
-  residential_address
-  issuer
-  issue_date
-  expiry_date
```
