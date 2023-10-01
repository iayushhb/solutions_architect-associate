# Hosting a static website using Amazon S3
1. Create a new S3 bucket named s3-site-hosting.
2. Upload files such as html and css files.
3. Make bucket public using ACL.
4. Now to host this static website, go buckets > your bucket > properties , then scroll down to static website hosting. Now hit edit and enable static website hosting and fill index file name and error file name.
![Alt text](/Photos/static-host.png)
5. Now if you scroll down again then you'll see the URL of the hosted site.
![Alt text](/Photos/static-host-2.png)

## Another way of making your bucket public is by using bucket policy.
1. Go to buckets > your bucket > permissions then paste this.
```Json
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Sid": "PublicReadGetObject",
			"Effect": "Allow",
			"Principal": "*",
			"Action": [
				"s3:GetObject"
			],
			"Resource": [
				"arn:aws:s3:::BUCKET_NAME/*"
			]
		}
	]
}
```
replace from arn: to BUCKET_NAME with your bucket's ARN : `arn:aws:s3:::hosting-static-site-ayush`

2. Now hit save and done.