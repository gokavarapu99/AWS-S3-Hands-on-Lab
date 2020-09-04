# AWS-S3-Hands-on-Lab
Create a bucket in Amazon S3
Add an object to the bucket

Add an object to the bucket
Use the provided image file in the instructions and use the AWS S3 management console to upload the image to the Amazon S3 bucket you've just created.


Manage Access Permissions On An Object
Once you've uploaded the object to your Amazon S3 bucket. Next you'll want to use the permissions tab to set the object as public.


Enable Bucket Versioning
Bucket versioning is a great tool for backups and recovery of objects. This check ensures that you have enabled bucket versioning


Lab Guidelines:

Introduction to Amazon S3
In this Learning Activity, we are going to learn how to work with Amazon S3 buckets. Start by signing in to your lab environment using the provided username and password. Once you are logged in, search for 'S3' under AWS Services - this will take you to the Amazon S3 homepage.

Creating an S3 Bucket
Click on the Create bucket button, enter your DNS-compliant bucket name into the 'Bucket name' space provided.

Note: Bucket names must be globally unique. This means that if an AWS s3 user has a bucket named 'my-bucket-15556', nobody else can create and name a bucket called 'my-bucket-15556'.

Select the Region in which you want your bucket to be stored. For instance, us-east-1 (N. Virginia). Leave the 'copy settings from an existing bucket' section blank, since we do not have any existing bucket. Click Next to proceed to the Set properties page. Click Versioning, select Enable Versioning, then Save.

Click the Next button again to proceed to 'Set Permissions' page. We want to leave the bucket as private, so we do not change 'Manage public permissions'. We will also not modify the 'Manage System permissions'. Click on Next to proceed to the Review page. Review all the bucket settings and click on Create bucket.

Upload an Object to Amazon S3
Start by downloading the file fountain.jpg from the learning activity description to your computer.

Go back to the AWS S3 homepage and click on the name of your bucket 'my-bucket-15556' (or the name that you entered), Select Upload and click on Add files. Navigate to the directory where you saved the fountain.jpg file and select it. Click Next to proceed to Set Permissions page, leave all settings here as default and click on Next to proceed to the Storage Class page. We'll leave everything under Storage class as default and click on Next to review the settings. Click Upload.

Select the uploaded file fountain.jpg from the bucket dashboard and a window will pop up at the right-hand corner displaying all of the configured properties of the file.

Click on the S3 public link provided under Overview to view the content of the file. You should get an 'Access denied' message.

Creating Read Permission on an Object
Select the object fountain.jpg, right click on the object, scroll down and select Make Public. A small window will pop up. Confirm by clicking on Make Public.

Navigate back to the object page, click on the object fountain.jpg and click on the public link. You should see a beautiful picture of a fountain.

Showing the Different Versions
Again, click the object fountain.jpg, under the Overview tab, select Show (next to Version) to display the versions of the object. Right-click on fountain.jpg and select Delete. Navigate back to the show version to view the different versions that existed.

Right-click on the first version, select Download and save it to your computer.

We can now go back to the bucket and confirm that fountain.jpg has been deleted. Since we were able to download it via versioning, we can re-upload the file again. Click Upload, navigate to the directory where you saved the downloaded file, select the file, fountain.jpg, and click Next through to review and click Upload file.

Select fountain.jpg and click on the S3 public link to view the content. This time, you should get an 'Access denied' message.

Re-Setting the Public Permission
Click on the object fountain.jpg, under the Overview tab, and select Make Public to set the public permission. Navigate back to the bucket home page, click your bucket and select Show Version. You should see the first version, the delete marker and the latest version.

Applying a Bucket Policy
Next, we will learn how to set bucket policies to Amazon S3 buckets. In our example, we'll provide anonymous access to the bucket.

Click the link in the instructions of this activity to take you to a GitHub page. Open it up and copy the text.

Navigate back to Amazon S3 management console. Click on S3 and click the bucket name. A small pop up window will appear on the right corner. Select Permissions and click on Bucket policy. Paste in the prior text copied from the GitHub page. Modify the Resources part of the policy by coping and pasting the ARN for the bucket and hit Save.

You should get a warning notification prompting you that any object in your bucket will be public.

Let's go back into the bucket and upload another file. Select the bucket name, click on Upload, rename the old file to fountain-new.jpg, and upload it. Now click on fountain-new.jpg and then click on the public link. You should see the beautiful fountain picture again!



#Creating a Basic Amazon S3 Lifecycle Policy




