# 🏋️ Exercise 3.3 Generate and Use a Presigned URL 🏋️

## ✏️ Description ✏️
1. Use the complete URL of a private object in an S3 bucket belonging to you to generate a presigned URL using variation of this command:
```
aws s3 presign s3://MyBucketName/PrivateObject --expires-in 600
```
3. Wait for the URL to expire and try again. This time, it should not work.
   
## ✅ Solution ✅

* I tried using the following 
```
   C:\Users\shiv.kumar>aws s3 presign s3://shiv-aws-demo-s3/gym.jpg --expires-in 120 --profile default
   https://shiv-aws-demo.s3.us-west-2.amazonaws.com/gym.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAQMX5TXAO7CLRNBVP%2F20241115%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20241115T112726Z&X-Amz-Expires=120&X-Amz-SignedHeaders=host&X-Amz-Signature=169ad1eb2f2004957d33688f9a90750f723e6e0ee81562139d754dfb9b8996f3
   ```

* This gave me a webpage like the following:
![](../screenshots/2024-11-15-12-07-47.png)

* It turns out the  commmand above no longer works for buckets created after 2020
* I had to specify the endpoint:
   ```
   aws s3 presign s3://shiv-aws-demo-s3/gym.jpg --expires-in 600 --region eu-west-2 --profile default
   ```
* This generated the following link: [https://shiv-aws-demo-s3.s3.eu-west-2.amazonaws.com/gym.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAQMX5TXAO7CLRNBVP%2F20241115%2Feu-west-2%2Fs3%2Faws4_request&X-Amz-Date=20241115T120132Z&X-Amz-Expires=600&X-Amz-SignedHeaders=host&X-Amz-Signature=b64f00c8a39fa891707b36cb1032f92d1935671598d31f5f86683b281941dc9f](https://shiv-aws-demo-s3.s3.eu-west-2.amazonaws.com/gym.jpg?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAQMX5TXAO7CLRNBVP%2F20241115%2Feu-west-2%2Fs3%2Faws4_request&X-Amz-Date=20241115T120132Z&X-Amz-Expires=600&X-Amz-SignedHeaders=host&X-Amz-Signature=b64f00c8a39fa891707b36cb1032f92d1935671598d31f5f86683b281941dc9f)
<br>
