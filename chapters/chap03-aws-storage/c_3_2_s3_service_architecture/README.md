<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.2 S3 Service Architecture
* S3 files are organised in buckets (you can think of them as directories), you can have up to 100 buckets to your account by default (which can be raised).
* An S3 bucket and its contents is only accessible to one region, gowever the name of the bucket must be 🌎globally unique🌎
* Here is an example URL that would let you access a file in a bucket over HTTP: `s3.amazon.com/bucketname/filename`
* This how the file would be addressed via CLI: `s3://bucketname/filename`

## 🟥 Prefixed and Delimiters


## 🟥 Working with Large Objects

### 🟡 H3