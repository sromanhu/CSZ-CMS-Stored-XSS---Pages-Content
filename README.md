# CSZ CMS Stored XSS v1.3.0

## Author: (Sergio)

**Description:** CSZ CMS 1.3.0 is affected by a Stored Cross-Site Scripting (XSS) vulnerability that allows attackers to execute arbitrary code via a crafted payload to the Additional Meta Tag parameter in the Pages Content Menu that will appear both on the main page and on the subpages. 

---

### POC:


When logging into the panel, we will go to the "Pages Content" section off General Menu [(http://localhost/cszcms/admin/pages)]

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Pages-Content/assets/87250597/06e7b1a7-8a72-40c6-bc12-d5e766e98e80)






We edit the Content of /home and see that we can inject arbitrary Javascript code into the Additional Meta tag field.


### XSS Payload:

```js
<img src=1 onerror=alert("1")
```



In the following image you can see the embedded code that executes the payload in the main web /home with the admin user:

![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Pages-Content/assets/87250597/5b957c84-17c9-4a1c-8c42-b5b7e4841c04)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Pages-Content/assets/87250597/8b7d56e0-056a-4afb-8d5c-9b8f1fb2a088)




If we log in with another user, the payload also skips:
![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Pages-Content/assets/87250597/23a21328-0958-4238-ae19-9bbef4f5db06)


![image](https://github.com/sromanhu/CSZ-CMS-Stored-XSS---Pages-Content/assets/87250597/341f4853-8b72-492d-8d12-5c86a9ae095f)




</br>
