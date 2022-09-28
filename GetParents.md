**getParents**
----
	Returns an array of structured parent data in JSON format.

* **Version History:**

	TASS v52.6 - Method Added
	
	TASS v54.4 PR3 - Addition of "email1" and "email2" keys within parent address for non split families. These keys are recommended to keep in line with split families.

	TASS v57.11 - Add `person_num` & `person_posn` in returned data

* **Version:**

	3

* **Permission:**

   Administration > LDAP/SAML Maintenance > View

* **Method:**

	`GET | POST`
  
* **Params:**

   **Required:**
 
	`user_code [string]` - One or a list of Parent Code(s) OR "ALL"

   **Optional:**

	none

   **Conditional:**

	none

* **Success Response:**

    ```javascript
    {
		"__tassversion": "01.054.4.094",
		"parents": [{
				"000007": [{
						"web_access": true,
						"user_code": "000007",
						"person2": {
							"initials": "J",
							"suffix": "",
							"surname": "Allen",
							"person_posn": 2,
							"description": "Father/Parent 2",
							"preferred_name": "James",
							"other_name": "",
							"title": "",
							"e_mail": "",
							"person_num": 287,
							"first_name": "James"
						},
						"address": {
							"1": {
								"person_posn": "",
								"email2": "JamesAllen2@testing.com",
								"email1": "JamesAllen1@testing.com"
							},
							"6": {
								"person_posn": 1,
								"email2": "",
								"email1": ""
							}
						},
						"person1": {
							"initials": "J",
							"suffix": "",
							"surname": "Allen",
							"person_posn": 1,
							"description": "Mother/Parent 1",
							"preferred_name": "Judy",
							"other_name": "",
							"title": "",
							"e_mail": "",
							"person_num": 288,
							"first_name": "Judy"
						},
						"username": "fwfwrfef",
						"sfa_num": 1,
						"students": [
							"0009073",
							"0020771",
							"0020595",
							"0009102",
							"0009226"
						]
					},
					{
						"web_access": true,
						"user_code": "000007",
						"person2": {
							"initials": "J",
							"suffix": "",
							"surname": "Allen",
							"person_posn": 2,
							"description": "Father/Parent 2",
							"preferred_name": "James",
							"other_name": "",
							"title": "",
							"e_mail": "",
							"person_num": 287,
							"first_name": "James"
						},
						"address": {
							"7": {
								"person_posn": 2,
								"email2": "",
								"email1": ""
							}
						},
						"person1": {
							"initials": "J",
							"suffix": "",
							"surname": "Allen",
							"person_posn": 1,
							"description": "Mother/Parent 1",
							"preferred_name": "Judy",
							"other_name": "",
							"title": "",
							"e_mail": "",
							"person_num": 288,
							"first_name": "Judy"
						},
						"username": "adfgaddg",
						"sfa_num": 2,
						"students": [
							"0009073",
							"0020595",
							"0009102",
							"0009226"
						]
					}
				]
			},
			{
				"002126": {
					"web_access": true,
					"user_code": "002126",
					"person2": {
						"initials": "P",
						"suffix": "",
						"surname": "Jackson",
						"person_posn": 2,
						"description": "Father/Parent 2",
						"preferred_name": "Peter",
						"other_name": "",
						"title": "",
						"e_mail": "",
						"person_num": 298,
						"first_name": "Peter"
					},
					"address": {
						"1": {
							"person_posn": "",
							"email": "P.Jackson@testing.com.au",
							"email2": "mysecondemail@testing.com.au",
							"email1": "P.Jackson@testing.com.au"
						}
					},
					"person1": {
						"initials": "M",
						"suffix": "",
						"surname": "Jackson",
						"person_posn": 1,
						"description": "Mother/Parent 1",
						"preferred_name": "Mary",
						"other_name": "",
						"title": "",
						"e_mail": "",
						"person_num": 299,
						"first_name": "Mary"
					},
					"username": "002126",
					"sfa_num": "",
					"students": [
						"0020843"
					]
				}
			}
		],
		"token": {
			"user_code": "002126,000007",
			"timestamp": "{ts '2022-09-28 16:43:51'}"
		}
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
		"user_code":"000007"
	}
	```

* **Sample GET:** (With URL Encoded `token`)

	```HTML
	http://api.tasscloud.com.au/tassweb/api/?appcode=API23&v=3&method=GetParents&token=3w6XHPP1j163aHf%2FHRAnLA%3D%3D&company=10
	```
  
* **Sample POST:**

	```HTML
	<form id="postForm" name="postForm" method="POST" action="http://api.tasscloud.com.au/tassweb/api/">
		<input type="hidden" name="method" value="GetParents" />
		<input type="hidden" name="appcode" value="API23" />
		<input type="hidden" name="company" value="10" />
		<input type="hidden" name="v" value="3" />
		<textarea name="token">3w6XHPP1j163aHf\/HRAnLA==</textarea>
	</form>
	```
