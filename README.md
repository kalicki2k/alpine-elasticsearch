# Elasticsearch on Alpine Linux
This is a micro docker images based on Alpine Linux and Elasticsearch.

## Usage
To use this start the container on port 9200 with:
```bash
$ docker run -d --name elastic -p 9200:9200 kalicki2k/alpine-elasticsearch
```