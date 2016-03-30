# S3 File Uploader for Windows CLI.
Basic *file to Amazon-S3* uploader.

Features:
 - No need for Amazon AWS CLI
 - Works from your OS Windows desktop (command line)
 - Logs upload % progress to CLI screen.
 - It's executable (s3_percent_upload.exe)  - no need for Python install
 - It's 32 bit - it will work on any vanilla Windows.
 - Access keys are fed from CLI environment (not command line args)
 - Written using Python/boto/PyInstaller

##Version

OS|Platform|Version 
---|---|---- | -------------
Windows|64bit|[0.1.0 beta]

##Purpose

- Ad-hoc file upload to Amazon S3.
- Optional upload to Reduced Redundancy storage (not RR by default).
- Optional "make it public" after upload (private by default)
- Custom S3 Key (defaulted to transfer file name)

##Audience

Business Analysts, AWS Developers, DevOps, 

##Designated Environment
Pre-Prod (UAT/QA/DEV)

## Amazon S3 data upload price

 - It's free to upload file to Amazon S3.
 - Storage will cost you.


##Usage

```
## Upload file to S3.
##
## Upload % progress outputs to the screen.
##
Usage:
  set AWS_ACCESS_KEY_ID=<you access key>
  set AWS_SECRET_ACCESS_KEY=<you secret key>
  s3_percent_upload.exe <file_to_transfer> <bucket_name> [<s3_key_name>] [<use_rr>] [<public>]
        if <s3_key_name> is not specified, the filename will be used.
        --use_rr -- Use reduced redundancy storage.
        --public -- Make uploaded files public.

        Boto S3 docs: http://boto.cloudhackers.com/en/latest/ref/s3.html

```

##Environment variables

* Set the following environment variables:

```
set AWS_ACCESS_KEY_ID=<you access key>
set AWS_SECRET_ACCESS_KEY=<you secret key>
```

#Example 

##Upload file to Amazon-S3 Reduced Redundancy storage and make in Publicly accessible


* S3_RR_Public_upload.bat
```
set AWS_ACCESS_KEY_ID=<you access key>
set AWS_SECRET_ACCESS_KEY=<you secret key>
  
cd c:\tmp\S3_Uploader
s3_percent_upload.exe c:\tmp\data.zip test123 --use_rr -public

```
* resutl.log (S3_RR_Public_upload.bat > resutl.log)
```
Connecting to S3...
File size: 388.5KiB
Public = True
ReducedRedundancy = True
Uploaded 0 bytes of 397799 (0%)
Uploaded 24576 bytes of 397799 (6%)
Uploaded 49152 bytes of 397799 (12%)
Uploaded 73728 bytes of 397799 (18%)
Uploaded 98304 bytes of 397799 (24%)
Uploaded 122880 bytes of 397799 (30%)
Uploaded 147456 bytes of 397799 (37%)
Uploaded 172032 bytes of 397799 (43%)
Uploaded 196608 bytes of 397799 (49%)
Uploaded 221184 bytes of 397799 (55%)
Uploaded 245760 bytes of 397799 (61%)
Uploaded 270336 bytes of 397799 (67%)
Uploaded 294912 bytes of 397799 (74%)
Uploaded 319488 bytes of 397799 (80%)
Uploaded 344064 bytes of 397799 (86%)
Uploaded 368640 bytes of 397799 (92%)
Uploaded 393216 bytes of 397799 (98%)
Upload complete.
Your file is at: https://s3-website-us-west-2.amazonaws.com/test123/data.zip

Time elapsed: 2.54299998283 seconds

```




##Download
* [Master Release](https://github.com/alexbuz/S3_File_Uploader/archive/master.zip) -- `s3_percent_uploader 0.1.0`
