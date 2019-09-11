# Overview

1. Create a Certificate Signing Request
2. Send CSR to Trusted Third Party to verify information. This trusted third party is called a Certificate Authority
3. Certificate Authority verify all the information and cryptographically sign a certificate
    a. Add details about themself "Issuer"
    b. Sign the cerificate with thier private key
4. Certificate Authority send the signed certificate back.

Certificates are "signed" with a cryptographic signature to say "Yes this information is correct". We can sign our own certificates but nobody considers this credible. So we send them to an impartial 3rd party who will verify the information and give us their stamp of approval by signing the certificate with their cryptographic signature.

# Public Key Encryption

## RSA

### Public Key

### Private Key

## Encrypting and Decrypting
  * Encrypyt with recipient's public key - Anyone
  * Decrypt with private key - Only the intended recipient

## Signing and Verifying

 * Encrypt with private key - 
 * Decrypt with public key
  
If we can decrypt the message with the persons public key and the message - after decryption turns out to be as we expected then we know it was in fact the person we expected to send the message, who sent the message.

# What is a certificate

```
-----BEGIN CERTIFICATE-----
MIIDNDCCAhwCCQCrNjpALu7QajANBgkqhkiG9w0BAQsFADBcMQswCQYDVQQGEwJO
WjETMBEGA1UECAwKV2VsbGluZ3RvbjETMBEGA1UEBwwKV2VsbGluZ3RvbjELMAkG
A1UECgwCTkExFjAUBgNVBAMMDVNpbW9uIE1lcnJpY2swHhcNMTkwOTA0MDUyMzI3
WhcNMjAwOTAzMDUyMzI3WjBcMQswCQYDVQQGEwJOWjETMBEGA1UECAwKV2VsbGlu
Z3RvbjETMBEGA1UEBwwKV2VsbGluZ3RvbjELMAkGA1UECgwCTkExFjAUBgNVBAMM
DVNpbW9uIE1lcnJpY2swggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDG
oztCn+NUyUIPbqIYKz2FPhHhkNVAeCxfS/zA7DQOmfw7oYtHg4yNt8rE19bEHla3
Op+bU8jXTvxRD7DWY42s4cADApUKHAl55qUg4XkPec6efY8TNxu91NwjI1ca8p0e
RIV/7r8aa/87GYmESXSZKXXdKgBuUTqbpkcKDmikvueGDwRSbHSM3D3AnBDKDVFD
kdVfPiRFoWSEl9jMtYJPK/7jvwAAI0ZunfvOQS4K2rHkpKii8vC9OqrgmoM5LrK5
btmbi84Ze17+1pYPpETJzLoN/lCtjIxeg96D8EYSW72JRIEu4p8k4GmeLaidcP9f
nocaxcZ5beJxDT/zNqKZAgMBAAEwDQYJKoZIhvcNAQELBQADggEBAKd4wfT3acDO
oGHuC9KWR1tJMM2VwBJDc3eDp4TDHgBxZfdZjQ7U5peZYmX3tDSIorj2VEFInbRE
BOVJQojsboAzCBAoz0BY1QHNw8cc5OcF3qg+nMoDHGhu25P0vV4Fs/TMeUWrSU4Q
XxpZKv4oQBacdJO7gjdA36Y8hs8nmxFnsrh0USRNVI5SA2UCVUFnORQ8G8cnNHK7
RAMdkUJJofeu3V6XlMEJZW4poke8xpjHZbemcwSZ1i/T10fHFxYeWfW4a+EZxVM+
gVQKJ1lTTNQjFFPvA7xE+pBtMQMoF/JW2ZImQFznNlEtB+3jli9F0krdguV+ecwl
RLzD7JPSCj4=
-----END CERTIFICATE-----
```

We can view the certificate
```
openssl x509 -in certificate.cert -noout -text
```

```
Certificate:
    Data:
        Version: 1 (0x0)
        Serial Number:
            ab:36:3a:40:2e:ee:d0:6a
    Signature Algorithm: sha256WithRSAEncryption
        Issuer: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
        Validity
            Not Before: Sep  4 05:23:27 2019 GMT
            Not After : Sep  3 05:23:27 2020 GMT
        Subject: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:c6:a3:3b:42:9f:e3:54:c9:42:0f:6e:a2:18:2b:
                    3d:85:3e:11:e1:90:d5:40:78:2c:5f:4b:fc:c0:ec:
                    34:0e:99:fc:3b:a1:8b:47:83:8c:8d:b7:ca:c4:d7:
                    d6:c4:1e:56:b7:3a:9f:9b:53:c8:d7:4e:fc:51:0f:
                    b0:d6:63:8d:ac:e1:c0:03:02:95:0a:1c:09:79:e6:
                    a5:20:e1:79:0f:79:ce:9e:7d:8f:13:37:1b:bd:d4:
                    dc:23:23:57:1a:f2:9d:1e:44:85:7f:ee:bf:1a:6b:
                    ff:3b:19:89:84:49:74:99:29:75:dd:2a:00:6e:51:
                    3a:9b:a6:47:0a:0e:68:a4:be:e7:86:0f:04:52:6c:
                    74:8c:dc:3d:c0:9c:10:ca:0d:51:43:91:d5:5f:3e:
                    24:45:a1:64:84:97:d8:cc:b5:82:4f:2b:fe:e3:bf:
                    00:00:23:46:6e:9d:fb:ce:41:2e:0a:da:b1:e4:a4:
                    a8:a2:f2:f0:bd:3a:aa:e0:9a:83:39:2e:b2:b9:6e:
                    d9:9b:8b:ce:19:7b:5e:fe:d6:96:0f:a4:44:c9:cc:
                    ba:0d:fe:50:ad:8c:8c:5e:83:de:83:f0:46:12:5b:
                    bd:89:44:81:2e:e2:9f:24:e0:69:9e:2d:a8:9d:70:
                    ff:5f:9e:87:1a:c5:c6:79:6d:e2:71:0d:3f:f3:36:
                    a2:99
                Exponent: 65537 (0x10001)
    Signature Algorithm: sha256WithRSAEncryption
         a7:78:c1:f4:f7:69:c0:ce:a0:61:ee:0b:d2:96:47:5b:49:30:
         cd:95:c0:12:43:73:77:83:a7:84:c3:1e:00:71:65:f7:59:8d:
         0e:d4:e6:97:99:62:65:f7:b4:34:88:a2:b8:f6:54:41:48:9d:
         b4:44:04:e5:49:42:88:ec:6e:80:33:08:10:28:cf:40:58:d5:
         01:cd:c3:c7:1c:e4:e7:05:de:a8:3e:9c:ca:03:1c:68:6e:db:
         93:f4:bd:5e:05:b3:f4:cc:79:45:ab:49:4e:10:5f:1a:59:2a:
         fe:28:40:16:9c:74:93:bb:82:37:40:df:a6:3c:86:cf:27:9b:
         11:67:b2:b8:74:51:24:4d:54:8e:52:03:65:02:55:41:67:39:
         14:3c:1b:c7:27:34:72:bb:44:03:1d:91:42:49:a1:f7:ae:dd:
         5e:97:94:c1:09:65:6e:29:a2:47:bc:c6:98:c7:65:b7:a6:73:
         04:99:d6:2f:d3:d7:47:c7:17:16:1e:59:f5:b8:6b:e1:19:c5:
         53:3e:81:54:0a:27:59:53:4c:d4:23:14:53:ef:03:bc:44:fa:
         90:6d:31:03:28:17:f2:56:d9:92:26:40:5c:e7:36:51:2d:07:
         ed:e3:96:2f:45:d2:4a:dd:82:e5:7e:79:cc:25:44:bc:c3:ec:
         93:d2:0a:3e
```

 * Information about the owner of the domain
    ```
    Subject: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
    ```
 * Information about the creator of the certificate.
    ```
    Issuer: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
    ```
 * RSA Public Key
    * Modulus and Exponent

