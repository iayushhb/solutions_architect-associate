# Encrypting S3 Objects -

## Types of Encryption : 
1. Encryption in Transit :
    - SSL/TLS
    - HTTPS
2. Encryption at Rest: Server-Side Encryption
    - SSE-S3: S3-managed keys, using AES 256-bit encryption
    - SSE-KMS: AWS Key Management Service-managed keys
    - SSE-C: Customer-provided keys
3. Encryption at Rest: Client-Side Encryption
You encrypt the files yourself before you upload them to S3.

> All Amazon S3 Buckets have encryption configured by default.
All objects are automatically encrypted by using server-side encryption with Amazon S3 managed keys(SSE-S3).
Applies to all objects in your S3 bucket.

Every time a file is uploaded to S3, a PUT request is initiated.
![Alt text](/Photos/put-request.png)

## Enforcing Server-Side Encryption using bucket policy
1. **x-amz-server-side-encryption** 

    If the file is to be encrypted at the upload time, the `x-amz-server-side-encryption` parameter will be included in the request header.
2. You get 2 encryption types : 

    `x-amz-server-side-encryption : AES256`
    (SSE-S3- - S3-Managed keys)

    `x-amz-server-side-encryption : aws:kms`
    (SSE-KMS -- KMS-Managed keys)
3. **PUT Request Header**

    When this parameter is included in the header of the PUT request, it tell S3 to encrypt the object at the time of upload, using the specified encryption method.

![Alt text](/Photos/put-req.png)
> If you want to change the encryption type of any object then just go to the object in the bucket and scroll down and you'll see `Server-side encryption settings`.