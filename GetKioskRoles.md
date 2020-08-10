**GetKioskRoles**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the admin user.

* **Version History:**

	TASS v53.0 - Method Added

* **Version:**

	3

* **Permission:**

   Administration > Portal Security Permissions > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`include_members [boolean]` - Include members in each secrole_code or not

   **Optional:**

	`code [string]` - One or a list of Kiosk Role Code(s)

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
	    "kioskRoles":[
	        {
	            "code":"ADM001",
	            "desc":"Administration User Group"
	        }
	    ],
	    "token":{
	        "code":"ADM001",
	        "timestamp":"{ts '2020-06-24 15:35:02'}",
	        "include_members":false
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
		"code":"ADM001",
		"include_members":"false"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetKioskRoles&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetKioskRoles" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```