# Creating a certificate

## Create a certificate signing request

```bash
openssl req -new > certificate_request.csr
```

* `req` - openssl certificate request and certificate generating utility (`openssl-req`)
* `-new` - Generate a new certificate request.

Creates two files:

* `certificate_request.csr` - A certificate request in _PKCS#10_ format
* `privkey.pem` - An Encrypted RSA private key

### Certificate Signing Request

 ```
-----BEGIN CERTIFICATE REQUEST-----
MIICoTCCAYkCAQAwXDELMAkGA1UEBhMCTloxEzARBgNVBAgMCldlbGxpbmd0b24x
EzARBgNVBAcMCldlbGxpbmd0b24xCzAJBgNVBAoMAk5BMRYwFAYDVQQDDA1TaW1v
biBNZXJyaWNrMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAxqM7Qp/j
VMlCD26iGCs9hT4R4ZDVQHgsX0v8wOw0Dpn8O6GLR4OMjbfKxNfWxB5Wtzqfm1PI
1078UQ+w1mONrOHAAwKVChwJeealIOF5D3nOnn2PEzcbvdTcIyNXGvKdHkSFf+6/
Gmv/OxmJhEl0mSl13SoAblE6m6ZHCg5opL7nhg8EUmx0jNw9wJwQyg1RQ5HVXz4k
RaFkhJfYzLWCTyv+478AACNGbp37zkEuCtqx5KSoovLwvTqq4JqDOS6yuW7Zm4vO
GXte/taWD6REycy6Df5QrYyMXoPeg/BGElu9iUSBLuKfJOBpni2onXD/X56HGsXG
eW3icQ0/8zaimQIDAQABoAAwDQYJKoZIhvcNAQELBQADggEBAGW7eb07Q9PfsvSX
CtKp+7ETkyKiRe9OnxhAHy+z51js1LYm2FLmM0aZCOfvaNNCN0LPnmQFi4VF+VaH
p0Olfk2OJZ7JcCfALa67oR4beRRwmX/u/P62wed9DvsVFPx+guojkZbh2AhphkSv
hyHcLS/4GF+IvuLcMZmiUQxSfrHj++wGVLbNgTheyf/BOEwpVhL9Z4JRWWJfNyck
wUNgRlGlazDPdcOM8HO6GqiL2QXHyx5hnleSKLg9EW1zv5ObGSWezjVSXQZ2eBrE
PoBssUVUJx/8vyaZmr9WxLLVFhlB2KnF9u+UA7IBSFRmETM80LqQt5NxoItfHntr
AKizHoA=
-----END CERTIFICATE REQUEST-----
```
```
openssl req -noout -text -in certificate_request.csr
```
```
Certificate Request:
    Data:
        Version: 0 (0x0)
        Subject: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:c6:a3:3b:42:9f:e3:54:c9:42:0f:6e:a2:18:2b:
                    3d:85:3e:11:e1:90:d5:40:78:2c:5f:4b:fc:c0:ec:
                    34:0e:99:fc:3b:a1:8b:47:83:8c:8d:b7:ca:c4:d7:
                    d6:c4:1e:56:b7:3a:9f:9b:53:c8:d7:4e:fc:51:0f:
                    b0:d6:63:8d:ac:e1:c0:03:02:95:0a:1c:09:79:e6:
                    a5:20:e1:79:0f:79:ce:9e:7d:8f:13:37:1b:bd:d4:
                    dc:23:23:57:1a:f2:9d:1e:44:85:7f:ee:bf:1a:6b:
                    ff:3b:19:89:84:49:74:99:29:75:dd:2a:00:6e:51:
                    3a:9b:a6:47:0a:0e:68:a4:be:e7:86:0f:04:52:6c:
                    74:8c:dc:3d:c0:9c:10:ca:0d:51:43:91:d5:5f:3e:
                    24:45:a1:64:84:97:d8:cc:b5:82:4f:2b:fe:e3:bf:
                    00:00:23:46:6e:9d:fb:ce:41:2e:0a:da:b1:e4:a4:
                    a8:a2:f2:f0:bd:3a:aa:e0:9a:83:39:2e:b2:b9:6e:
                    d9:9b:8b:ce:19:7b:5e:fe:d6:96:0f:a4:44:c9:cc:
                    ba:0d:fe:50:ad:8c:8c:5e:83:de:83:f0:46:12:5b:
                    bd:89:44:81:2e:e2:9f:24:e0:69:9e:2d:a8:9d:70:
                    ff:5f:9e:87:1a:c5:c6:79:6d:e2:71:0d:3f:f3:36:
                    a2:99
                Exponent: 65537 (0x10001)
        Attributes:
            a0:00
    Signature Algorithm: sha256WithRSAEncryption
         65:bb:79:bd:3b:43:d3:df:b2:f4:97:0a:d2:a9:fb:b1:13:93:
         22:a2:45:ef:4e:9f:18:40:1f:2f:b3:e7:58:ec:d4:b6:26:d8:
         52:e6:33:46:99:08:e7:ef:68:d3:42:37:42:cf:9e:64:05:8b:
         85:45:f9:56:87:a7:43:a5:7e:4d:8e:25:9e:c9:70:27:c0:2d:
         ae:bb:a1:1e:1b:79:14:70:99:7f:ee:fc:fe:b6:c1:e7:7d:0e:
         fb:15:14:fc:7e:82:ea:23:91:96:e1:d8:08:69:86:44:af:87:
         21:dc:2d:2f:f8:18:5f:88:be:e2:dc:31:99:a2:51:0c:52:7e:
         b1:e3:fb:ec:06:54:b6:cd:81:38:5e:c9:ff:c1:38:4c:29:56:
         12:fd:67:82:51:59:62:5f:37:27:24:c1:43:60:46:51:a5:6b:
         30:cf:75:c3:8c:f0:73:ba:1a:a8:8b:d9:05:c7:cb:1e:61:9e:
         57:92:28:b8:3d:11:6d:73:bf:93:9b:19:25:9e:ce:35:52:5d:
         06:76:78:1a:c4:3e:80:6c:b1:45:54:27:1f:fc:bf:26:99:9a:
         bf:56:c4:b2:d5:16:19:41:d8:a9:c5:f6:ef:94:03:b2:01:48:
         54:66:11:33:3c:d0:ba:90:b7:93:71:a0:8b:5f:1e:7b:6b:00:
         a8:b3:1e:80
```
* Your details
* Contains your public key
* Signed with your private key

