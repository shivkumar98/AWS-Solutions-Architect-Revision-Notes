<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.3 S3 Durability and Availability
* S3 offers multiple storage classes which offer various levels of durability (avoid corruption) and availability (how fast you can obtain)

## 🟥 Durability
* Durability is measured as a percentage. For instance, the `99.999999999%` durability guarantee for most S3 classes and Amazon S3 Glacier.
* This is equivalent of 0.000000001% of data loss on annual average. E.g. You will incure a loss of a single object once every 10,000 years.
* Even with this extremely robust storage of data, data should be backed up to other platforms to cover scenarios like misconfiguration, external attacks, account lockout.
* S3 data is replicated accross multiple AZ except for `S3 One Zone-IA` which is single zone - hence data has lower availability

## 🟥 Availability
* Availability is a measure of the amount of time an object would be instantly available on request in a year.
* The Standard S3 class has 99.99% availability.  I.e. in a year, you will only have 9 hours of downtime. AWS will give you service credit if they do not meet this agreement.
* S3 Intelligent-Tiering is a class which can help you save money while optimising availability. This is amonthly cost service which has the same availability as the Standard S3 class

## 🟥 Eventually Consistent Data 
* Due to S3 replicating data across multiple regions, there may be delays while propogating objects across the systemm.
* Uploading a new file could lead to one region having an outdated version of a file.
* Due to this, storage should be treated as eventually consistent. 
* Since there is no risk of corruption, S3 provides read-after-write consistency for PUT operations.