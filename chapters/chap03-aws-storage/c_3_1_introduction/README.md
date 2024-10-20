# 🧠 3.1 Introduction

* Amazon S3 (Simple Storage Service) is used by individuals, applications and other AWS services host their data
* It is an ideal platform for:
  - Maintaining backup archives, log files, and distaster recovery images
  - Running analytics on big data
  - Hosting static websites
* S3 gives cheap and reliable storage, and effectively offers unlimited *object storage*. Unlike instance store volumes whichh are *block storage*.
* ***Block level storage***, data on a physical device storage. The filesystem is responsible for allocating space for files.
* ***Object level storage*** provides a flat space for data. Thhis formmat offers simple access to any amount of data
* When files are written to S3, they're stored with up to 2KB of metadata, which is made up of keys that establish system details like data permissions.
* In this chapter, I will be learning the following:
  - How S3 objects are saved, managed and accessed
  - How to choose an S3 class based on durability, availability and cost.
  - How to incorporate AWS S3 Glacier for managing long term life cycles for storage.
  - What other AWS services exist to help with data storage and access operations.