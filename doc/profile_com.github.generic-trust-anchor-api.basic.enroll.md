# com.github.generic-trust-anchor-api.basic.enroll

## Description
The profile com.github.generic-trust-anchor-api.basic.enroll supports the generation of a Certificate Signing Request (CSR) as PKCS#10 in PEM.

The same profile name com.github.generic-trust-anchor-api.basic.enroll is used for a enrollment and usage profile:
- Generation of a certificate signing request (CSR) [see [Enrollment](#enrollment)]
- Adding personality attributes as part of the enrollment process (e.g. the issued certificate from the PKI) [see [Usage](#usage)]

## Enrollment
The following table specifies the behaviour of the function **gta_personality_enroll()**. <br>The function gta_personality_enroll_auth() is not defined in this profile and any calls to it shall result in GTA_ERROR_PROFILE_UNSUPPORTED.

| **Property** | **Description** |
| ------------ | ----------------|
| Profile Dependencies | Shall be usable with any personality that is created with com.github.generic-trust-anchor-api.basic.rsa and com.github.generic-trust-anchor-api.basic.ec |
| Enrollment Attributes | Supported Context Attributes:<br>**com.github.generic-trust-anchor-api.enroll.subject_rdn** (optional)<br><blockquote>Subject RDN String (zero terminated) as defined in RFC4514. In case of a parsing error or in case the attribute has been set already, the function gta_context_set_attribute() will fail with GTA_ERROR_INVALID_ATTRIBUTE.</blockquote> |
| Enrollment Artifact | The enrollment artifact is a Certificate Signing Request (CSR) as PKCS#10 in PEM. |

## Usage
Usage of the profile with any other function than those functions listed in the table shall result in GTA_ERROR_PROFILE_UNSUPPORTED.

| **Property** | **Description** |
| ------------ | ----------------|
| Profile Dependencies | Shall be usable with any personality that is created with com.github.generic-trust-anchor-api.basic.rsa and com.github.generic-trust-anchor-api.basic.ec |
| Supported Functions | **Context attribute functions [^1]**<br>**Personality attribute functions [^2]** |
| Usage Attributes | N/A |
| Usage Artifact | N/A |

[^1]: Context attribute functions are: gta_context_set_attribute() and gta_context_get_attribute()
[^2]: Personality attribute functions are: gta_personality_add_attribute(), gta_personality_add_trusted_attribute(), gta_personality_get_attribute(), gta_personality_activate_attribute(), gta_personality_deactivate_attribute(), gta_personality_remove_attribute()

