# filecheckio
Malice [FileCheckIO](https://filecheck.io) Plugin

```python
import urllib, urllib2i, ssl, json 

def getFileInfo(fileName,fileSize,fileVersion,md5,sha1,sha256,sha512,apiKey): 
 	ctx = ssl.create_default_context() 
 	url = "https://filecheck.io/api" 
 	parameters = {"file": fileName, 
 	"size": fileSize, 
 	"version": fileVersion, 
 	"md5": md5, 
 	"sha1": sha1, 
 	"sha256": sha256, 
 	"sha512": sha512, 
 	"key": apiKey} 
 	data = urllib.urlencode(parameters) 
req = urllib2.Request(url, data) 
response = urllib2.urlopen(req, context=ctx) 
return response 

if __name__=="__main__": 
 	fileName='___FILENAME___' 
 	fileVersion='___FILEVERSION___' 
 	md5='___MD5___' 
 	sha1='___SHA1___' 
 	sha256='___SHA256___' 
 	sha512='___SHA512___' 
 	apiKey='___APIKEY___' 
 	fileSize='___FILESIZE___' 
 	fileStatus=getFileInfo(fileName,fileSize,fileVersion,md5,sha1,sha256,sha512,apiKey) 
 	fileStatusJson = json.loads(fileStatus.read()) 
 	print(fileStatusJson)
```
