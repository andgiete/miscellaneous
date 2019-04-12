# 18Biotronik

*REST API Backend for 18Biotro*

## Usage

### GET /api/products
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with a product attributes

### POST /api/products
* *Authentication:* JSON Webtoken (See authentication section)
* *Request Headers:* Content-Type:application/json
* *Body:* JSON containing product attributes
* *Return:* JSON with the new product inserted

### GET /api/products/:ID_Prod
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with the product id provided

### PUT /api/products/:ID_Prod
* *Authentication:* JSON Webtoken (See authentication section)
* *Request Headers:* Content-Type:application/json
* *Body:* JSON containing product attributes to be modified
* *Return:* JSON with the new product modified

### DELETE /api/products/:ID_Prod
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with the product removed


### GET /api/veilles
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with a veille attributes

### POST /api/veilles
* *Authentication:* JSON Webtoken (See authentication section)
* *Request Headers:* Content-Type:application/json
* *Body:* JSON containing product attributes
* *Return:* JSON with the new veille inserted

### GET /api/veilles/:ID_Veille
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with the veille id provided

### PUT /api/veilles/:ID_Veille
* *Authentication:* JSON Webtoken (See authentication section)
* *Request Headers:* Content-Type:application/json
* *Body:* JSON containing product attributes to be modified
* *Return:* JSON with the veille modified

### DELETE /api/veilles/:ID_Veille
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with the veille removed

## Authentication

The Authentication is based on JSON WEB TOKENS. Upon sign in, every user is given a seperate JSON token that need to be inserted in the header attribute called "Authorization". 

Example: 
 Authorization: eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VySWQiOiJiMDhmODZhZi0zNWRhLTQ4ZjItOGZhYi1jZWYzOTA0NjYwYmQifQ.-xN_h82PHVTCMA9vdoHrcZxH-x5mb11y1537t3rGzcM
 
### POST /api/authentication/signup
* *Authentication:* NO AUTH
* *Request Headers:* Content-Type:application/json
* *Body:* JSON containing user attributes
* *Return:* JSON with the new user inserted

### POST /api/authentication/signin
* *Request Headers:* Content-Type:application/json
* *Body:* JSON containing user credentials
* *Return:* WEBTOKEN

### GET /api/authentication/verify/:serial
* *Return:* Verification Status

### GET /api/user/:Username
* *Authentication:* JSON Webtoken (See authentication section)
* *Return:* JSON with the user requested

## Product Attributes
* denomination_commune
* denomination_commerciale
* code_nomenclature
* code_LPPR
* classe_DM
* directive_UE
* num_org_notified
* date_first_market
* fabricant_DM
* composition_dispo
* domaine_indications
* DM_steril
* mode_steril
* cons_stock_condition
* tech_sec
* bio_sec
* mode_emploi
* indications
* precautions
* contre_indications
* extra_info

## User Attributes
* username
* password *HASH THE PASSWORD IN SHA256 BEFORE SUBMITTING REQUESTS*
* email
* phone
* website
* address
* first_name
* last_name
* is_verified

## Veille Attributes
* title
* body
* image