### Private Key

```
-----BEGIN ENCRYPTED PRIVATE KEY-----
MIIFDjBABgkqhkiG9w0BBQ0wMzAbBgkqhkiG9w0BBQwwDgQI0Kd+nkXKfs4CAggA
MBQGCCqGSIb3DQMHBAg38LcK1u7TmASCBMgsKE8i3dxLIxMJZMh75VVj/ZjKhDeY
UAjsYno5oCCcigDxjd/8V0HyCItW4zHWACc18lvCn98Rx646JIrcy47cllZQu9HJ
qr5rMbRDLOxTm16p+W4X1rr97JMZMYTLhQgRbqzFeUMHvUqmkOsLzbt5Y2/SL5dU
GBDQV2xxRUbUfY7l4mevz8jZd/XWtagCgucNAr4t0ZhNW97K+oHmUGVRyen0BozS
L2kWdr1Ma637eyjEhRm4UtrU+GUtw5ZQZXm/H4AfGDpgguM9nZQynuEvIqkkTaQe
GAfyp2B9cqY0PAAb3ts6ovv0oMFVrvSKfDVFQHkbQoFdOA9LNnwloeEdZq/V4tUw
OpHBuhbY/Em2F5Bg3V7rz11ZYYfmtA34GvpJ5KkkoS7alVcQPR7kQZ3Vv4uYIb/3
Isc6KD8QAaUpwL0/zUlCFEdqCI8YJhTWXwtd0EV7YHOX6o4t8lVaC+1XH+5wXzzU
ZCoq2NyQLUymLqC+7Fh8Uo7LyjY2oNKHH7cG7HIg7egeMv9WtVbdHCc8tQc4TZ8L
T+2SpiAbBZHLo+CHpsOUJorQ1QvyTRJWK76fbAnKg+PJp1gdymkCHYTjovhpUXxa
jjRaVzFpRpAFI5BiGqDLqaee/EuKwacimCrLKXVV3FeCCOKbA1HnVPX/LXjr41kT
isOx1kj5oG/VF403eqJYNZ5/yxNw0AbhSXaTnNp4YyKZIMxOhJS7JiYmR2/IH3eP
Cro/216BrxNdAVNkBjy/68i7L6+AmSMwtQNlun1Cf0E5U5Vay/E7DvGcjiiGPmEt
+agq9ZJ4Xl3bIixAVP7BtC4zDfGHahGM6skSDXnGsdfWjfg4oddrtpHSrnf9RegX
G/SGArZyYyuIH9vGIVQ5Ezh2NNpgGr4P+h9kZV7vQXVlBMxB7WwnCtFrg30Yr/iU
FfqlNZ05Oe5udojfZmpvKqdpEhLtKCVwvT4nkck0uXDnbtSZ++0umnLJxdifizXm
ETq57vAOMIjlrXx66G2oGlnTF4ss47t9f8JCw2edo3XijwOckkNr0wvmcKK9Ys6L
a2sijwLb6VIyvbGTltAaznRRTYXrFe0+Su3o+T5K89uRyKFUPtLHIs6iHPeg1X5e
Mg5xRu+ww/fnR5knTmV0hNLkuXcuAdHiJq3Wv9LSboWwFyI601gJzcnPBttqdtwf
UWD7z5mAF1BJfPGbIlGh2tPqLPI4JSx9MezaMsoIaq/BD/CdU44ndheuq51ghQzr
PrE9IDxXPK7xeNZNlbIDGH55psikZJ5B0hXo1WCnRxVcwHIFSdvodH4D1iyPI7tB
SiY169rMX/IrjjZFZFAmlQjtUHvkJzxsRcztXlbZv/JNpBw8eNuFrvDPCUJn8CiU
SOlQVcE9IcRzzoaRAJ0NbZgupe3Y6BDGS0NmL3MeZFKPUWikIFzIMpUVrZLErhsh
2ugGXXD1OroFzluxChml9Sfc04SAiD8fSwlzlsZQED0oEvfC206vNVmvPISmgxQn
gT9d8Nv3Cq157hI4YPPk17exoc8VsckW4+j0JCJVgTQlDtCzh47Zvydj52LdmVxD
KE2OnF1VkpqSHg2Rg/t+UefOTkI/YWIAKSaIOOxmi541Xn7XCHnDfGOQCAn+2vCS
0r0=
-----END ENCRYPTED PRIVATE KEY-----
```
```bash
openssl rsa -noout -text -in privkey.pem
```

