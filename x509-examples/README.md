# Examples using COSE header parameters for X.509 certificates

The X.509 certificates used in these examples were generated following the examples and scripts in [draft-dkg-lamps-samples](https://datatracker.ietf.org/doc/draft-dkg-lamps-samples/).  

## Certificate Authority Certificate

This certificate is contained in `ca.crt`.
```
-----BEGIN CERTIFICATE-----
MIIBnjCCAUWgAwIBAgIUFKSVf9UGqiqvxmmogAMujJW4diQwCgYIKoZIzj0EAwIw
LDEqMCgGA1UEAxMhU2FtcGxlIENPU0UgQ2VydGlmaWNhdGUgQXV0aG9yaXR5MCAX
DTIwMTIwMjE3MjMzMloYDzIwNTMxMDEwMTcyMzMyWjAsMSowKAYDVQQDEyFTYW1w
bGUgQ09TRSBDZXJ0aWZpY2F0ZSBBdXRob3JpdHkwWTATBgcqhkjOPQIBBggqhkjO
PQMBBwNCAAR7RHyY9zEzevvjuslueTrxKGXzvVa2R6Fyl2QZGuER8xYbTVb6QvJu
Gxjdh/nbQvTJFo5CDizl4tFJZI7g7l+0o0MwQTAPBgNVHRMBAf8EBTADAQH/MA8G
A1UdDwEB/wQFAwMHBgAwHQYDVR0OBBYEFB5vxNDA2gBKhCfLvT/gWpnqLS0RMAoG
CCqGSM49BAMCA0cAMEQCIAb5mzrOAAB7+3F3hN3SMAE9jNygur4g7gADm+oImKbU
AiAP+vneYcG2vSi/XdsaGR5jsi6tSmlGjVIixIfVPDPCBA==
-----END CERTIFICATE-----
```

This certificate was generated using
```bash
certtool --generate-self-signed --load-privkey ca.key --template ca.template --outfile ca.crt
```
The certificate was then converted to DER using
```bash
certtool --certificate-info --infile ca.crt --outder --outfile ca.der
```

### Certificate Authority Secret Key

This key is contained in `ca.key`.
```
-----BEGIN EC PRIVATE KEY-----
MHgCAQEEIQCTkdqaGrni3qj8I+zeAZOX6ZF0H6tEye/HxXeH1+6dP6AKBggqhkjO
PQMBB6FEA0IABHtEfJj3MTN6++O6yW55OvEoZfO9VrZHoXKXZBka4RHzFhtNVvpC
8m4bGN2H+dtC9MkWjkIOLOXi0UlkjuDuX7Q=
-----END EC PRIVATE KEY-----
```

This key was generated using
```bash
certtool --generate-privkey --ecc --outfile ca.key
```

## Alice's End-Entity Certificate

This certificate is contained in `alice.crt`.
```
-----BEGIN CERTIFICATE-----
MIIBqTCCAVCgAwIBAgIUTjAZVIQpook9BLjtuhQ7j30XsnYwCgYIKoZIzj0EAwIw
LDEqMCgGA1UEAxMhU2FtcGxlIENPU0UgQ2VydGlmaWNhdGUgQXV0aG9yaXR5MCAX
DTIwMTIwMjE3MjcyNVoYDzIwNTMxMDEwMTcyNzI1WjAZMRcwFQYDVQQDEw5BbGlj
ZSBMb3ZlbGFjZTBZMBMGByqGSM49AgEGCCqGSM49AwEHA0IABIY6p7wDJnFqpZ21
v2bMZg0FkdUeSJG8Lmqbr/UHfZJ8rU7tSCp5hb4BnpsZNsFuABkOi8xI7hLTX/if
D8egmcqjYTBfMAwGA1UdEwEB/wQCMAAwDwYDVR0PAQH/BAUDAweAADAdBgNVHQ4E
FgQUEVFVWwH/P23d+eVxKtP/cqLZTWIwHwYDVR0jBBgwFoAUHm/E0MDaAEqEJ8u9
P+BameotLREwCgYIKoZIzj0EAwIDRwAwRAIgOP+SB4crpNaFcAd0eD01vltFr1km
WoVnrpUtcYLVy6ACIBY6GDiO/mMQUXOFRYq007v3oMI9nIfaHPN4iE+7zchs
-----END CERTIFICATE-----
```

This certificate was generated using
```bash
certtool --generate-certificate --load-privkey alice.key --template alice.template --load-ca-certificate ca.crt --load-ca-privkey ca.key --outfile alice.crt
```
The certificate was then converted to DER using
```bash
certtool --certificate-info --infile alice.crt --outder --outfile alice.der
```

### Alice's Private Key Material

This key is contained in `alice.key`.
```
-----BEGIN EC PRIVATE KEY-----
MHgCAQEEIQDUIETrLNJpHpJtpIcc81Kd3sawNPgkul4FDSxwL5fHpaAKBggqhkjO
PQMBB6FEA0IABIY6p7wDJnFqpZ21v2bMZg0FkdUeSJG8Lmqbr/UHfZJ8rU7tSCp5
hb4BnpsZNsFuABkOi8xI7hLTX/ifD8egmco=
-----END EC PRIVATE KEY-----
```

This key was generated using
```bash
certtool --generate-privkey --ecc --outfile alice.key
```

