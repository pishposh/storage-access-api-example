# Storage Access API Example

## Usage

1. update /etc/hosts to include entries for 3 unique domains. for example:

```
127.0.0.1   www.parent-a.com
127.0.0.1   www.parent-b.com
127.0.0.1   sub-frame.example.com
```

2. start three local webservers; 1 for each parent, another for the sub-frame.. for example (using [http-server](https://github.com/indexzero/http-server)):

```
cd parent-a && http-server -p 8181 &
cd parent-b && http-server -p 8282 &
cd sub-frame && http-server -p 8888 &
```

3. load [www.parent-a.com](http://www.parent-a.com:8181) and [www.parent-b.com](http://www.parent-b.com:8282) in [Safari Developer Preview](https://developer.apple.com/safari/download/)

4. test storage from embedded sub-frame access www.parent-a.com and www.parent-b.com

5. clean up

```
ps aux | grep [h]ttp-server
kill -9 [pid...]
```