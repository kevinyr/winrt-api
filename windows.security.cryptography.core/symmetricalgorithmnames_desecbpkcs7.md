---
-api-id: P:Windows.Security.Cryptography.Core.SymmetricAlgorithmNames.DesEcbPkcs7
-api-type: winrt property
---

<!-- Property syntax
public string DesEcbPkcs7 { get; }
-->

# Windows.Security.Cryptography.Core.SymmetricAlgorithmNames.DesEcbPkcs7

## -description
Retrieves a string that contains "DES_ECB_PKCS7".

## -property-value
String that contains "DES_ECB_PKCS7".

## -remarks
Use the string retrieved by this property to set the symmetric encryption algorithm name when you call the [OpenAlgorithm](symmetrickeyalgorithmprovider_openalgorithm.md) method on a [SymmetricKeyAlgorithmProvider](symmetrickeyalgorithmprovider.md) object. The string represents the Data Encryption Standard (DES) algorithm coupled with an electronic codebook (ECB) mode of operation and PKCS#7 padding.

## -examples

## -see-also
[SymmetricKeyAlgorithmProvider](symmetrickeyalgorithmprovider.md)