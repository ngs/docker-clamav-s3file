docker-clamav-s3file
====================

[![Docker Automated build](https://img.shields.io/docker/automated/atsnngs/clamav-s3file.svg?maxAge=2592000)](https://hub.docker.com/r/atsnngs/clamav-s3file/)

Docker Container for Virus Scan S3 Objects with [ClamAV]

Taste with [eicar Anti-Malwate Test File]
------------------------------------

```sh
wget http://www.eicar.org/download/eicarcom2.zip
aws s3 cp eicarcom2.zip s3://mybucket/eicarcom2.zip

docker pull atsnngs/clamav-s3file:latest
docker run \
  -e AWS_ACCESS_KEY_ID=$AWS_ACCESS_KEY_ID \
  -e AWS_SECRET_ACCESS_KEY=$AWS_SECRET_ACCESS_KEY \
  atsnngs/clamav-s3file:latest \
  s3://mybucket/eicarcom2.zip \
  http://requestb.in/123456 \
  PATCH
```

Example Request Payload
-----------------------

```json
{
  "content_hash": "e4968ef99266df7c9a1f0637d2389dab",
  "content_size": 308,
  "status": "ng"
}
```

[ClamAV]: https://www.clamav.net/
[eicar Anti-Malwate Test File]: http://www.eicar.org/85-0-Download.html
