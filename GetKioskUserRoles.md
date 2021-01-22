**GetKioskUserRoles**
----
	Returns an array of structured admin user roles data in JSON format.

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
 
	`user_code [string]` - One or a list of Kiosk User sign_on_code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
	{
	    "KioskUserRoles":[
	        {
	            "user_code":"AJ",
	            "roles":"ADM001,TCH,WEB"
	        },
	        {
	            "user_code":"KAT",
	            "roles":"TCH"
	        }
	    ],
	    "__tassversion": "01.053.3.000",
	    "token":{
	        "user_code":"AJ,KAT",
	        "timestamp":"{ts '2021-01-22 18:39:08'}"
	    }
	}
    ```
 
* **Error Response:**

    `user_code` not supplied
    ```javascript
    "user_code": "field is required"
    ```

    `user_code` invalid
    ```javascript
    "user_code": "user_code([user_code] not in any group)"
    ```
    
* **Sample Parameters:**

	```javascript
	{
		"user_code":"AJ,KAT"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetKioskUserRoles&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetKioskUserRoles" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```