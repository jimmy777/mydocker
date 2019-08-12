# docker

## tomcat
https://hub.docker.com/_/tomcat
```
# docker run -d -P --name tomcat tomcat:9.0.21-jdk8
```

## mysql
https://hub.docker.com/_/mysql

```
download
# docker pull mysql:5.7

run
# docker run -d -P --name mysql -e MYSQL_ROOT_PASSWORD=abcd1234 mysql:5.7

mysql-client 
# docker run -it --name mysqlclient --link mysql:mysql mysql:5.7 bash

...# mysql -hmysql -uroot -pabcd1234



```


# docker-compose

http://get.daocloud.io/#install-compose

```
# curl -L https://get.daocloud.io/docker/compose/releases/download/1.24.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose

# chmod +x /usr/local/bin/docker-compose

# docker-compose version
docker-compose version 1.24.1, build 4667896b
docker-py version: 3.7.3
CPython version: 3.6.8
OpenSSL version: OpenSSL 1.1.0j  20 Nov 2018
```






### ES
- $ docker network create es
- $ docker run -d --name es --net es -p 9200:9200 -p 9300:9300 -e "discovery.type=single-node" -e ES_JAVA_OPTS="-Xms512m -Xmx512m" elasticsearch:6.8.1

```
[root@node100 ~]# curl -sL 'localhost:9200/_cat/health?v'

[root@node100 ~]# curl -sL 'localhost:9200/_cat/nodes?v'

[root@node100 ~]# curl -sL 'localhost:9200/_cat/indices?v'

[root@node100 ~]# curl -XPUT 'localhost:9200/customer?pretty'

[root@node100 ~]# curl -XPUT 'localhost:9200/customer/external/1?pretty'  -H "Content-Type: application/json" -d '
{
  "name": "John Doe"
}'


[root@node100 ~]# curl -XGET 'localhost:9200/customer/external/1?pretty'
[root@node100 ~]# curl -s -XGET 'localhost:9200/customer/external/1?pretty'| python -mjson.tool
[root@node100 ~]# curl -s -XDELETE 'localhost:9200/customer?pretty'



```

```
$ jq . <<< '{ "foo": "lorem", "bar": "ipsum" }'
{
  "bar": "ipsum",
  "foo": "lorem"
}
Or in other words:

$ echo '{ "foo": "lorem", "bar": "ipsum" }' | jq .
{
  "bar": "ipsum",
  "foo": "lorem"
}
```

```
#!/usr/bin/python

"""
Convert JSON data to human-readable form.

Usage:
  prettyJSON.py inputFile [outputFile]
"""

import sys
import simplejson as json


def main(args):
    try:
        if args[1] == '-':
            inputFile = sys.stdin
        else:
            inputFile = open(args[1])
        input = json.load(inputFile)
        inputFile.close()
    except IndexError:
        usage()
        return False
    if len(args) < 3:
        print json.dumps(input, sort_keys = False, indent = 4)
    else:
        outputFile = open(args[2], "w")
        json.dump(input, outputFile, sort_keys = False, indent = 4)
        outputFile.close()
    return True


def usage():
    print __doc__
```

```

On *nix, reading from stdin and writing to stdout works better:

#!/usr/bin/env python
"""
Convert JSON data to human-readable form.

(Reads from stdin and writes to stdout)
"""

import sys
try:
    import simplejson as json
except:
    import json

print json.dumps(json.loads(sys.stdin.read()), indent=4)
sys.exit(0)
```

```
sudo gem install json
echo '{ "foo": "bar" }' | prettify_json.rb
```

```
Pretty print web service responses like so:

curl -s -L http://<!---->t.co/tYTq5Pu | jsonpp
and make beautiful the files running around on your disk:

jsonpp data/long_malformed.json
```

ref:
- https://stackoverflow.com/questions/352098/how-can-i-pretty-print-json-in-a-shell-script
- http://jimpravetz.com/blog/2010/11/curl-json-and-pretty-print/


