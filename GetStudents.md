**getStudents**
----
	Returns an array of structured student data in JSON format.

* **Version History:**

	TASS v52.6 - Method Added

* **Version:**

	3

* **Permission:**

   Administration > LDAP/SAML Maintenance > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`user_code [string]` - One or a list of Student Code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    {
	    "token":{
	        "user_code":"0009130",
	        "timestamp":"{ts '2020-03-27 10:35:31'}"
	    },
	    "students":[
	        {
	            "dol":"",
	            "surname":"Clark",
	            "expiry":"",
	            "e_mail":"andy.clark@tassweb.com.au",
	            "first_name":"jean",
	            "campus_code":"SE",
	            "alt_id":"FOREVERCLARK",
	            "web_access":true,
	            "user_code":"0009130",
	            "year_grp":11,
	            "idm":"",
	            "preferred_name":"Andy",
	            "dob":"1994-09-02 00:00:00.0",
	            "other_name":"",
	            "username":"aclark",
	            "gender":"F",
	            "form_cls":"D",
	            "house":"BA",
	            "doe":"2018-03-30 00:00:00.0"
	        }
	    ]
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
		"user_code":"0009130"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetStudents&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetStudents" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```