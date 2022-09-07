**setParent**
----
	Returns "success" message, or a structure of invalid validations "error" message belonging to the parent.

* **Version History:**

	TASS v52.6 - Method Added

	TASS v57.10 - Required fields updated

* **Version:**

	3

* **Permission:**

   Administration > User Maintenance > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
    `user_code [string]` - Parent Code must be supplied.

    `username [string]` - Parent Portal Username must be supplied.

   **Optional:**

    `web_access [string]` - web_access

    `stud_codes [string]` - student codes, must be current student(s)

    `add_nums [string]` - add_nums is optional for updating a split family record

   **Conditional:**

    `sfa_num [string]` - sfa_num must be supplied for creating/updating a split family record

    `stud_codes [string]` - stud_codes must be supplied for creating a split family record, and will be optional for updating a split family record. Must be current student(s)

    `add_nums [string]` - add_nums must be be supplied for creating a split family record, and will be optional for updating a split family record.

* **Success Response:**

    ```javascript
		{
			"success": "You successfully updated a parent.",
			"__tassversion": "01.057.10.000",
			"token": {
				"web_access": "Y",
				"user_code": "000003",
				"add_nums": 1,
				"stud_codes": "0009130,0009131",
				"timestamp": "{ts '2022-09-07 11:26:45'}",
				"username": "agnew",
				"sfa_num": 1
			}
		}
    ```
 
* **Error Response:**

    `user_code` or `username` not supplied
    ```javascript
    "required": "user_code' AND 'username' must both be defined."
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

    `username` used by a split family
    ```javascript
    "username": "'username' is already being used by another Split Family."
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
        "add_nums":"1",
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