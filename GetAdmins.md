**getAdmins**
----
	Returns an array of structured admin user data in JSON format.

* **Version History:**

	TASS v52.6 - Method Added

* **Version:**

	3

* **Permission:**

   Administration > User Maintenance > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`user_code [string]` - One or a list of User Code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    {
	    "token":{
	        "user_code":"james",
	        "timestamp":"{ts '2020-03-27 10:48:57'}"
	    },
	    "admins":{
	        "1":{
	            "user_code":"james",
	            "username":"",
	            "e_mail":"james@tassweb.com.au",
	            "name":"System Administrator"
	        }
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
		"user_code":"root"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetAdmins&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetAdmins" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```