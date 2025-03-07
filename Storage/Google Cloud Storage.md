##### Google Cloud Storage
- Object storage solution in GCP
- Unstructured Data Storage
  - Images
  - Videos
  - Binary Files etc
- It can be used for long term archival storage
- can be accessed over http, Rest API
- No capacity planning required
  - can scale to Exabyte
- By default, Data is encrypted at rest/ in transit
- No minimum size
- Max object size is 5TB.
- High Durability
- Can be accessed Globally
- Single API to access across multiple storage class
- Data is geo-redundant
  - Due to multiregional
  - Dual-Region storage

- Global unique name for bucket
  - since bucket name will appear in URL.
- Inside bucket, you can create **folders** which are **virtual** and create/upload object.
- Bucket level lock with data retention policy.
- Objects are immutable.
- Objects can be versioned.

##### Storage Location

1. Region
   1. Lowest latency within a single region
   2. Data is replicated across multiple zones in single region
2. Dual Region
   1. High availability
   2. Low latency across 2 paired regions
   3. Auto fail over
3. Multi Region
   1. Highest availability across continent - US, EU and Asia
   2. Auto fail over
   
##### Storage Class

Depends on how frequently we access data

1. Standard
   1. Good for very frequently accessed data(Hot data).
   2. Storage is costlier
   3. Access cost is very low
   4. low latency
2. Near Line
   1. Less frequent access once in a 30days
   2. storage is cheaper than standard
   3. Access cost will increase
3. Cold Line
   1. Very less frequent access once in 90days
   2. storage cheaper than Near line
   3. Access cost will increase compared to Near line
4. Archive
   1. Offline data
   2. For backup purpose
   3. Data access is once in a year
   4. storage is cheaper
   5. Access cost is very high
   
##### Object Life Cycle Management

- Based on condition what action needs to perform on object.
- Condition
  - Object Age
  - Object file type
  - after some specific date
- Action
  - Transition to different storage class for high performance.
  - Like Standard to Near line
  - Cold line to Delete

##### Secure Data with Encryption
- Encryption
  - Google Managed Encryption keys
    - No configuration
    - Fully Managed
  - Customer Managed Encryption keys
    - Create keyring in Cloud KMS
    - key will be managed by customer like key rotation
  - Customer supplied Encryption Keys
    - we will generate key with openssl rand -base64 32
    - gsutil -enrypt with CSEK

#### Object Versioning
- Helps us to prevent accidental deletion of object.
- Enable/ Disable versioning at bucket level.
- Get access to older version with object key + version number
- If you dont need earlier version, delete it & reduce storage cost
- If you dont specify version number, always retrieves latest version.

#### Access Control
1. Uniform 
   1. all permissions can be modified at bucket level
2. Fine Grain
   1. At each object level, we can modify the permissions.