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
 
	`user_code [string]` - One or a list of Student Code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    {
	    "parents":[
	        {
	            "000007":[
	                {
	                    "web_access":true,
	                    "user_code":"000007",
	                    "person2":{
	                        "initials":"J",
	                        "suffix":"",
	                        "surname":"Allen",
	                        "description":"Father/Parent 2",
	                        "preferred_name":"James",
	                        "other_name":"",
	                        "title":"",
	                        "e_mail":"",
	                        "first_name":"James"
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
	                        "initials":"J",
	                        "suffix":"",
	                        "surname":"Allen",
	                        "description":"Mother/Parent 1",
	                        "preferred_name":"Judy",
	                        "other_name":"",
	                        "title":"",
	                        "e_mail":"",
	                        "first_name":"Judy"
	                    },
	                    "username":"agnew",
	                    "sfa_num":1,
	                    "students":[
	                        "0009073",
	                        "0020771",
	                        "0020595",
	                        "0009102",
	                        "0009226"
	                    ]
	                },
	                {
	                    "web_access":true,
	                    "user_code":"000007",
	                    "person2":{
	                        "initials":"J",
	                        "suffix":"",
	                        "surname":"Allen",
	                        "description":"Father/Parent 2",
	                        "preferred_name":"James",
	                        "other_name":"",
	                        "title":"",
	                        "e_mail":"",
	                        "first_name":"James"
	                    },
	                    "address":{
	                        "7":{
	                            "email2":"",
	                            "email1":""
	                        }
	                    },
	                    "person1":{
	                        "initials":"J",
	                        "suffix":"",
	                        "surname":"Allen",
	                        "description":"Mother/Parent 1",
	                        "preferred_name":"Judy",
	                        "other_name":"",
	                        "title":"",
	                        "e_mail":"",
	                        "first_name":"Judy"
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
	            ]
	        }
	    ],
	    "token":{
	        "user_code":"000007",
	        "timestamp":"{ts '2020-03-31 11:02:17'}"
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