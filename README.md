# Host a Website on Amazon S3

**Project Link:** [View Project](https://nextwork.ai/projects/70e2d059-31ab-5f67-8c58-f5edbd451140)

**Author:** Shubh Biswas  

---

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Introducing Today's Project!

### Project overview

I completed this project to apply my AWS knowledge to a practical use case, strengthen my understanding of S3 static website hosting, and learn how bucket policies control access to website files.

### Tools and concepts

The service I used was Amazon S3
Key concepts I learned include bucket policies, uploading static website files, index.html, bucket endpoint URLs, ACLs and how they control access to all bucket objects.

### Time, challenges, and wins

This project took me approximately 45 minutes.
The most challenging part was resolving the bucket policy error.
It was most rewarding to see the webpage finally load live.

## How I Set Up an S3 Bucket

### What I did in this step

In this step, we opened S3 and then created a storage space inside to start storing website files.

### How long it took to create the bucket

Creating an S3 bucket took me less than 5 minutes. I needed to learn a few concepts like 'block public access' and ACLs

### Region selection

I created my S3 bucket in the Mumbai Region because that's the region that's closest to me. It's best practice to pick the region closest to you because it lowers time to retrieve things i.e. latency

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means that no 2 Amazon S3 buckets in the entire world can have the same name. They have to be completely unique regardless of region or account.

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_ba6d42ad)

## Upload Website Files to S3

### What I did in this step

In this step, I uploaded the website files into my S3 bucket. This is important because without files, there is no website and my bucket is still empty.

### Files I uploaded

I uploaded two files to my S3 bucket - they were an index.html file (this determines the structure) and a folder of images and assets.

### How the files work together

Both files are necessary for this project as `index.html` determines the structure but the structure alone does not illustrate the contents of the website...that's where the contents folder, containing the images and assets, come in.

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_a265af88)

## Static Website Hosting on S3

### What I did in this step

In this step, I made my website available to the public. This is called Static Website Hosting and its important because my website files will stay as just files and not turn into a website if this step isn't done.

### Understanding website hosting

Website hosting makes my website files accessible through a web endpoint so that people can visit the website..

### How I enabled website hosting

To enable website hosting with my S3 bucket, I went into the properties tab of my bucket, enabled Static Website Hosting and labeled `index.html` as my index document (the document that serves as the website's homepage).

### Access Control Lists (ACLs)

An ACL (Access Control List) is a way to configure permission settings inside a bucket. I enabled ACLs so I can control access to my website files (objects) later.

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_c22c54c0)

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website hosting is enabled, S3 produces a bucket endpoint URL, which is a URL that takes you to the website that I am hosting. 

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 Forbidden Error.
The endpoint returned a 403 Forbidden error because the website objects did not have the required public read permissions. I needed to configure object access before the website could be viewed publicly.

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_22ce4daf)

## Success!

### What I did in this step

In this step, I made my website files public because this will enable us to view the contents of the website.
Once that is done, the website will be live

### How I resolved the 403 error

To resolve this 403 Forbidden error, I updated the access setting of the files inside the bucket too
Using ACLs, I made my objects (files inside the bucket) public.
When I checked my S3 bucket's website endpoint, the webpage loaded successfully.

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_5d4474f9)

## Bucket Policies

### What I did in this extension

In this project extension, I used bucket policies to control access to my bucket objects.
I'm doing this so that I can stop people from deleting the objects inside the bucket.

### Understanding bucket policies

An alternative to ACLs are bucket policies, which are rules that determine who is allowed or not allowed to do something.
Bucket policies define permissions for S3 resources, while ACLs provide a separate mechanism for managing access to buckets and objects.

![Image](https://nextwork.ai/motivated_orange_shy_paprika/uploads/70e2d059-31ab-5f67-8c58-f5edbd451140_sm2sm2sm)

### What my bucket policy does

My bucket policy explicitly denies deletion of the index.html file. I tested the policy by attempting to delete the file and confirming that AWS returned a permission-denied error.

---

**Note:** The AWS resources used for this project have been deleted after completion to avoid ongoing costs. The documentation and screenshots are retained here to demonstrate the implementation and configuration process.