```
Private-Key: (2048 bit)
modulus:
    00:c6:a3:3b:42:9f:e3:54:c9:42:0f:6e:a2:18:2b:
    3d:85:3e:11:e1:90:d5:40:78:2c:5f:4b:fc:c0:ec:
    34:0e:99:fc:3b:a1:8b:47:83:8c:8d:b7:ca:c4:d7:
    d6:c4:1e:56:b7:3a:9f:9b:53:c8:d7:4e:fc:51:0f:
    b0:d6:63:8d:ac:e1:c0:03:02:95:0a:1c:09:79:e6:
    a5:20:e1:79:0f:79:ce:9e:7d:8f:13:37:1b:bd:d4:
    dc:23:23:57:1a:f2:9d:1e:44:85:7f:ee:bf:1a:6b:
    ff:3b:19:89:84:49:74:99:29:75:dd:2a:00:6e:51:
    3a:9b:a6:47:0a:0e:68:a4:be:e7:86:0f:04:52:6c:
    74:8c:dc:3d:c0:9c:10:ca:0d:51:43:91:d5:5f:3e:
    24:45:a1:64:84:97:d8:cc:b5:82:4f:2b:fe:e3:bf:
    00:00:23:46:6e:9d:fb:ce:41:2e:0a:da:b1:e4:a4:
    a8:a2:f2:f0:bd:3a:aa:e0:9a:83:39:2e:b2:b9:6e:
    d9:9b:8b:ce:19:7b:5e:fe:d6:96:0f:a4:44:c9:cc:
    ba:0d:fe:50:ad:8c:8c:5e:83:de:83:f0:46:12:5b:
    bd:89:44:81:2e:e2:9f:24:e0:69:9e:2d:a8:9d:70:
    ff:5f:9e:87:1a:c5:c6:79:6d:e2:71:0d:3f:f3:36:
    a2:99
publicExponent: 65537 (0x10001)
privateExponent:
    0d:83:09:02:ed:31:5f:91:19:27:47:95:4b:23:95:
    d9:bc:71:26:f0:dd:30:b7:7b:fd:37:84:07:f3:89:
    4e:fc:f6:85:6f:e5:b3:85:a5:47:f6:9a:9a:6d:3c:
    34:b7:03:9b:0f:27:d0:3f:10:c8:64:9d:11:3e:89:
    fe:eb:62:b5:c1:dd:77:d6:f3:20:6e:eb:ce:18:fc:
    5e:92:37:d3:ef:ab:38:68:be:14:c6:88:e2:8e:da:
    32:a1:b2:c9:28:7b:bb:95:59:a7:6c:2c:1f:b5:fc:
    f4:9e:36:16:83:90:a4:e2:87:1b:f6:41:75:3f:9d:
    46:fd:36:93:de:8b:0b:b9:ba:02:eb:d9:e7:4b:a8:
    77:2c:87:58:83:56:ba:5b:b5:41:ad:e4:58:01:4a:
    88:27:06:1a:74:aa:3c:5b:eb:54:5c:ba:24:81:24:
    da:4d:eb:3d:15:6e:7f:b9:23:13:ef:5e:9c:2d:81:
    a5:d9:c7:13:b9:da:86:c8:1f:bd:36:12:75:14:ca:
    21:2c:8b:35:87:f7:c4:77:db:84:e7:d6:68:cf:2b:
    69:53:9e:fc:95:ee:29:5e:2c:5f:ac:09:48:71:90:
    40:e8:06:8e:1c:46:b8:94:d9:40:87:89:8e:c9:42:
    ae:c2:34:2d:d1:c7:86:02:d8:27:e3:6d:87:5d:da:
    21
prime1:
    00:e5:a5:38:50:1f:50:e9:b8:9a:6c:4d:b7:bd:5b:
    8a:60:88:f9:23:ca:6c:66:9e:4a:fa:28:27:dc:9a:
    2b:d9:ba:aa:23:d9:ed:a7:23:0f:8c:20:37:23:a2:
    aa:99:45:06:7d:ee:4f:16:2f:69:a2:4b:d6:a2:9a:
    eb:8a:90:91:28:cc:90:31:5a:3e:06:da:e6:7a:33:
    43:c0:25:d4:c9:a8:39:90:9b:dc:30:2f:44:e8:fc:
    61:d4:db:61:78:a7:e4:dc:75:de:37:1c:1d:cb:32:
    c0:2c:ea:5d:7c:1b:ff:34:96:1a:a6:3d:f4:d0:67:
    3e:53:23:3b:83:78:30:5e:dd
prime2:
    00:dd:6f:07:cf:ed:6b:43:00:12:95:c8:2f:98:96:
    af:10:93:d3:7e:d2:db:ee:7f:2a:69:d1:14:a3:d1:
    b5:e4:be:c4:c8:b4:de:b4:e3:cf:12:e9:a3:da:84:
    0b:1b:8b:75:a6:7e:4f:43:ee:57:fb:8c:c9:50:b4:
    b4:af:14:02:bd:8a:9a:05:be:ae:58:4b:9b:5d:97:
    91:75:47:e8:c9:89:4e:ed:b2:0b:99:30:3e:85:ad:
    74:83:c0:a7:18:80:01:ec:13:09:fb:29:eb:b6:d6:
    ee:66:e3:50:cc:ee:9e:9d:30:d4:38:25:a2:23:e8:
    79:66:07:e6:53:eb:f5:10:ed
exponent1:
    00:b7:44:04:4d:c4:c0:20:d5:46:bf:79:c2:51:66:
    95:66:f6:c8:c4:ac:4d:98:13:69:48:7b:f5:5b:d2:
    d9:7d:d7:be:e1:ff:8f:ee:1b:47:d4:0e:fd:91:fd:
    c5:e1:ad:39:42:14:85:9e:f1:d5:7e:44:c1:94:60:
    c7:ea:7b:f6:ac:35:9c:39:16:88:7b:96:03:ea:af:
    b0:b8:ce:38:23:7a:91:fd:fa:b4:5c:eb:cc:35:96:
    fc:48:0f:8f:98:e7:7b:f8:08:44:7f:7c:7b:b6:66:
    d9:00:bf:44:3d:c0:66:09:44:65:1e:18:41:a0:73:
    54:44:aa:d0:5a:d9:f6:d8:2d
exponent2:
    00:c5:71:cc:70:7e:0e:07:87:18:0b:50:9e:08:1c:
    4c:6b:a6:b4:8e:40:6c:75:44:14:c8:97:f3:24:83:
    c9:01:f7:8c:b6:3e:78:da:a8:cb:2a:dd:04:0a:c3:
    74:b8:11:e9:4d:15:11:8e:cc:06:cd:b9:62:84:c1:
    2c:df:74:23:61:69:26:1f:7b:40:30:60:f2:5f:48:
    d8:1d:d0:89:e4:b2:b7:9b:41:08:10:87:31:28:b7:
    5a:ce:64:49:5a:92:41:a4:83:f1:81:70:86:ca:d8:
    e9:68:fa:c6:40:85:81:0f:3e:cb:ec:68:ba:23:f4:
    95:d3:01:b6:42:1c:82:bf:9d
coefficient:
    60:b7:23:3e:5a:ee:67:70:3d:c6:71:7e:19:64:ce:
    75:1e:b4:b5:f9:c6:e3:19:20:8a:77:3d:35:82:a9:
    74:dc:b8:ed:42:0e:90:72:89:c9:f7:ed:62:5f:e1:
    ff:91:19:88:ac:09:73:ce:62:2e:f7:21:6e:3b:80:
    64:2a:34:e7:33:cf:45:c2:8c:0d:2c:28:82:bd:2f:
    ca:26:bb:e2:d8:29:e5:88:8d:14:8b:76:8a:ae:82:
    3a:54:20:38:47:31:35:ec:a6:27:52:88:ff:ac:d2:
    26:73:79:a8:46:80:54:7b:ff:76:5d:a6:a9:d5:6e:
    23:5d:74:67:7f:ea:d3:92
```

