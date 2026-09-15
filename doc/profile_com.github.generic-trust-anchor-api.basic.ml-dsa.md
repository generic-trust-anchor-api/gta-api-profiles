# com.github.generic-trust-anchor-api.basic.ml-dsa

## Description
The profile com.github.generic-trust-anchor-api.basic.ml-dsa supports the creation of a ML-DSA based personality.

The profile name com.github.generic-trust-anchor-api.basic.ml-dsa is used for a creation profile only.

## Creation
The following table specifies the behaviour of the function **gta_personality_create()**.

| **Property** | **Description** |
| ------------ | ----------------|
| Security Mechanism | ML-DSA-65 |
| Fingerprinting [^1] | The fingerprint is the SHA512 value of the DER encoded private key. |
| Attributes | **com.github.generic-trust-anchor-api.keytype.openssl [^2]**<BR><blockquote>An attribute of type “com.github.generic-trust-anchor-api.keytype.openssl” and with name ”com.github.generic-trust-anchor-api.keytype.openssl” is created, specifying the type of the secret attribute (“ML-DSA-65” in this case) of the personality. </blockquote>|
| Usage Info | Intended for use with com.github.generic-trust-anchor-api.basic.tls |

[^1]: Fingerprinting: description under discussion; may be changed in the future
[^2]: Attribute type/name: under discussion; may be changed in the future
