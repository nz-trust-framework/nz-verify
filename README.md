# NZ Verify / Whakatūturu

![NZ Verify / Whakatūturu](https://www.dia.govt.nz/vwluResources/NZ-Verify-Brand-image-white-2/$file/NZ-Verify-Brand-image-white-2.png)

**Developer and Technical Support for the NZ Verify app**

NZ Verify/Whakatūturu App supports the verification of select international digital credentials issued by trusted authorities – including mobile driver licences. This allows organisations like rental car companies and government agencies to verify eligible credentials in person with ease and accuracy, supporting a secure and seamless experience for individuals and organisations alike. Available now on the Apple App Store and the Google Play Store.

*  [Download on the Apple App Store](https://apps.apple.com/nz/app/nz-verify-whakat%C5%ABturu/id6743457606)
*  [Get it on Google Play](https://play.google.com/store/apps/details?id=nz.govt.nzverify)

For support and enquiries, please email [nzverifyapp@dia.govt.nz](mailto:nzverifyapp@dia.govt.nz)

## Contents
-  Technical overview
-  Adding support for credentials
-  Technical guidance for issuers and wallets
-  Future functionality

## Technical overview
This guidance outlines technical and structural requirements for developers issuing credentials to be used with the NZ Verify app.

NZ Verify accepts only verifiable credentials conforming to [ISO/IEC 18013-5](https://www.iso.org/standard/69084.html), the international standard for mobile driving licences (mDLs), and [ISO/IEC 23220](https://www.iso.org/standard/86782.html), the internation standard for mobile documents (mDocs), ensuring privacy-preserving and interoperable credential presentations.

Credential issuers must issue credentials, and users must hold and present credentials in apps, that support these standards to ensure successful verification within NZ Verify.

### Device Engagement & Presentation Modes
In accordance with ISO/IEC 18013-5 (sections referred below) and ISO/IEC 23220-4, NZ Verify supports the following flows:
-	**Device engagement** (6.3.2.3) is provided via QR code (8.2.2.3) or NFC (8.2.2.1).
    -	NFC is currently only supported on the Android version of NZ Verify. We expect to support the Apple iOS version in the future.
-	**Device retrieval** (6.3.2.5) is provided via Bluetooth Low Energy (8.3.3.1.1). 
    -  NFC (for device retrieval) and Wi-Fi Aware are not supported.
-	**Server retrieval** (8.3.3.2) is not supported.

### Cryptographic Requirements
In accordance with ISO/IEC 18013-5 and ISO/IEC 23220, NZ Verify requires:
-	Issuer-signed Mobile Security Object (MSO) using:
    -  ECDSA (e.g., secp256r1), or
    -  EdDSA (e.g., Ed25519) signatures.
-	Session encryption using ephemeral key exchange for each session.
-	IACA Certificates must conform to X.509 v3 and include relevant ISO mDL extensions. This can be tested here: [MATTR: X.509 Certificate Formatter & Decoder](https://tools.mattrlabs.com/pem)

### Data Elements and Namespace
NZ Verify is currently configured to support verification of mobile driver licences and data attributes associated with that namespace (`org.iso.18013.5.1`).

Detail of the current verifier templates, and associated attributes, can be found here: [NZ Verify (Production) - Verifier Templates](TEMPLATES.md)

However, NZ Verify can support *any* namespace or set of attributes including, but not limited to, `org.iso.18013.5.1`, `org.iso.18013.5.1.aamva`, `org.iso.23220.1`, `org.iso.23220.1.jp`, `org.iso.23220.photoID.1`, `eu.europa.ec.eudi.pid.1`, or `org.micov.1`.

## Adding support for credentials
NZ Verify can be enabled to support the verification of credentials that are issued in the ISO/IEC 18013-5/23220 format and are either:
*  **accredited in New Zealand** by the [Trust Framework Authority](https://www.dia.govt.nz/trust-framework); or
*  **issued by an overseas authority**, or an agent of that authority, authorised to issue a driver licence or permit.[^1]

If you meet this criteria and wish to discuss NZ Verify supporting verification of your credential, please contact us at [nzverifyapp@dia.govt.nz](mailto:nzverifyapp@dia.govt.nz).

[^1]: Refer: [Land Transport (Driver Licensing) Rule 1999](https://www.legislation.govt.nz/regulation/public/1999/0100/latest/DLM281967.html?search=ts_act%40bill%40regulation%40deemedreg_land+transport_resel_25_a&p=1)

## Technical guidance for issuers and wallets
If your organisation is interested in exploring how NZ Verify can support your development of ISO-compliant digital credentials or holder apps, or if you'd like access to the sandbox environment, we’d love to hear from you. Please contact us at [nzverifyapp@dia.govt.nz](mailto:nzverifyapp@dia.govt.nz) to start a conversation about how we can work together to enable trusted digital services in New Zealand.

The sandbox can be configured to support any technically valid credential (as defined above) and to add new document types or namespaces for other use cases.

### Test Holder/Wallet Apps
NZ Verify Sandbox has been successfully tested with the following wallet/holder apps for the purpose of testing:
*  [MATTR GO Hold](https://learn.mattr.global/guides/get-started-go/go-hold/go-hold-example)
*  [EUDI Android Wallet reference application](https://github.com/eu-digital-identity-wallet/eudi-app-android-wallet-ui)
*  [Open Wallet Foundation Identity Credential Wallet](https://github.com/openwallet-foundation-labs/identity-credential)
*  [Multipaz Test App](https://apps.multipaz.org/)

## Future functionality
NZ Verify will support additional technologies and use cases in the future. This includes:
*    NFC Device Engagement for Apple iOS
