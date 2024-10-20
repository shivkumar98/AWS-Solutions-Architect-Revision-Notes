<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.2 S3 Service Architecture
* S3 files are organised in buckets (you can think of them as directories), you can have up to 100 buckets to your account by default (which can be raised).
* An S3 bucket and its contents is only accessible to one region, gowever the name of the bucket must be 🌎globally unique🌎
* Here is an example URL that would let you access a file in a bucket over HTTP: `s3.amazon.com/bucketname/filename`
* This how the file would be addressed via CLI: `s3://bucketname/filename`

## 🟥 Prefixed and Delimiters
* S3 stores objects in flat structure without subfolder hierarchy. You can use prefixed and delimiters to give the illusion of structure
* E.g. you could use `/` delimiter to emulate folder directories.

## 🟥 Working with Large Objects
* There is no size limit for how much a bucket can store, however there is a 5TB limit on a single object
* There is a 5GB limit on a single upload
* You can use multipart upload to upload documents up to 5TB
* AWS offers low-level and high-level APIs for S3 uploads.

## 🟥 Encryption
* Most of the time you want your S3 contents not to be publicly accessible
* You would also want the contents to be encrypted, which it is, data can only be decrypted at Amazon's API endpoints
* Data is either clients-side or server-side encrypted

### 🟡 Server-Side Encryption
* The server side is the S3 platform, AWS encrypts the data as it gets stored, and decrypt when requested from a properly authenticated endpoint.
* There are three encryption options:
1. **Server-Side Encryption with Amazon S3-Managed Keys (SSE-S3)**, in which AWS uses its own keys to managed every facet of the encryption/decryption process.
2. **Server-Side Encryption with AWS KMS-Managed Keys (SSE-KMS)**, where an envelope key is added along with a full audit trail for tracking key usage. You can optionally import your keys through the AWS KMS service
3. **Server-Side Encryption with Customer-Provided Keys (SSE-C)** which uses your own keys for S3 to apply encyption

### 🟡 Client-Side Encryption
* The client could do the encryption themselves, this can be done using Managed Customer Master Key (CMK) from AWS KMS.
* You could also use a Client-Side Master key which is provided through Amazon S3 encryption client.
* Server-side encryption is generally preferreed as it is less complicated.

## 🟥 Logging
* Logging events from S3 buckets is disabled by default.
* If you decide to enable logging, you will specify  the source bucket and a target bucket (where the logs will be stored)
* S3 generated logs will contain operation details, including:
   - The account and IP odf the requestor
   - Source bucket namme
   - Action request type (PUT, GET, POST, DELETE, etc)
   - Time of request
   - Response status
* S3 buckets are also used for logs of other AWS service like CloudWatch
