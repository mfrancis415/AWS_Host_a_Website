# AWS Host A Website

Introducing Today's Project!</br>
In this project, I will demonstrate how to use S3 to host a static website. I'm doing this project to learn about AWS and cloud services and it can be used as storage and host websites.

- Tools and concepts: Services I used were Amazon S3. Key concepts I learnt include bucekt policies, uploading static website files, index.html, bucket endpoint URLs, and the ways ACLs control access to the bucket objects.

- Project reflection: This project took me approximately 45 minutes including the secret mission time. The most challenging part was resolving the error at the begining. It was most rewarding to seeing the website up and running and public.

## How I Set Up an S3 Bucket
Creating an S3 bucket took me took me less than 2 minutes. There were some concepts I needed to understand like block public access. The Region I picked for my S3 bucket was North Virgina because, it is the closet region to me. I learned that this is the best practice as it lowers the latency and cost. The S3 bucket names are globally unique! This means no two AWS S3 buckets can have the same name in the entire world. 

![Screenshot 2025-05-30 114312](https://github.com/user-attachments/assets/c4445fe7-9f2c-42d4-9ae4-97554929f2e9)

## Upload Website Files to S3
- index.html and image assets: I uploaded two files to my S3 bucket - they were folder of pictures & assets (this will fill in the website with pictures & things to look at) and index.html file (this determines the structure i.e. what goes inside the website). Both files are necessary for this project because the index file gives structure and directs what's in the website, while the folder of images provides the content.

![Screenshot 2025-05-30 123947](https://github.com/user-attachments/assets/74fcb839-2eed-4139-937d-b6df9a367d3b)

## Static Website Hosting on S3
Website hosting means putting our website file on a web server so that people can visit. To enable website hosting with my S3 bucket, I went into the properties tab of the
bucket, enabled static website hosting, and name index.html as the index document. An ACL (aka an Access Control List) is a set of rules that decides who can get access to a resource. We enable ACLs in order to control access to website files later. AWS reccommended disabling ACLs, but I kept it enabled to learn how ACLs work.


![Screenshot 2025-05-30 124613](https://github.com/user-attachments/assets/718393d2-11d2-4f54-9432-af78a2290167)

# Bucket Endpoints
Once static website is enabled, S3 produces a bucket endpoint URL, which is URL that takes me and everyone online to the website I am hosting. When I first visited the bucket endpoint URL, I saw error message stating my access is denied. The reason for this error was because the objects the website files are still completely private and settings need to be managed separately.

![Screenshot 2025-05-30 125055](https://github.com/user-attachments/assets/77702478-4969-455c-8cdb-5c12108443bb)

## Success!
To resolve this 403 Forbidden error, I went back to the Objects tab then selecting the check boxes next to the files I wanted to make public. Then clicked the actions button
and then selected make public using ACL.



![Screenshot 2025-05-30 130130](https://github.com/user-attachments/assets/bdda0b75-d2f4-4e0e-a48e-1ce44de9bd7e) 

# Bucket Policies
In this project extension, I’m about to use bucket policies to control access to our bucket’s files. I’m doing this so that people will not be able to delete the objects inside the file. An alternative to ACLs is bucket policies, which are rules that determine who is allowed or not allowed to do something.  The benefit of using bucket policies is I can have greater control of the actions that people are/aren’t allowed to do, while ACLs are useful for controlling public access to individual objects inside the bucket. My bucket policy denies everyone even me from deleting our index.html file. I tested this by trying to delete the index.html file and got an error message as my access was denied. The bucket policy was successful in denying the permission to deleting objects. 

![image](https://github.com/user-attachments/assets/42883b00-95ac-45f0-96c5-4a0af52ef6a5)

