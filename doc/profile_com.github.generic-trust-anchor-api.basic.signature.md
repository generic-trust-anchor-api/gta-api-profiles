# com.github.generic-trust-anchor-api.basic.signature

## Description
The profile com.github.generic-trust-anchor-api.basic.signature supports the creation of digital signatures (e.g., for authentication during TLS handshake).

The same profile name com.github.generic-trust-anchor-api.basic.signature is used for a enrollment and a usage profile.

## Enrollment
The following table specifies the behaviour of the function **gta_personality_enroll()**. <br>The function gta_personality_enroll_auth() is not defined in this profile and any calls to it shall result in GTA_ERROR_PROFILE_UNSUPPORTED.

The enrollment function for profile com.github.generic-trust-anchor-api.basic.signature allows an application to get the public key of a personality, corresponding to its private key.

| **Property** | **Description** |
| ------------ | ----------------|
| Profile Dependencies | Shall be usable with any personality that is created with com.github.generic-trust-anchor-api.basic.rsa, com.github.generic-trust-anchor-api.basic.ec and com.github.generic-trust-anchor-api.basic.dilithium |
| Enrollment Attributes | N/A |
| Enrollment Artifact | PEM encoded public key |

## Usage
Usage of the profile with any other function than those functions listed in the table shall result in GTA_ERROR_PROFILE_UNSUPPORTED.

| **Property** | **Description** |
| ------------ | ----------------|
| Profile Dependencies | Shall be usable with any personality that is created with com.github.generic-trust-anchor-api.basic.rsa, com.github.generic-trust-anchor-api.basic.ec and com.github.generic-trust-anchor-api.basic.dilithium |
| Supported Functions | **Personality attribute functions [^1]**<br>**gta_authenticate_data_detached()**<br><blockquote>computes a digital signature for the data provided as input data.</blockquote> |
| Usage Attributes | N/A |
| Usage Artifact | Digital signature in the following format depending on the used creation profile:<br>- com.github.generic-trust-anchor-api.basic.rsa: raw bytes (RSASSA-PKCS1-v1_5 using SHA-256)<br>- com.github.generic-trust-anchor-api.basic.ec: DER-encoded (ECDSA with P-256 and SHA-256)<br>- com.github.generic-trust-anchor-api.basic.dilithium: raw bytes |

[^1]: Personality attribute functions are: gta_personality_add_attribute(), gta_personality_add_trusted_attribute(), gta_personality_get_attribute(), gta_personality_activate_attribute(), gta_personality_deactivate_attribute(), gta_personality_remove_attribute()
