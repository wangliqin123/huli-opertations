**Deploying a frontend application to Amazon S3 ( Simple Storage Service)**
========================================================================

Your Scrum Master has an AWS IAM (Identity and Access Management) access, so you can use her/his Acces Key ID & Secret Acces Key.






----------

**Installing the AWS Command Line Interface**
-----------------------------------------
[Follow the steps](http://docs.aws.amazon.com/cli/latest/userguide/installing.html)

----------


**Quick Configuration**
-------------------

For general use, the aws configure command is the fastest way to set up your AWS CLI installation.

> **$ aws configure**
**AWS Access Key ID** [None]: EXAMPLEID
**AWS Secret Access Key** [None]: Ex2MPl4K4y
**Default region name** [None]: eu-central-1
**Default output format** [None]: just hit *ENTER*
 


----------


**Listing buckets**
-------------------
 - The following command lists all buckets.

	

> **$ aws s3 ls**
> 
> ![enter image description here](https://lh3.googleusercontent.com/a-8AQDhkCpoKtIdTN_KyQt4hU3wm6pq3MnjcgQFhnnDhmsgVmDlHOv8XOAYXvmHXzhqrjPaZzMEy=s0)


 - The following command lists all objects and folders (prefixes) in a
   bucket.
   
   

> **$ aws s3 ls s3://*bucket-name*** 
> 
> ![enter image description here](https://lh3.googleusercontent.com/-JL6THVLibFs/WiEiJIgv8II/AAAAAAAAAbA/Ll0Km6UVZ9Y0kghjxCgyldpLBA6LYQW5ACLcBGAs/s0/listing_buckets2.PNG)


----------


**Creating buckets**
----------------

 - Bucket names must be unique and should be DNS compliant. Bucket names
   can contain lowercase letters, numbers, hyphens and periods. Bucket
   names can only start and end with a letter or number, and cannot
   contain a period next to a hyphen or another period.

> **$ aws s3 mb s3://*bucket-name*** 
> 
> ![enter image description here](https://lh3.googleusercontent.com/-qj7pG4NjSJY/WiEk3wnRskI/AAAAAAAAAbQ/XopPxit97k0X5nCC8sYAoXv1j9cBwZPaACLcBGAs/s0/making-bucket.PNG) 


----------


**Removing buckets**
----------------

 - To remove a bucket, use the following command.

> **$ aws s3 rb s3://*bucket-name*** 
> 
> ![enter image description here](https://lh3.googleusercontent.com/-7JV5N43WHkA/WiEl262BEMI/AAAAAAAAAbg/aefRNQu6cwEjcMjSmcjgQW-z0-DutyCKQCLcBGAs/s0/remove_bucket.PNG) 

 - By default, the bucket must be empty for the operation to succeed. To
   remove a non-empty bucket, you need to include the ***- -force***
   option.

> **$ aws s3 rb s3://*bucket-name* - -force**


----------


**Managing objects**
----------------

 - The following example copies an object into a bucket. It grants read
   permissions on the object to everyone (public-read) .
  

> **Permission options:** 
>  - *private*
>  - *public-read*
>  - *public-read-write*
>  - *authenticated-read*
>  - *aws-exec-read*
>  - *bucket-owner-read*
>  - *bucket-owner-full-control*
> 
> **$ aws s3 cp file.txt s3://my-bucket/  *- - acl public-read*** 
> 
> ![enter image description here](https://lh3.googleusercontent.com/-n2Gar9nHT3Q/WiEvoL24uyI/AAAAAAAAAcE/7sqUzYc69o0xR4Kq9Ee7JF11jsLeDkLSwCLcBGAs/s0/upload_file.PNG) 

 


----------


**Delete object from bucket.**
--------------------------
To deleting object use ***rm*** command.

> **$ aws s3 rm s3://*my-bucket/path/MySubdirectory/MyFile3.txt*** 
> 
> ![enter image description here](https://lh3.googleusercontent.com/-Rgu2rbYKZz4/WiEwZK_o0CI/AAAAAAAAAcQ/QRcVbJgDeL8t_6gwV9IuGLw7j-WiCQwfwCLcBGAs/s0/delete_from+bucket.PNG) 

 

**Synchronizes the contents**
-------------------------


 
The ***sync*** command has the following form. Possible source-target combinations are:

		

>  **1. Local file system to Amazon S3**
>  **2. Amazon S3 to local file system**
>  **3. Amazon S3 to Amazon S3**

 
The following example synchronizes the contents of an Amazon S3  with
the local working directory ***sync*** updates any files that have a
different size or modified time than files with the same name at the
 destination.

 

> **$ aws s3 sync *[source] [target] [--options]*** 
> 
> ![enter image description here](https://lh3.googleusercontent.com/-pwFVJZFPT9c/WiFBs7r1icI/AAAAAAAAAdE/5c61QoAFiiks4UUufAsxJEeXto9nfw3kQCLcBGAs/s0/uploadwithsyncfromlocaltobucket.PNG)


----------


**To get more info from S3 commands visit:** [Amazon S3 commands](http://docs.aws.amazon.com/cli/latest/userguide/using-s3-commands.html)


----------


***Also you can ask for help from the Malachite® team***

*"We care about your applications!"*


