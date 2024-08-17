Step 1: Create a Basic Static Website

Create two HTML files: index.html and error.html.
Step 2: Configure an S3 Bucket for Website Hosting

1. *Create a Bucket:*
    - Go to the S3 console in AWS.
    - Click "Create bucket".
    - Provide a unique bucket name and choose a region.
    - Uncheck "Block all public access".
    - Acknowledge that the bucket will be public.
    - Click "Create bucket".

2. *Upload Files:*
    - Click on your newly created bucket.
    - Click "Upload".
    - Upload index.html and error.html.

3. *Configure Bucket for Website Hosting:*
    - In your bucket, click the "Properties" tab.
    - Scroll down to "Static website hosting" and click "Edit".
    - Choose "Enable".
    - Set the index document to index.html.

*Set Permissions:*
    - Go to the "Permissions" tab of your bucket.
    - Scroll down to "Bucket policy" and click "Edit".
    - Add the following bucket policy to make the content publicly accessible:

json
{
    "Version": "2012-10-17",
    "Statement": [
       {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
        }
    ]
}

   - Replace YOUR_BUCKET_NAME with the name of your bucket.
   - Save changes.

### Step 3: Access Your Website


