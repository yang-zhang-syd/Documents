### Retrieve crt file from remote services

```
openssl s_client -connect accounts.google.com:443 < /dev/null | sed -ne '/-BEGIN CERTIFICATE-/,/-END CERTIFICATE-/p' > google-oauth.crt
```

### Add crt to java trust store

```
keytool.exe -import -file google-oauth.crt -alias google-oauth-crt -keystore myTrustStore
```

### convert pem to crt 

```
openssl x509 -outform der -in adait.pem -out adait-cert.crt
```