## Create the certificate key

Decrypt `privkey.pem` and save it in its decrypted form

```bash
openssl rsa -in privkey.pem -out certificate_key.key
```
 * `rsa` - openssl RSA key processing tool. The rsa command processes RSA keys. They can be converted between various forms.
 * `-in` - filename of an RSA private key
 * `-out` - filename of a new key

Creates:

 * `certificate_key.key` - Decrypted RSA Private Key

```
-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAxqM7Qp/jVMlCD26iGCs9hT4R4ZDVQHgsX0v8wOw0Dpn8O6GL
R4OMjbfKxNfWxB5Wtzqfm1PI1078UQ+w1mONrOHAAwKVChwJeealIOF5D3nOnn2P
EzcbvdTcIyNXGvKdHkSFf+6/Gmv/OxmJhEl0mSl13SoAblE6m6ZHCg5opL7nhg8E
Umx0jNw9wJwQyg1RQ5HVXz4kRaFkhJfYzLWCTyv+478AACNGbp37zkEuCtqx5KSo
ovLwvTqq4JqDOS6yuW7Zm4vOGXte/taWD6REycy6Df5QrYyMXoPeg/BGElu9iUSB
LuKfJOBpni2onXD/X56HGsXGeW3icQ0/8zaimQIDAQABAoIBAA2DCQLtMV+RGSdH
lUsjldm8cSbw3TC3e/03hAfziU789oVv5bOFpUf2mpptPDS3A5sPJ9A/EMhknRE+
if7rYrXB3XfW8yBu684Y/F6SN9PvqzhovhTGiOKO2jKhsskoe7uVWadsLB+1/PSe
NhaDkKTihxv2QXU/nUb9NpPeiwu5ugLr2edLqHcsh1iDVrpbtUGt5FgBSognBhp0
qjxb61RcuiSBJNpN6z0Vbn+5IxPvXpwtgaXZxxO52obIH702EnUUyiEsizWH98R3
24Tn1mjPK2lTnvyV7ileLF+sCUhxkEDoBo4cRriU2UCHiY7JQq7CNC3Rx4YC2Cfj
bYdd2iECgYEA5aU4UB9Q6biabE23vVuKYIj5I8psZp5K+ign3Jor2bqqI9ntpyMP
jCA3I6KqmUUGfe5PFi9pokvWoprripCRKMyQMVo+BtrmejNDwCXUyag5kJvcMC9E
6Pxh1NtheKfk3HXeNxwdyzLALOpdfBv/NJYapj300Gc+UyM7g3gwXt0CgYEA3W8H
z+1rQwASlcgvmJavEJPTftLb7n8qadEUo9G15L7EyLTetOPPEumj2oQLG4t1pn5P
Q+5X+4zJULS0rxQCvYqaBb6uWEubXZeRdUfoyYlO7bILmTA+ha10g8CnGIAB7BMJ
+ynrttbuZuNQzO6enTDUOCWiI+h5ZgfmU+v1EO0CgYEAt0QETcTAINVGv3nCUWaV
ZvbIxKxNmBNpSHv1W9LZfde+4f+P7htH1A79kf3F4a05QhSFnvHVfkTBlGDH6nv2
rDWcORaIe5YD6q+wuM44I3qR/fq0XOvMNZb8SA+PmOd7+AhEf3x7tmbZAL9EPcBm
CURlHhhBoHNURKrQWtn22C0CgYEAxXHMcH4OB4cYC1CeCBxMa6a0jkBsdUQUyJfz
JIPJAfeMtj542qjLKt0ECsN0uBHpTRURjswGzblihMEs33QjYWkmH3tAMGDyX0jY
HdCJ5LK3m0EIEIcxKLdazmRJWpJBpIPxgXCGytjpaPrGQIWBDz7L7Gi6I/SV0wG2
QhyCv50CgYBgtyM+Wu5ncD3GcX4ZZM51HrS1+cbjGSCKdz01gql03LjtQg6QconJ
9+1iX+H/kRmIrAlzzmIu9yFuO4BkKjTnM89FwowNLCiCvS/KJrvi2CnliI0Ui3aK
roI6VCA4RzE17KYnUoj/rNImc3moRoBUe/92Xaap1W4jXXRnf+rTkg==
-----END RSA PRIVATE KEY-----
```

