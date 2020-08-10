**setParent**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the parent.

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

    `web_access [string]` - web_access

    `stud_codes [string]` - student codes, must be current student(s)

    `add_nums [string]` - add_nums is optional for updating a split family record

   **Conditional:**

    `user_code [string]` - Parent Code must be supplied if 'username' is not

    `username [string]` - Parent Portal Username must be supplied if 'user_code' is not

    `sfa_num [string]` - sfa_num must be supplied for creating/updating a split family record

    `stud_codes [string]` - stud_codes must be supplied for creating a split family record, and will be optional for updating a split family record. Must be current student(s)

    `add_nums [string]` - add_nums must be be supplied for creating a split family record, and will be optional for updating a split family record.

* **Success Response:**

    ```javascript
    "success": "You successfully updated a parent."
    ```
 
* **Error Response:**

    `user_code` AND `username` both not supplied
    ```javascript
    "required": "user_code' or 'username' must be defined."
    ```

    `web_access` not 'Y' or 'N'
    ```javascript
    "web_access": "web_access must be 'Y' or 'N'."
    ```

    `user_code` not found in parent table
    ```javascript
    "user_code": "user_code is not valid"
    ```

    `sfa_num` not supplied for a split family
    ```javascript
    "sfa_num": "'sfa_num' required for split family."
    ```

    `add_nums` not supplied for a split family
    ```javascript
    "add_nums": "'add_nums' required for creating a split family record."
    ```

    `stud_codes` not supplied for a split family
    ```javascript
    "stud_codes": "'stud_codes' required for creating a split family record."
    ```

    `stud_codes` include non-current student(s)
    ```javascript
    "stud_codes": "'[stud_code]' is not a current student."
    ```

    `username` not supplied for a split family
    ```javascript
    "username": "'username' required for updating a split family."
    ```

    `username` not supplied for a split family
    ```javascript
    "username": "'username' required for creating a split family."
    ```

    `username` used by a split family
    ```javascript
    "username": "'username' is already being used by another Split Family."
    ```

    `username` not supplied for another Parent
    ```javascript
    "username": "'username' required for updating a parent portal user."
    ```

    `username` not supplied for another Parent
    ```javascript
    "username": "'username' required for creating a parent portal user."
    ```

    `username` used by another Parent
    ```javascript
    "username": "'username' is already being used by another Parent."
    ```
    
* **Sample Parameters:**

	```javascript
	{
        "user_code":"000003",
        "sfa_num":"1",
        "stud_codes":"0009130,0009131",
        "web_access":"Y",
        "username":"agnew"
    }
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=SetParent&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="SetParent" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```