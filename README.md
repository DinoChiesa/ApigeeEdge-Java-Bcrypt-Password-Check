# Java BCrypt Check

This directory contains the Java source code and pom.xml file required to
compile a simple Java callout for Apigee Edge, that performs a BCrypt password hash check.

## Disclaimer

This example is not an official Google product, nor is it part of an official Google product.

## Notes

There is one callout class, com.google.apigee.edgecallouts.BcryptCheck ,
which checks a plaintext password against a bcrypt hash.


## Example Usage

This is what the policy configuration looks like:

```
<JavaCallout name='Java-BcryptCheck'>
  <Properties>
    <Property name='hash'>{bcrypt_hash}</Property>
    <Property name='password'>{plaintext_password}</Property>
  </Properties>
  <ClassName>com.google.apigee.edgecallouts.BcryptCheck</ClassName>
  <ResourceURL>java://edge-bcrypt-password-check-1.0.1.jar</ResourceURL>
</JavaCallout>
```

There are two required properties:
* hash - the bcrypt hash
* password - the plaintext password to check against the hash

You can specify these with context variables using the curly-brace syntax shown above.

## BouncyCastle is a Runtime dependency

You need to insure the BouncyCastle JAR is installed in the apiproxy/resources/java directory.

See [the example API proxy included here](./bundle) for details. 

## License

This material is copyright 2018, Google Inc.
and is licensed under the Apache 2.0 license. See the [LICENSE](LICENSE) file.


## Bugs

There are no unit tests for this project.