```
openssl rsa -noout -text -in certificate_key.key
```

```
Private-Key: (2048 bit)
modulus:
    00:c6:a3:3b:42:9f:e3:54:c9:42:0f:6e:a2:18:2b:
    3d:85:3e:11:e1:90:d5:40:78:2c:5f:4b:fc:c0:ec:
    34:0e:99:fc:3b:a1:8b:47:83:8c:8d:b7:ca:c4:d7:
    d6:c4:1e:56:b7:3a:9f:9b:53:c8:d7:4e:fc:51:0f:
    b0:d6:63:8d:ac:e1:c0:03:02:95:0a:1c:09:79:e6:
    a5:20:e1:79:0f:79:ce:9e:7d:8f:13:37:1b:bd:d4:
    dc:23:23:57:1a:f2:9d:1e:44:85:7f:ee:bf:1a:6b:
    ff:3b:19:89:84:49:74:99:29:75:dd:2a:00:6e:51:
    3a:9b:a6:47:0a:0e:68:a4:be:e7:86:0f:04:52:6c:
    74:8c:dc:3d:c0:9c:10:ca:0d:51:43:91:d5:5f:3e:
    24:45:a1:64:84:97:d8:cc:b5:82:4f:2b:fe:e3:bf:
    00:00:23:46:6e:9d:fb:ce:41:2e:0a:da:b1:e4:a4:
    a8:a2:f2:f0:bd:3a:aa:e0:9a:83:39:2e:b2:b9:6e:
    d9:9b:8b:ce:19:7b:5e:fe:d6:96:0f:a4:44:c9:cc:
    ba:0d:fe:50:ad:8c:8c:5e:83:de:83:f0:46:12:5b:
    bd:89:44:81:2e:e2:9f:24:e0:69:9e:2d:a8:9d:70:
    ff:5f:9e:87:1a:c5:c6:79:6d:e2:71:0d:3f:f3:36:
    a2:99
publicExponent: 65537 (0x10001)
privateExponent:
    0d:83:09:02:ed:31:5f:91:19:27:47:95:4b:23:95:
    d9:bc:71:26:f0:dd:30:b7:7b:fd:37:84:07:f3:89:
    4e:fc:f6:85:6f:e5:b3:85:a5:47:f6:9a:9a:6d:3c:
    34:b7:03:9b:0f:27:d0:3f:10:c8:64:9d:11:3e:89:
    fe:eb:62:b5:c1:dd:77:d6:f3:20:6e:eb:ce:18:fc:
    5e:92:37:d3:ef:ab:38:68:be:14:c6:88:e2:8e:da:
    32:a1:b2:c9:28:7b:bb:95:59:a7:6c:2c:1f:b5:fc:
    f4:9e:36:16:83:90:a4:e2:87:1b:f6:41:75:3f:9d:
    46:fd:36:93:de:8b:0b:b9:ba:02:eb:d9:e7:4b:a8:
    77:2c:87:58:83:56:ba:5b:b5:41:ad:e4:58:01:4a:
    88:27:06:1a:74:aa:3c:5b:eb:54:5c:ba:24:81:24:
    da:4d:eb:3d:15:6e:7f:b9:23:13:ef:5e:9c:2d:81:
    a5:d9:c7:13:b9:da:86:c8:1f:bd:36:12:75:14:ca:
    21:2c:8b:35:87:f7:c4:77:db:84:e7:d6:68:cf:2b:
    69:53:9e:fc:95:ee:29:5e:2c:5f:ac:09:48:71:90:
    40:e8:06:8e:1c:46:b8:94:d9:40:87:89:8e:c9:42:
    ae:c2:34:2d:d1:c7:86:02:d8:27:e3:6d:87:5d:da:
    21
prime1:
    00:e5:a5:38:50:1f:50:e9:b8:9a:6c:4d:b7:bd:5b:
    8a:60:88:f9:23:ca:6c:66:9e:4a:fa:28:27:dc:9a:
    2b:d9:ba:aa:23:d9:ed:a7:23:0f:8c:20:37:23:a2:
    aa:99:45:06:7d:ee:4f:16:2f:69:a2:4b:d6:a2:9a:
    eb:8a:90:91:28:cc:90:31:5a:3e:06:da:e6:7a:33:
    43:c0:25:d4:c9:a8:39:90:9b:dc:30:2f:44:e8:fc:
    61:d4:db:61:78:a7:e4:dc:75:de:37:1c:1d:cb:32:
    c0:2c:ea:5d:7c:1b:ff:34:96:1a:a6:3d:f4:d0:67:
    3e:53:23:3b:83:78:30:5e:dd
prime2:
    00:dd:6f:07:cf:ed:6b:43:00:12:95:c8:2f:98:96:
    af:10:93:d3:7e:d2:db:ee:7f:2a:69:d1:14:a3:d1:
    b5:e4:be:c4:c8:b4:de:b4:e3:cf:12:e9:a3:da:84:
    0b:1b:8b:75:a6:7e:4f:43:ee:57:fb:8c:c9:50:b4:
    b4:af:14:02:bd:8a:9a:05:be:ae:58:4b:9b:5d:97:
    91:75:47:e8:c9:89:4e:ed:b2:0b:99:30:3e:85:ad:
    74:83:c0:a7:18:80:01:ec:13:09:fb:29:eb:b6:d6:
    ee:66:e3:50:cc:ee:9e:9d:30:d4:38:25:a2:23:e8:
    79:66:07:e6:53:eb:f5:10:ed
exponent1:
    00:b7:44:04:4d:c4:c0:20:d5:46:bf:79:c2:51:66:
    95:66:f6:c8:c4:ac:4d:98:13:69:48:7b:f5:5b:d2:
    d9:7d:d7:be:e1:ff:8f:ee:1b:47:d4:0e:fd:91:fd:
    c5:e1:ad:39:42:14:85:9e:f1:d5:7e:44:c1:94:60:
    c7:ea:7b:f6:ac:35:9c:39:16:88:7b:96:03:ea:af:
    b0:b8:ce:38:23:7a:91:fd:fa:b4:5c:eb:cc:35:96:
    fc:48:0f:8f:98:e7:7b:f8:08:44:7f:7c:7b:b6:66:
    d9:00:bf:44:3d:c0:66:09:44:65:1e:18:41:a0:73:
    54:44:aa:d0:5a:d9:f6:d8:2d
exponent2:
    00:c5:71:cc:70:7e:0e:07:87:18:0b:50:9e:08:1c:
    4c:6b:a6:b4:8e:40:6c:75:44:14:c8:97:f3:24:83:
    c9:01:f7:8c:b6:3e:78:da:a8:cb:2a:dd:04:0a:c3:
    74:b8:11:e9:4d:15:11:8e:cc:06:cd:b9:62:84:c1:
    2c:df:74:23:61:69:26:1f:7b:40:30:60:f2:5f:48:
    d8:1d:d0:89:e4:b2:b7:9b:41:08:10:87:31:28:b7:
    5a:ce:64:49:5a:92:41:a4:83:f1:81:70:86:ca:d8:
    e9:68:fa:c6:40:85:81:0f:3e:cb:ec:68:ba:23:f4:
    95:d3:01:b6:42:1c:82:bf:9d
coefficient:
    60:b7:23:3e:5a:ee:67:70:3d:c6:71:7e:19:64:ce:
    75:1e:b4:b5:f9:c6:e3:19:20:8a:77:3d:35:82:a9:
    74:dc:b8:ed:42:0e:90:72:89:c9:f7:ed:62:5f:e1:
    ff:91:19:88:ac:09:73:ce:62:2e:f7:21:6e:3b:80:
    64:2a:34:e7:33:cf:45:c2:8c:0d:2c:28:82:bd:2f:
    ca:26:bb:e2:d8:29:e5:88:8d:14:8b:76:8a:ae:82:
    3a:54:20:38:47:31:35:ec:a6:27:52:88:ff:ac:d2:
    26:73:79:a8:46:80:54:7b:ff:76:5d:a6:a9:d5:6e:
    23:5d:74:67:7f:ea:d3:92
```

