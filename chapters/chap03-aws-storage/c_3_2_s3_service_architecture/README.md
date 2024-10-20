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

## 🟥 Logging



### 🟡 H3