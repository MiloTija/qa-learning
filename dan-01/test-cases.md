# Login Test Cases

## TC_LOGIN_001 — Successful login with valid credentials

**Conditions:** User is registered, not logged in  
**Test Data:** Username: "standard_user" | Pass: "secret_sauce"  
**Type:** Positive

### Steps:
1. Open "https://www.saucedemo.com"
2. In "Username" field enter: standard_user
3. In "Password" field enter: secret_sauce
4. Click "Login" button

**Expected:** User is redirected to /inventory.html, 
product list is displayed, no error messages


## TC_LOGIN_002	Login with empty username and password	

**Conditions:** Login with leaving bouth fields empty and taping on "Login" 
**Test Data:** Username: "" | Pass: ""  
**Type:** Negative

### Steps:
1. URL "https://www.saucedemo.com" is opened on Safari browser.
2. Leave "Username" field empty
3. Leave "Password" field empty
4. Tap on button "Login"	

**Expected:** Error msg is displayed :"Epic sadface: Username is required"
								


## TC_LOGIN_003	Login with non-existing username

**Conditions:** User is registered, not loged 
**Test Data:** Username: "invalid" | Pass: "secret_sauce"  
**Type:** Negative 

### Steps:
1. URL "https://www.saucedemo.com" is opened on Safari browser.
2. In "Username" field enter: "Invalid"
3. In "Password" field enter: "secret_sauce" 
4. Tap on button "Login"	

**Expected:** Error msg is displayed :"Epic sad fece: Username and password do not match any user in this service"