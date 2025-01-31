<link href="../../../style.css" rel="stylesheet"></link>

# 🧠 3.8 AWS CLI Example

## 🟥 Instructions

* This example will use the AWS CLI to create a new bucket, and recursively copy `sales-docs` directory
* Using the low level `s3api` CLI (which should be installed along with AWS CLI package), you'll check for the current life cycle configuration of your new bucket with the `get-bucket-lifecycle-configuration` subcommand, specifying your bucket name. This will return an error since there currently is no configuration.
* Next, you'll run the `put-bucket-lifecycle-configuration` subcommand, specifying the bucket name. 
* You'll also add some JSON code to the `--lifecycle-configuration` argument. The code will transition all objects using the sales-docs prefix to the Standard-IA after 30 days and to Glacier after 60 days. The objects will be deleted after a full year.
* Finally, you can run the `get-bucklet-lifecycle-configuration` command to confirm that your configuration is active.
* Here are the commands you will need to run to make this work:
   ```yaml
   $ aws s3 mb s3://bucket-name
   $ aws s3 cp --recursive sales-docs/ s3://bucket-name
   $ aws s3api get-bucket-lifecycle-configuration --bucket bucket-name
   $ aws s3api put-bucket-lifecycle-configuration
   --bucket bucket-name
   --lifecycle-configuration '{
      "Rules": [
         {
            "Filter": {
            "Prefix": "sales-docs/"
         },
      "Status": "Enabled",
      "Transitions": [
         {
            "Days": 30,
            "StorageClass": "STANDARD_IA"
         },
         {
            "Days": 60,
            "StorageClass": "GLACIER"
         }
      ],
      "Expiration": {
         "Days": 365
      },
      "ID": "Lifecycle for bucket objects."
         }
      ]
   }'
   $ aws s3api get-bucket-lifecycle-configuration
   --bucket bucket-name 
   ```

## 🟥 Running the Commands
* I create a new bucket called `shiv-3-8-bucket`:
   ```yaml
   $ aws s3 mb s3://shiv-3-8-bucket --profile default

   make_bucket: shiv-3-8-bucket
   ```

* I then upload all the [content of chapter of this repo](../.)
   ```yaml
   $ aws s3 cp --recursive . s3://shiv-3-8-bucket --profile default


   upload: c_3_9_summary\README.md to s3://shiv-3-8-bucket/c_3_9_summary/README.md
   upload: c_3_2_s3_service_architecture\README.md to s3://shiv-3-8-bucket/c_3_2_s3_service_architecture/README.md
   upload: .\README.md to s3://shiv-3-8-bucket/README.md
   upload: c_3_8_aws_cli_example\README.md to s3://shiv-3-8-bucket/c_3_8_aws_cli_example/README.md
   upload: c_3_1_introduction\README.md to s3://shiv-3-8-bucket/c_3_1_introduction/README.md
   upload: c_3_7_other_storage_services\README.md to s3://shiv-3-8-bucket/c_3_7_other_storage_services/README.md
   upload: c_3_5_accessing_s3_objs\README.md to s3://shiv-3-8-bucket/c_3_5_accessing_s3_objs/README.md
   upload: c_3_6_s3_glacier\README.md to s3://shiv-3-8-bucket/c_3_6_s3_glacier/README.md
   upload: c_3_4_s3_object_life_cycle\README.md to s3://shiv-3-8-bucket/c_3_4_s3_object_life_cycle/README.md
   upload: c_3_3_s3_durability_availability\README.md to s3://shiv-3-8-bucket/c_3_3_s3_durability_availability/README.md
   PS C:\Users\shiv.kumar\Documents\Github\New folder\AWS-Solutions-Architect-Revision-Notes\chapters\chap03-aws-storage>
   ```

* I confirm no configuration is present:
   ```yaml
   $ aws s3api get-bucket-lifecycle-configuration --bucket shiv-3-8-bucket --profile default

   An error occurred (NoSuchLifecycleConfiguration) when calling the GetBucketLifecycleConfiguration operation: The lifecycle configuration does not exist
   ```

* I then apply the configuration:
