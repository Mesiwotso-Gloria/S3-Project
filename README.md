# Static website in Amazon S3
## Overview
This tutorial walk you through how to set up a static website using Amazon S3. It allows you to host a website with AWS, providing high availability and scalability.

Errors or corrections? Contact
mesiwotsodakpah@gmail.com 

## Create an S3 Bucket
1. Go to the Amazon S3 Console.
2. Click on "Create bucket."
3. Enter a global unique bucket name and select a region.
4. Click "Create bucket" to complete the process.

If succesful,your confirmation message should match what is below:
![Diagram](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot.png?raw=true)

## Configure Bucket for Static Website Hosting
1. Navigate to your bucket in the S3 Console.
2. Go to the "Properties" tab.
3. Scroll down to the "Static website hosting" section.
4. Click "Edit."
5. Select "Enable."
6. For "Index document," enter the name of your main HTML file (e.g., index.html).
7. Optionally, specify an "Error document" if you have one (e.g., 404.html).
8. Click "Save changes."

Your configuration should match the following:
![Diagram](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(389).png?raw=true)
![Diagram](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(372).png?raw=true)
![Diagram](
https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(373).png?raw=true)
![Diagram](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(374).png?raw=true)

## Set Bucket Policy for Public Access
1. Go to the "Permissions" tab of your bucket.
2. Click "Bucket Policy."
3. Add the following policy to allow public read access to your files:
   
```json
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

```
Replace YOUR_BUCKET_NAME with your actual bucket name.
4. Click "Save."

