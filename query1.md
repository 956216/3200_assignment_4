### Query 1
```SQL
SELECT DISTINCT
  customers.LastName,
  customers.Email
FROM customers
JOIN invoices
  ON invoices.CustomerId = customers.CustomerId;
```
The above query selects customer emails and lastnames (using DISTINCT to remove duplicates) based upon invoic IDs
### Answer
```
Gonçalves|luisg@embraer.com.br
Köhler|leonekohler@surfeu.de
Tremblay|ftremblay@gmail.com
Hansen|bjorn.hansen@yahoo.no
Wichterlová|frantisekw@jetbrains.com
Holý|hholy@gmail.com
Gruber|astrid.gruber@apple.at
Peeters|daan_peeters@apple.be
Nielsen|kara.nielsen@jubii.dk
Martins|eduardo@woodstock.com.br
Rocha|alero@uol.com.br
Almeida|roberto.almeida@riotur.gov.br
Ramos|fernadaramos4@uol.com.br
Philips|mphilips12@shaw.ca
Peterson|jenniferp@rogers.ca
Harris|fharris@google.com
Smith|jacksmith@microsoft.com
Brooks|michelleb@aol.com
Goyer|tgoyer@apple.com
Miller|dmiller@comcast.com
Chase|kachase@hotmail.com
Leacock|hleacock@gmail.com
Gordon|johngordon22@yahoo.com
Ralston|fralston@gmail.com
Stevens|vstevens@yahoo.com
Cunningham|ricunningham@hotmail.com
Gray|patrick.gray@aol.com
Barnett|jubarnett@gmail.com
Brown|robbrown@shaw.ca
Francis|edfrancis@yachoo.ca
Silk|marthasilk@gmail.com
Mitchell|aaronmitchell@yahoo.ca
Sullivan|ellie.sullivan@shaw.ca
Fernandes|jfernandes@yahoo.pt
Sampaio|masampaio@sapo.pt
Schneider|hannah.schneider@yahoo.de
Zimmermann|fzimmermann@yahoo.de
Schröder|nschroder@surfeu.de
Bernard|camille.bernard@yahoo.fr
Lefebvre|dominiquelefebvre@gmail.com
Dubois|marc.dubois@hotmail.com
Girard|wyatt.girard@yahoo.fr
Mercier|isabelle_mercier@apple.fr
Hämäläinen|terhi.hamalainen@apple.fi
Kovács|ladislav_kovacs@apple.hu
O'Reilly|hughoreilly@apple.ie
Mancini|lucas.mancini@yahoo.it
Van der Berg|johavanderberg@yahoo.nl
Wójcik|stanisław.wójcik@wp.pl
Muñoz|enrique_munoz@yahoo.es
Johansson|joakim.johansson@yahoo.se
Jones|emma_jones@hotmail.com
Hughes|phil.hughes@gmail.com
Murray|steve.murray@yahoo.uk
Taylor|mark.taylor@yahoo.au
Gutiérrez|diego.gutierrez@yahoo.ar
Rojas|luisrojas@yahoo.cl
Pareek|manoj.pareek@rediff.com
Srivastava|puja_srivastava@yahoo.in
```