## Create a self signed certificate

```bash
openssl x509 -in certificate_request.csr -out certificate.cert -req -signkey certificate_key.key -days 365
```

 * `x509` - Certificate display and signing utility. The x509 command is a multi purpose certificate utility. It can be used to display certificate information, convert
       certificates to various forms, sign certificate requests
 * `-in`
 * `-out`
 * `-req`
 * `-signkey`
 * `-days`

Creates
 * `certificate.cert` - The x509 certificate, encoded using DER (Distinguished Encoding Rules), base64 encoded and finally
wedged between the `BEGIN CERTIFICATE` and `END CERTIFICATE` header and footer.

```
-----BEGIN CERTIFICATE-----
MIIDNDCCAhwCCQCrNjpALu7QajANBgkqhkiG9w0BAQsFADBcMQswCQYDVQQGEwJO
WjETMBEGA1UECAwKV2VsbGluZ3RvbjETMBEGA1UEBwwKV2VsbGluZ3RvbjELMAkG
A1UECgwCTkExFjAUBgNVBAMMDVNpbW9uIE1lcnJpY2swHhcNMTkwOTA0MDUyMzI3
WhcNMjAwOTAzMDUyMzI3WjBcMQswCQYDVQQGEwJOWjETMBEGA1UECAwKV2VsbGlu
Z3RvbjETMBEGA1UEBwwKV2VsbGluZ3RvbjELMAkGA1UECgwCTkExFjAUBgNVBAMM
DVNpbW9uIE1lcnJpY2swggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDG
oztCn+NUyUIPbqIYKz2FPhHhkNVAeCxfS/zA7DQOmfw7oYtHg4yNt8rE19bEHla3
Op+bU8jXTvxRD7DWY42s4cADApUKHAl55qUg4XkPec6efY8TNxu91NwjI1ca8p0e
RIV/7r8aa/87GYmESXSZKXXdKgBuUTqbpkcKDmikvueGDwRSbHSM3D3AnBDKDVFD
kdVfPiRFoWSEl9jMtYJPK/7jvwAAI0ZunfvOQS4K2rHkpKii8vC9OqrgmoM5LrK5
btmbi84Ze17+1pYPpETJzLoN/lCtjIxeg96D8EYSW72JRIEu4p8k4GmeLaidcP9f
nocaxcZ5beJxDT/zNqKZAgMBAAEwDQYJKoZIhvcNAQELBQADggEBAKd4wfT3acDO
oGHuC9KWR1tJMM2VwBJDc3eDp4TDHgBxZfdZjQ7U5peZYmX3tDSIorj2VEFInbRE
BOVJQojsboAzCBAoz0BY1QHNw8cc5OcF3qg+nMoDHGhu25P0vV4Fs/TMeUWrSU4Q
XxpZKv4oQBacdJO7gjdA36Y8hs8nmxFnsrh0USRNVI5SA2UCVUFnORQ8G8cnNHK7
RAMdkUJJofeu3V6XlMEJZW4poke8xpjHZbemcwSZ1i/T10fHFxYeWfW4a+EZxVM+
gVQKJ1lTTNQjFFPvA7xE+pBtMQMoF/JW2ZImQFznNlEtB+3jli9F0krdguV+ecwl
RLzD7JPSCj4=
-----END CERTIFICATE-----
```

