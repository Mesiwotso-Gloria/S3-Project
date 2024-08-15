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

## Disable Block Public Access Settings
Disabling Block Public Access on S3 buckets is typically done when you need to make content accessible to the public, such as for hosting websites, distributing files, or supporting legacy applications. While this configuration is sometimes necessary, it's crucial to carefully manage and monitor the data being exposed to ensure it aligns with your security and business requirements.

1. Click on the "Permissions" tab.
2. Scroll down to "Block public access" (bucket settings) section.
3. Click "Edit."
4. uncheck "Block all public access" box.
5. type "confirm."
6. Click "Confirm."

Your configuration should match the following:
![](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(379).png?raw=true)
![](


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

## Enabling Versioning on an S3 Bucket
1. Click on the "Properties" tab.
2. Scroll down to the "Bucket Versioning" section.
3. Click "Edit."
4. Select "Enable" to activate versioning.
5. Click "Save changes."
6. Ensure that the "Bucket Versioning" section now shows that 
   versioning is enabled.

Your configuration should match the following:
![](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(389).png?raw=true)
![](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(391).png?raw=true)
![](https://github.com/Mesiwotso-Gloria/S3-Project/blob/main/images/Screenshot%20(392).png?raw=true)

## Upload Your Website Files
1. Go to the "Objects" tab of your bucket.
2. Click "Upload" and select your website files (e.g., HTML, CSS, JavaScript).
3. Click "Upload" to upload your files.
![](

## Access Your Website
1. Go back to the "Properties" tab of your bucket.
2. In the "Static website hosting" section, note the "Bucket website endpoint."
3. Open the endpoint URL in your browser to view your website.
