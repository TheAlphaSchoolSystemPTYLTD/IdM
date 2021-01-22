**setEmployee**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the employee.

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

    `school_email [string]` - School Email Address

    `idm [string]` - idm

   **Conditional:**

    `user_code [string]` - Employee Code must be supplied if 'username' is not

    `username [string]` - Employee Portal Username must be supplied if 'user_code' is not

    `web_access [string]` - Must be "Y" or "N", only valid for teacher

* **Success Response:**

    ```javascript
    {
      "success": "You successfully updated an employee.",
      "__tassversion": "01.053.3.000",
      "token": {
        "user_code":"000003",
        "username":"baskins",
        "timestamp": "{ts '2021-01-22 16:29:03'}",
        "e_mail":"abaskins@alphabus.com.au"
      }
    }
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

    `school_email` not in correct format
    ```javascript
    "school_email": "school_email is not valid."
    ```

    `user_code` not found in employees table
    ```javascript
    "user_code": "user_code is not a valid emp_code"
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

    `web_access` not supplied for teacher
    ```javascript
    "web_access": "web_access must be provided for a teacher"
    ```

    `web_access` supplied for non-teacher
    ```javascript
    "web_access": "web_access only valid for a teacher"
    ```
    
* **Sample Parameters:**

	```javascript
	{
	    "user_code":"000003",
        "username":"baskins",
        "e_mail":"abaskins@alphabus.com.au"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=SetEmployee&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="SetEmployee" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```