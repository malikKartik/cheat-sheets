### Setting up elasticsearch in docker

```docker pull elasticsearch:7.14.1```


```docker run -d --name elasticsearch --net somenetwork -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" elasticsearch:7.14.1```