Introduction
AWS Glacier is a long-term archive storage service that provides lower-cost storage than other AWS storage options. When data has not been accessed for a certain period of time, it can be moved automatically between S3 storage classes using a lifecycle policy. In this lab, we will create a basic Amazon S3 lifecycle policy.

Solution
Log in to the AWS Management Console using the credentials provided on the lab instructions page. Make sure you're using the us-east-1 region.

Feel free to download the pinehead.jpg file if you'd like to upload it to the folder we'll create.

Create an S3 Bucket and Upload an Object
Navigate to S3.
Click Create bucket.
For Bucket name, type "lalifecycle". (Since bucket names must be globally unique, add a series of random numbers at the end.)
Un-check Block all public access.
Check to acknowledge that the current settings might result in the bucket and the objects within it becoming public.
Click Create bucket.
Click the name of the bucket to open it, and then click + Create folder.
Name the folder "MyProject", and click Save.
Open the folder, and click Upload.
Upload any file you'd like (which could be the pinehead.jpg file if you downloaded that from GitHub).
Click Next.
Under Manage public permissions, select Grant public read access to this object(s).
Click Next > Next > Upload.
Create a Lifecycle Policy
Click the bucket name at the top of the page.
Select the Management tab.
Click + Add lifecycle rule.
Name the rule "s3toGlacier".
Under Choose a rule scope, select Apply to all objects in the bucket.
Click Next.
On the Storage class transition screen, check the boxes next to Current version and Previous versions.
Next to For current versions of objects, click + Add transition, and set the following values:
Object creation: Transition to Glacier after
Days after creation: 30 days
Check to acknowledge that this lifecycle rule will increase the one-time lifecycle request cost if it transitions small objects.
Next to For previous versions of objects, click + Add transition, and set the following values:
Object becomes a previous version: Transition to Glacier Deep Archive after
Days after objects become noncurrent: 15 days
Check to acknowledge that this lifecycle rule will increase the one-time lifecycle request cost if it transitions small objects.
Click Next.
On the Configure expiration screen, check Previous versions.
With Permanently delete previous versions checked, type "365" in to indicate they should delete after 365 days from becoming a previous version.
Click Next.
Check the box to acknowledge the lifecycle rule will apply to all objects in the bucket.
Click Save.

#Creating Amazon S3 Buckets, Managing Objects, and Enabling Versioning

Create an Amazon S3 Bucket with Public Access Enabled
Create Public Bucket
Navigate to S3.
Click + Create bucket.
For Bucket name, type "lapublic". (Since bucket names must be globally unique, add a series of random numbers at the end.) Click Next.
Leave the versioning settings as-is, and click Next.
On the configuration options screen, ensure that Block all public access is unchecked. Click Next.
On the permissions screen, ensure none of the checkmarks are selected — this includes individual ones and any group check mark.
Click Create bucket.
Create Private Bucket
Click + Create bucket.
For Bucket name, type "laprivate". (Since bucket names must be globally unique, add a series of random numbers at the end.) Click Next.
Leave the versioning settings as-is, and click Next.
On the configuration options screen, make sure Block all public access is checked. Click Next.
On the permissions screen, verify the private bucket creation fields that we just set up.
Click Create bucket.
Create a Folder and Upload File in Public Bucket
Click the public bucket to open it.
Click + Create folder
Give the folder a name of "images", and click Save.
Click the folder name, and then click Upload.
Click Add files to upload the pinehead.jpg file you downloaded at the start of the lab. Click Next.
Set Manage public permissions to Grant public read access to this object(s), and click Next.
Click Next and Upload.
Upload File to Private Bucket
Head back to the S3 dashboard.
Click the private bucket to open it.
Click Upload.
Click Add files to upload the same pinehead.jpg file. Click Next.
Click Next, Next, and Upload.
Once it's uploaded, click the listed Object URL, which should result in an error.
Enable Versioning on the Public Bucket and Validate Access to Different Versions of Files with the Same Name
Note: Before taking the following steps, rename the pineheadv2.jpg file to pinehead.jpg to achieve the same versioning results as the lab video.

Head back to the S3 dashboard.

Click the public bucket to open it.
Click the Properties tab.
Click into the Versioning box.
Check the circle to Enable versioning, and click Save.
Back in the Overview tab, click to open the images folder.
Click Upload, Add files, and upload the pinehead.jpg file.
Click Next, Next, and Upload.
Once it's uploaded, click Make public.
Click the Latest version link at the top to see there are two versions listed: the previous one and the one we just uploaded.

