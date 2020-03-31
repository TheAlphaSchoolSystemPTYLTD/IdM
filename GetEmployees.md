**getEmployees**
----
	Returns an array of structured employee data in JSON format.

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
	    "employees":[
	        {
	            "initials":"P",
	            "suffix":"",
	            "surname":"Baskins",
	            "ceider":"",
	            "end_date":"",
	            "start_date":"2007-06-25 00:00:00.0",
	            "e_mail":"jeandoe@alphabus.com.au",
	            "departments":"",
	            "school_email":"jeandoe@tassweb.com.au",
	            "first_name":"Jean",
	            "web_access":false,
	            "user_code":1000002,
	            "salutation":"",
	            "preferred_name":"Jean",
	            "other_name":"",
	            "username":"jdoe",
	            "title":"Mr"
	        }
	    ],
	    "token":{
	        "user_code":1000002,
	        "timestamp":"{ts '2020-03-27 10:41:50'}"
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
		"user_code":"1000002"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetEmployees&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetEmployees" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```