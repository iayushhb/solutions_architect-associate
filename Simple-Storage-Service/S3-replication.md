# Backing up Data with S3 Replication
Replication enables automatic, asynchronous copying of objects across Amazon S3 buckets. Buckets that are configured for object replication can be owned by the same AWS account or by different accounts. You can replicate objects to a single destination bucket or to multiple destination buckets. The destination buckets can be in different AWS Regions or within the same Region as the source bucket.
1. You can replicate objects from one bucket to another,
Versioning must be enabled on both the source and destination buckets.
2. Objects in an existing bucket are not replicated automatically,
Once replication is turned on, all subsequent updated objects will be replicated automatically. *Upload objects after turning on the replication*
3. Delete markers are not replicated by default, 
Deleting individual versions or delete markers will not be replicated.*If you delete an item in the source bucket then the object in the destination bucket will not be deleted*
>AWS announced a new Amazon S3 Batch Replication feature on 08
FEB 2022, which allows replication of existing objects to different buckets on demand. Note that new AWS products, services or features must be generally available (GA) for at least 6 months prior to it appearing on certification exams. Check the resources section of the lesson for more details.

## Replication Demo
1. Create a source bucket and a destination bucket and turn on versioning for both of 'em. And select a different region while creating the destination bucket.
2. Then go to Management sectin of your source bucket and create replication rules.
3. Now enter replication name and choose status enabled.
4. In source bucket section select apply to all objects.
5. In destination section select the bucket you want your data to be replicated.
6. Now in IAM role , select create new role or you can select another role.
7. You can change some other things but we're gonna leave it default. Now hit save.
8. Now after some time depending the location you selected you'll see your uploaded object that you uploaded after turning replication on.
9. However we didn't selected the delete the delete markers option therefore even if you delete your object from source bucket it will still be present in the destination bucket.