#### Data Transfer Service
1. On Premises to GCS
   1. Using command line utility
      1. Install Google cloud SDK
      2. gsutil -m cp large_number_of_small_files(-m for parallel upload)
   2. Transfer service for on-primises data
      1. This will securely and quickly move your data from private data center to GCS.
      2. Install an agent
      3. create a transfer job.
   3. Transfer Appliance
      1. Physical device which securely transfer large amount of data to GCP.
      2. When data that exceeds 20TB or would take more than a week to upload.
2. One bucket to another in GCS
3. Other cloud to GCS

#### Transfer Service
- for other two cases, we can use this to transfer data between different buckets or from other cloud to GCP.
- create a transfer job
- one time run or recurring 