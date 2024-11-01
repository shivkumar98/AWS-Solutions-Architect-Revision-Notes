<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.4 Object Life Cycle
* S3 workloads may involve archiving backups
* Maintaining previous archive versions is important, but you may want to delete and retire old versions to keep costs minimised.
* S3 lets you automatically do this with life cycle features

## 🟥 Versioning
* By default, S3 works the same ways as file systems in that if you try to save a file with the same name and path of an existing one, the existing one gets overwritten.
* You can enable versioning on buckets, this means older overwritten versions of an object are saved indefinitely.
* This can lead to archive bloat

## 🟥 Life Cycle Management
* On top of intelligent tiering, S3 classes have lifecycle management which let you to change S3 class after a set number of days.
* E.g. you could move files to the ultra cheap Glacier class for 365 days before being deleted.

* I completed [🏋️ Exercise 3.2 Enable Versioning and Life Cycle Management for an S3 Bucket 🏋️](../../../exercises/chap03/e_3_2/)