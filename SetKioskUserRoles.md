**SetKioskUserRoles**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the admin user.

* **Version History:**

	TASS v53.0 - Method Added

* **Version:**

	3

* **Permission:**

   Administration > Portal Security Permissions > Edit

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`user_code [string]` - One Kiosk User sign_on_code

	`roles [string]` - A list of secrole_code to be added to the Kiosk user

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
	    "success":"Roles updated for AJ.",
	    "token":{
	        "user_code":"AJ",
	        "roles":"ADM001,TCH,WEB",
	        "timestamp":"{ts '2020-06-24 17:29:09'}"
	    }
	}
    ```
 
* **Error Response:**

    `user_code` not supplied
    ```javascript
    "user_code": "field is required"
    ```

    `roles` not supplied
    ```javascript
    "roles": "field is required"
    ```

    `user_code` invalid
    ```javascript
    "user_code": "user_code([user_code] not in any group yet)"
    ```

    `roles` has invalid role_code
    ```javascript
    "roles": "role_code([one of code in roles] invalid)"
    ```
    
* **Sample Parameters:**

	```javascript
	{
		"user_code":"AJ",
		"roles":"ADM001,TCH,WEB"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=SetKioskUserRoles&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="SetKioskUserRoles" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```