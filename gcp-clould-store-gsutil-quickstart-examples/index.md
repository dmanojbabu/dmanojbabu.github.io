# GCP: Cloud Store gsutil QuickStart Examples


GCP Cloud Store gsutil command line tool quickstart examples.

<!--more-->

## Synopsis

The gsutil tool helps to access Clould Storage and perform operations on bucket.
- Bucket – A top-level folder.
- Prefix – An folder in a bucket.
- Object – Any item that's stored in an Cloud Storage bucket.

## 1 Basic operations

The following basic operations can be performed on buckets in Cloud Storage.

### 1.1 Creating Bucket

gsutil provides a `gsutil mb` command to make buckets.

- `gsutil mb gs://<bucket-name>` command to create bucket.

### 1.2 Listing Buckets, Subdirectories and Objects

gsutil provides a `gsutil ls` command to list buckets, sub-directories and objects.

- `gsutil ls` to list all buckets.
- `gsutil ls gs://<bucket-name>` to list objects at the top level of each bucket.
- `gsutil ls gsutil ls gs://<bucket-name>/*.csv` to list objects at the top level of each bucket.

### 1.3 Delete Buckets and Objects

gsutil provides a `gsutil rm gs://<bucket-name>/<filepath>` command to delete buckets or objects.

- `gsutil rm gs://bucket/subdir/*` remove all objects in gs://bucket/subdir
- `gsutil rm gsutil rm gs://bucket/subdir/**` remove all objects in gs://bucket/subdir or subdirectories
- `gsutil rm -r gs://bucket` to delete all objects in the bucket and the bucket itself.
- `gsutil rm gs://bucket/**` to delete all objects in the bucket but not the bucket itself.

### 1.4 Move Buckets and Objects

gsutil provides a `gsutil mv` command to move date between your file system and the cloud.

- `gsutil mv <src-filepath> gs://<bucket-name>/<directory>/<dest-filepath>` command used to move from local to bucket in cloud.
- `gsutil mv gs://<bucket-name>/<directory>/<src-filepath>` <dest-filepath> command used to move from bucket in cloud to local.

### 1.5 Copy Buckets and Objects

gsutil provides a `gsutil cp` command to copy date between your file system and the cloud.

- `gsutil cp <src-filepath> gs://<bucket-name>/<directory>/<dest-filepath>` command used to copy from local to bucket in cloud.
- `gsutil cp gs://<bucket-name>/<directory>/<src-filepath>` <dest-filepath> command used to copy from bucket in cloud to local.
