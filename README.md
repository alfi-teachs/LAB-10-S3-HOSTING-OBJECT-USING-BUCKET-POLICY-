# LAB-10-S3-HOSTING-OBJECT-USING-BUCKET-POLICY-

Use a bucket policy to make objects public and access objects using URL

# Step 1: Create S3 Bucket

Go to AWS Console → S3

Click Create bucket

Enter:

Bucket name (must be unique)

Region (any)

Enable Versioning

Keep rest default

Click Create bucket

# Step 2: Upload Object

Open your bucket

Click Upload → Add files

Upload any file (image / HTML)

Click Upload

# Step 3: Disable Block Public Access

Go to Permissions tab

Scroll to Block public access

Click Edit

Uncheck:

Block all public access

Save changes

Confirm (type “confirm”)

# Step 4: Add Bucket Policy

In Permissions → Bucket Policy

Paste this policy:

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}



{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadAccess",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
    }
  ]
}


👉 Replace:

YOUR-BUCKET-NAME with your actual bucket name

Click Save

# Step 5: Access Object

Go to your uploaded file

Click the object

Copy Object URL

Paste in browser

👉 Now your file should open publicly

# Important Concept (Very Important)

Block Public Access OFF → allows public access

Bucket Policy → actually grants permission

Both are required

Common Mistakes

Forgot to replace bucket name in ARN

Block public access still ON

Wrong action (must be s3:GetObject)

Missing /* at end of ARN

# Final Result

You successfully:

Created S3 bucket

Enabled versioning

Uploaded object

Made it public using policy

Accessed it via URL
