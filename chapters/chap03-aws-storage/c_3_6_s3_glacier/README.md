<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.6 Amazon S3 Glacier
* S3 Glacier appears like a storage class upon first look
* It guarantees 99.999999999 percent durability
* However it does differ from storage classes, such as Glacier's archives being encrypted by default (this is an option for S3 which needs to be selected), and the fact that keynames not being human readable.
* The key differentiator of Glacier from S3 is the retrieval time which can take hours, compared to nearly instant from S3.
* Glacier is much more inexpensive, making it ideal for long term stroage which need infrequent access

<br>

* The word ***archive*** means a document type like TAR or ZIP in the context of Glacier
* The S3 equivalent form of a bucket for Glacier is a **vault** - which do ❌NOT❌ have to be 🌎globally🌎 unique
* There are 3 **S3 Glacier Storage Classes**:
1. `Amazon S3 Glacier Instant Retrieval` - milliseconds retrieval
2. `Amazon S3 Glacier Flexible Retrieval` - 12 hours retrieval
3. `Amazon S3 Glacier Deep Archive` - 12-48 hours retrieval

<br>

* Here are the sample retrieval costs for Glacier data in the U.S. East Region:

| Tier | Amount Retrieved | Cost |
|------|------------------|------|
| Glacier Instant | 100GB | $3.00 |
| Glacier Flexible | 100GB | $1.00 |
| Glacier Deep Archive | 100GB | $2.00 |

## 🟥 Storage Pricing
* To understand the pricing differences between S3 and Glacier, I will run through a scenario for typical usage
* Imagine I have to make weekly backups of a company's sales data which generate 5GB archives.
* I decide to maintain each archive in the S3 Standard Storage class and Requests class for its first 30 days and then convert it to S3 One Zone, where it will remain for 90 more days. At the end of the total 120 days, you move archives once again to Glacier Instant, where it is kept for 2 years (730 days) and then gets deleted
* In a full cycle, there will be the following sizes stored in:
    - S3 Standard: 20GB
    - One Zone-IA: 65GB
    - Glacier Instant: 520GB
* Herer is the sample storage costs in U.S. East Region:

| Class | Storage Amount | Rate/GB/month | Cost/Month |
| ----- | -------------- | ------------- | ---------- |
| Standard | 20 GB       | $0.023        | $0.46      |
| One Zone-IA | 65GB     | $0.01         | $0.65      |
| Glacier Instant | 520GB| $0.004        | $2.08      |
| Total |                |               | $3.19      |
