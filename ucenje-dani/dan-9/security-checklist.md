## Input Validation
- [ ] SQL Injection u Username polju
- [ ] SQL Injection u Password polju
- [ ] XSS u Username polju
- [ ] XSS u Password polju
- [ ] Specijalni karakteri (!@#$%^&*)
- [ ] Veoma dugačak string (1000+ karaktera)
- [ ] Prazna polja

## Authentication
- [ ] Brute Force zaštita
- [ ] CAPTCHA nakon više neuspelih pokušaja
- [ ] Password policy — minimum dužina
- [ ] Prazna lozinka nije prihvaćena
- [ ] Default kredencijali blokirani
- [ ] Error poruke ne otkrivaju detalje
- [ ] HTTPS na login stranici

## Session Management
- [ ] Nakon logout session token ne važi
- [ ] Token ističe nakon neaktivnosti
- [ ] Token je dovoljno kompleksan
- [ ] Simultane sesije na dva browsera
- [ ] Session cookie ima Secure i HttpOnly flag

## Data Exposure
- [ ] Lozinka maskirana u input polju
- [ ] HTTPS na svim stranicama
- [ ] Token u headeru, ne URL-u
- [ ] Nema sensitive podataka u konzoli
- [ ] Error poruke ne otkrivaju tehničke detalje