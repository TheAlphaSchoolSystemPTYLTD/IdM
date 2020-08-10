**GetAdminUserRoles**
----
	Returns an array of structured admin user roles data in JSON format.

* **Version History:**

	TASS v53.0 - Method Added

* **Version:**

	3

* **Permission:**

   Administration > User Maintenance > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`user_code [string]` - One or a list of Admin User Code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
	    "userRoles":[
	        {
	            "user_code":"jack",
	            "roles":[
	                "SEC",
	                "PAR",
	                "SR",
	                "ACC",
	                "ADM",
	                "ENR",
	                "FUN",
	                "PSR",
	                "PUR",
	                "SMR",
	                "TCH",
	                "FA1"
	            ]
	        }
	    ],
	    "token":{
	        "user_code":"jack",
	        "timestamp":"{ts '2020-06-24 10:20:13'}"
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
		"user_code":"jack"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetAdminUserRoles&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetAdminUserRoles" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```