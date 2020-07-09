**GetAdminRoles**
----
	Returns an array of structured admin roles data in JSON format.

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
 
	`include_members [boolean]` - Include members in each secrole_code or not

   **Optional:**

	`code [string]` - One or a list of Admin Role Code(s)

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
	    "roles":[
	        {
	            "code":"SEC",
	            "members":[
	                {
	                    "sing_on_code":"craig"
	                },
	                {
	                    "sing_on_code":"Deepa"
	                },
	                {
	                    "sing_on_code":"Mani"
	                },
	                {
	                    "sing_on_code":"ricardo"
	                },
	                {
	                    "sing_on_code":"service."
	                }
	            ],
	            "desc":"Extra Curricular"
	        }
	    ],
	    "token":{
	        "code":"SEC",
	        "timestamp":"{ts '2020-06-24 09:31:22'}",
	        "include_members":true
	    }
	}
    ```
 
* **Error Response:**

    `include_members` not supplied
    ```javascript
    "include_members": "field is required"
    ```

    `include_members` not a boolean
    ```javascript
    "include_members": "Value is not a valid boolean."
    ```
    
* **Sample Parameters:**

	```javascript
	{
		"include_members":"true",
		"code":"SEC"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetAdminRoles&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetAdminRoles" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```