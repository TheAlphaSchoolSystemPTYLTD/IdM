**setAdmin**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the admin user.

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
 
	none

   **Optional:**

	`username [string]` - username (will be used for creating new portalusers record)

    `e_mail [string]` - Email Address

   **Conditional:**

	`user_code [string]` - User Code must be supplied if 'username' is not

    `username [string]` - Username must be supplied if 'user_code' is not

* **Success Response:**

    ```javascript
    "success": "You successfully updated a admin user."
    ```
 
* **Error Response:**

    `user_code` AND `username` both not supplied
    ```javascript
    "required": "user_code' or 'username' must be defined."
    ```

    `e_mail` not in correct format
    ```javascript
    "e_mail": "e_mail is not valid."
    ```

    `user_code` not found in employees table
    ```javascript
    "user_code": "user_code is not a valid admin user code."
    ```

    `username` not found in portalusers table and `user_code` not supplied
    ```javascript
    "user_code": "'user_code' required to update username."
    ```

    `username` used in another company
    ```javascript
    "username": "user_code exists in another company ([cmpy_code])."
    ```
    
* **Sample Parameters:**

	```javascript
	{
        "user_code":"adam001",
        "e_mail":"adam@tassweb.com.au",
        "username":"adam"
    }
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=SetAdmin&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="SetAdmin" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```