# JAVA_awsS3
## Select Bucket List
```
final String KEY = Const.AWS_KEY_ID;
final String SECRET = Const.AWS_SECRET_ACCESS_KEY;

BasicAWSCredentials credentials = new BasicAWSCredentials(KEY, SECRET);
AmazonS3 s3Client = new AmazonS3Client(credentials);

ListObjectsV2Request listObjects = new ListObjectsV2Request().withBucketName("bucketname");
ListObjectsV2Result res = s3Client.listObjectsV2(listObjects);

for (S3ObjectSummary myValue : res.getObjectSummaries()) {
    Log.i("pskim","\n The name of the key is " + myValue.getKey());
    Log.i("pskim","\n The object is " + myValue.getSize() + " KBs");
}
```
