**getParents**
----
	Returns an array of structured parent data in JSON format.

* **Version History:**

	TASS v52.6 - Method Added

* **Version:**

	3

* **Permission:**

   Administration > LDAP/SAML Maintenance > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`user_code [string]` - One of a list of Student Code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    {
	    "parents":[
	        {
	            "000007":{
	                "splitFamily1":{
	                    "web_access":true,
	                    "user_code":"000007",
	                    "person2":{
	                        "f_initials":"J",
	                        "f_first_name":"James",
	                        "f_suffix":"",
	                        "f_description":"Father/Parent 2",
	                        "f_other_name":"",
	                        "f_preferred_name":"James",
	                        "e_mail":"",
	                        "f_title":"",
	                        "f_surname":"Allen"
	                    },
	                    "address":{
	                        "1":{
	                            "email2":"",
	                            "email1":""
	                        },
	                        "6":{
	                            "email2":"",
	                            "email1":""
	                        }
	                    },
	                    "person1":{
	                        "m_preferred_name":"Judy",
	                        "m_description":"Mother/Parent 1",
	                        "m_other_name":"",
	                        "m_surname":"Allen",
	                        "m_title":"",
	                        "m_suffix":"",
	                        "m_initials":"J",
	                        "e_mail":"",
	                        "m_first_name":"Judy"
	                    },
	                    "username":"fwfwrfef",
	                    "sfa_num":1,
	                    "students":[
	                        "0009073",
	                        "0020771",
	                        "0020595",
	                        "0009102",
	                        "0009226"
	                    ]
	                },
	                "splitFamily2":{
	                    "web_access":true,
	                    "user_code":"000007",
	                    "person2":{
	                        "f_initials":"J",
	                        "f_first_name":"James",
	                        "f_suffix":"",
	                        "f_description":"Father/Parent 2",
	                        "f_other_name":"",
	                        "f_preferred_name":"James",
	                        "e_mail":"",
	                        "f_title":"",
	                        "f_surname":"Allen"
	                    },
	                    "address":{
	                        "7":{
	                            "email2":"",
	                            "email1":""
	                        }
	                    },
	                    "person1":{
	                        "m_preferred_name":"Judy",
	                        "m_description":"Mother/Parent 1",
	                        "m_other_name":"",
	                        "m_surname":"Allen",
	                        "m_title":"",
	                        "m_suffix":"",
	                        "m_initials":"J",
	                        "e_mail":"",
	                        "m_first_name":"Judy"
	                    },
	                    "username":"adfgaddg",
	                    "sfa_num":2,
	                    "students":[
	                        "0009073",
	                        "0020595",
	                        "0009102",
	                        "0009226"
	                    ]
	                }
	            }
	        }
	    ],
	    "token":{
	        "user_code":"000007",
	        "timestamp":"{ts '2020-03-30 09:59:30'}"
	    }
	}
    ```
 
* **Error Response:**

    `user_code` not supplied
    ```javascript
    "user_code": "field is required"
    ```
    
* **Sample Parameters:**

	```javascript
	{
		"user_code":"000007"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetParents&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetParents" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```