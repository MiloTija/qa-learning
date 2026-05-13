Kad završiš — idemo na Zadatak 2 — stvarno security testiranje na saucedemo! 🔍

Test 1: SQL Injection u Username polju
Test 2: XSS u Username polju  
Test 3: Direct URL bez logovanja
Test 4: Brute Force — 5x pogrešna lozinka

Test 1:
Unesi u Username polje:
1. ' OR '1'='1
2. ' OR 1=1--
3. '; DROP TABLE users;--

- Kada ukucam samo ova 3 elementa u username polje, bez passworda -> "Epic sadface: Password is required"
- Kada ukucam ova tri elementa u username polje i ukucam sifru "secret_sauce" -> "Epic sadface: Username and password do not match any user in this service"

Test 2:
Unesi u Username polje:
1. <script>alert('XSS')</script>
2. <img src=x onerror=alert('XSS')>

- Kada ukucam samo ova 2 elementa u username polje, bez passworda -> "Epic sadface: Password is required"
- Kada ukucam ova 2 elementa u username polje i ukucam sifru "secret_sauce"  -> "Epic sadface: Username and password do not match any user in this service"

Test 3: 
1. Direktno sam ukucala: https://www.saucedemo.com/inventory.html -> "Epic sadface: You can only access '/inventory.html' when you are logged in."

Test 4: 
1. Pokusaj logina sa userom "standard_user" kada 5x ukucam pogresnu lozinku -> Svaki put izbaci obavestenje "Epic sadface: Username and password do not match any user in this service"
Probala jos 5x -> isti error izlazi
→ Ovo je A07 — Authentication Failure!

Title: [Security] Brute Force Authentication Failure -> After attempting 5 or more times to log in with the wrong password, the login is not locked
Severity: Critical
Priority: High
Attack Vector: An attacker can try unlimited password combinations.
Impact: An attacker can eventually guess the password through brute force attempts.
Remediation: The login should be temporarily blocked after multiple failed login attempts.
The user should receive a security alert email, or be redirected to/use the “Forgot Password” flow.
Environment: Chrome 146, saucedemo.com
Steps to Reproduce:
1. OPen https://www.saucedemo.com
2. In "Username" field enter: "standard_user"
3. In "Password" field enter : "wrong_password"
4. Click on "Login" — 10x
Expected: The account is locked after 3–5 failed login attempts.
Actual: The login form remains active without any restrictions.