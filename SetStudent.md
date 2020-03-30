**setStudent**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the student.

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

	`web_access [string]` - Must be "Y" or "N"

	`e_mail [string]` - Email Address

	`idm [string]` - idm

	`ceider [string]` - ceider

	`alt_id [string]` - alternate id

   **Conditional:**

	`user_code [string]` - Student Code must be supplied if 'username' is not

	`username [string]` - Student Portal Username must be supplied if 'user_code' is not

* **Success Response:**

    ```javascript
    "success": "You successfully updated a student."
    ```
 
* **Error Response:**

    `user_code` AND `username` both not supplied
    ```javascript
    "required": "user_code' or 'username' must be defined."
    ```

    `user_code` not found in employees table
    ```javascript
    "user_code": "user_code is not a valid stud_code"
    ```

    `username` not found in portalusers table and user_code not supplied
    ```javascript
    "user_code": "'user_code' required to update username."
    ```

    `username` found in portalusers but do not match `user_code`
    ```javascript
    "user_code": "username already in use."
    ```

    `web_access` not 'Y' or 'N'
    ```javascript
    "web_access": "web_access must be 'Y' or 'N'."
    ```

    `e_mail` not in correct format
    ```javascript
    "e_mail": "e_mail is not valid."
    ```

    `user_code` not found in students table
    ```javascript
    "user_code": "user_code is not a valid stud_code"
    ```

    `username` not found in portalusers table
    ```javascript
    "user_code": "username does not exist"
    ```

    `username` corresponding stud_code does not match `user_code`
    ```javascript
    "user_code": "user_code and username do not match"
    ```
    
* **Sample Parameters:**

	```javascript
	{
	    "user_code":"0009131",
	    "username":"wHarry"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=SetStudent&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="SetStudent" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```