**View our certificate**
```
openssl x509 -in certificate.cert -noout -text
```

```
Certificate:
    Data:
        Version: 1 (0x0)
        Serial Number:
            ab:36:3a:40:2e:ee:d0:6a
    Signature Algorithm: sha256WithRSAEncryption
        Issuer: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
        Validity
            Not Before: Sep  4 05:23:27 2019 GMT
            Not After : Sep  3 05:23:27 2020 GMT
        Subject: C=NZ, ST=Wellington, L=Wellington, O=NA, CN=Simon Merrick
        Subject Public Key Info:
            Public Key Algorithm: rsaEncryption
                Public-Key: (2048 bit)
                Modulus:
                    00:c6:a3:3b:42:9f:e3:54:c9:42:0f:6e:a2:18:2b:
                    3d:85:3e:11:e1:90:d5:40:78:2c:5f:4b:fc:c0:ec:
                    34:0e:99:fc:3b:a1:8b:47:83:8c:8d:b7:ca:c4:d7:
                    d6:c4:1e:56:b7:3a:9f:9b:53:c8:d7:4e:fc:51:0f:
                    b0:d6:63:8d:ac:e1:c0:03:02:95:0a:1c:09:79:e6:
                    a5:20:e1:79:0f:79:ce:9e:7d:8f:13:37:1b:bd:d4:
                    dc:23:23:57:1a:f2:9d:1e:44:85:7f:ee:bf:1a:6b:
                    ff:3b:19:89:84:49:74:99:29:75:dd:2a:00:6e:51:
                    3a:9b:a6:47:0a:0e:68:a4:be:e7:86:0f:04:52:6c:
                    74:8c:dc:3d:c0:9c:10:ca:0d:51:43:91:d5:5f:3e:
                    24:45:a1:64:84:97:d8:cc:b5:82:4f:2b:fe:e3:bf:
                    00:00:23:46:6e:9d:fb:ce:41:2e:0a:da:b1:e4:a4:
                    a8:a2:f2:f0:bd:3a:aa:e0:9a:83:39:2e:b2:b9:6e:
                    d9:9b:8b:ce:19:7b:5e:fe:d6:96:0f:a4:44:c9:cc:
                    ba:0d:fe:50:ad:8c:8c:5e:83:de:83:f0:46:12:5b:
                    bd:89:44:81:2e:e2:9f:24:e0:69:9e:2d:a8:9d:70:
                    ff:5f:9e:87:1a:c5:c6:79:6d:e2:71:0d:3f:f3:36:
                    a2:99
                Exponent: 65537 (0x10001)
    Signature Algorithm: sha256WithRSAEncryption
         a7:78:c1:f4:f7:69:c0:ce:a0:61:ee:0b:d2:96:47:5b:49:30:
         cd:95:c0:12:43:73:77:83:a7:84:c3:1e:00:71:65:f7:59:8d:
         0e:d4:e6:97:99:62:65:f7:b4:34:88:a2:b8:f6:54:41:48:9d:
         b4:44:04:e5:49:42:88:ec:6e:80:33:08:10:28:cf:40:58:d5:
         01:cd:c3:c7:1c:e4:e7:05:de:a8:3e:9c:ca:03:1c:68:6e:db:
         93:f4:bd:5e:05:b3:f4:cc:79:45:ab:49:4e:10:5f:1a:59:2a:
         fe:28:40:16:9c:74:93:bb:82:37:40:df:a6:3c:86:cf:27:9b:
         11:67:b2:b8:74:51:24:4d:54:8e:52:03:65:02:55:41:67:39:
         14:3c:1b:c7:27:34:72:bb:44:03:1d:91:42:49:a1:f7:ae:dd:
         5e:97:94:c1:09:65:6e:29:a2:47:bc:c6:98:c7:65:b7:a6:73:
         04:99:d6:2f:d3:d7:47:c7:17:16:1e:59:f5:b8:6b:e1:19:c5:
         53:3e:81:54:0a:27:59:53:4c:d4:23:14:53:ef:03:bc:44:fa:
         90:6d:31:03:28:17:f2:56:d9:92:26:40:5c:e7:36:51:2d:07:
         ed:e3:96:2f:45:d2:4a:dd:82:e5:7e:79:cc:25:44:bc:c3:ec:
         93:d2:0a:3e
```

# Glossary

#### PKCS - Public Key Cryptography Standards

#### ASN.1 - Abstract Syntax Notation One

A standard interface description language for defining data structures that can be serialized and deserialized in a cross-platform way. It is broadly used in telecommunications and computer networking, and especially in cryptography. 

#### BER - Basic Encoding Rules

Basic Encoding Rules specifies a self-describing and self-delimiting format for encoding ASN.1 data structures.

#### DER - Distinguished Encoding Rules

A binary encoding format

#### PEM - Privacy-Enhanced Mail

Base64 encoded DER datastructure, enclosed between `-----BEGIN CERTIFICATE-----` and `-----END CERTIFICATE-----`. This makes it easier to handle - Copying and pasting, sending via email.

```
-----BEGIN CERTIFICATE-----

[Base64 Encoded DER Cert.]

-----BEGIN CERTIFICATE-----
```
