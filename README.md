
# PDF composer
PDF composer is a part of the ecosystem that allow you to generate signed PDF document from JSON data and HTML template. the ecosystem consists of 3 seperate services
* [PDF composer](https://www.google.com/) 
* [XML generator](https://www.google.com/)
* [PDF generator](https://www.google.com/)
## How it work?
PDF composer provide an API `yourdomain/compose`. It's going to grab all your data and pass it through [XML generator](https://www.google.com/) to generate signed XML file. After that, it's going to pass all your data plus a generated XML file to [PDF generator](https://www.google.com/) to generate  signed PDF file. Finally, you going to get response of a generated PDF file as Base64 encoded.

![example of a request](https://i.imgur.com/qbA1ndT.jpg)

## Configuration
To deploy an API you need to define your environment configuration in `config.yml`
```yml
env:
port: "8000" # define your port to deploy here

service:
xml-generator: "http://127.0.0.1:8080/genXML" # define your XML generetor API path here 
pdf-generator: "http://127.0.0.1:9000/genPDF" # define your PDF generetor API path here 

syslog:
server: "127.0.0.1" # define your syslog domain
port: "8000" # define your syslog port
```


## Contributors
* Realtime & Secure Technology Co., Ltd.
* beTECH
