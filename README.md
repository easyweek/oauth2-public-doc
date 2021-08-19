# EasyWeek API

## OAuth v2 Endpoint Configuration

URL: `https://my.easyweek.io/oauth/authorize`

### Credentials

```
{
    "clientId": "ASK_EASYWEEK_SUPPORT"
    "clientSecret": "ASK_EASYWEEK_SUPPORT"
}
```

### Headers

```
"headers": {
    "authorization": "Bearer {{accessToken}}",
    "accept": "application/json"
}
```

## Authorize

### Request

URL: `https://my.easyweek.io/oauth/authorize`

```
    "client_id": "{{clientId}}",
    "redirect_uri": "{{redirectUri}}", // PLEASE! provide redirect URL for EasyWeek engineer
    "response_type": "code"
```

### Response

```
"query": {
    "code": "{{code}}"
}
```

## Access Token Request & Refresh Token

### Request

URL: `https://my.easyweek.io/api/ext/oauth/token`

Method: **POST**

```
"code": "{{temp.code}}",
"client_id": "{{clientId}}",
"grant_type": "authorization_code",
"redirect_uri": "{{redirectUri}}",
"client_secret": "{{clientSecret}}"
```

### Response

```
"body": {
    "access_token": "{{access_token}}"
}
```

## Get Info

### Request

URL: `https://my.easyweek.io/api/ext/services/zapier/me`

```
"headers": {
    "authorization": "Bearer {{accessToken}}"
},
```

### Response

```
"body": {
    "id": "{{id}}",
    "user": "{{user}}"
}

```

## Trigger: Watch New User Bookings

URL: `https://my.easyweek.io/api/ext/services/zapier/user/bookings`

Method: **GET**

### Response Example

```
{
  "id": 1422,
  "booking_hash_id": "6009746",
  "booking_page": "https://easyweek.io/demo/orders/6009746",
  "booking_created_at": "2020-06-17T13:36:37+0000",
  "booking_created_at_formatted": "17 June 2020 13:36",
  "booking_date_start": "2020-06-24T14:00:00+0000",
  "booking_date_start_formatted": "24 June 2020 13:36",
  "booking_date_end": "2020-06-24T16:00:00+0000",
  "booking_date_end_formatted": "24 June 2020 13:36",
  "booking_duration": 120,
  "booking_duration_formatted": "2 hours",
  "booking_status": "New",
  "booking_price": "4000",
  "booking_price_formatted": "40,00 Euro",
  "booking_description": "Some booking comment",
  "company_name": "Ginger",
  "company_logo": "https://cdn.easyweek.io/image/logo.png",
  "company_page": "https://eyw.me/demo",
  "location_name": "Ginger West",
  "location_street": "",
  "location_apt": "",
  "location_zip": "",
  "location_city": "",
  "location_address_formatted": "",
  "location_lat": 23.5122323,
  "location_lng": 23.5122323,
  "customer_first_name": "Max",
  "customer_last_name": "Mustermann",
  "customer_email": "max@example.com",
  "customer_phone": "+491642321232",
  "service_name": "Ladies - Wash & Wet Haircut",
  "service_related": "Ladies - Fringe Trim; Ladies - Brazilian Blow Dry",
  "user_name": "Chris",
  "user_email": "chris@example.com",
  "user_phone": "+495122312322"
}
```

## Trigger: Watch New Bookings

URL: `https://my.easyweek.io/api/ext/services/zapier/bookings`

Method: **GET**

### Response Example

```
{
  "id": 1422,
  "booking_hash_id": "6009746",
  "booking_page": "https://easyweek.io/demo/orders/6009746",
  "booking_created_at": "2020-06-17T13:36:37+0000",
  "booking_created_at_formatted": "17 June 2020 13:36",
  "booking_date_start": "2020-06-24T14:00:00+0000",
  "booking_date_start_formatted": "24 June 2020 13:36",
  "booking_date_end": "2020-06-24T16:00:00+0000",
  "booking_date_end_formatted": "24 June 2020 13:36",
  "booking_duration": 120,
  "booking_duration_formatted": "2 hours",
  "booking_status": "New",
  "booking_price": "4000",
  "booking_price_formatted": "40,00 Euro",
  "booking_description": "Some booking comment",
  "company_name": "Ginger",
  "company_logo": "https://cdn.easyweek.io/image/logo.png",
  "company_page": "https://eyw.me/demo",
  "location_name": "Ginger West",
  "location_street": "",
  "location_apt": "",
  "location_zip": "",
  "location_city": "",
  "location_address_formatted": "",
  "location_lat": 23.5122323,
  "location_lng": 23.5122323,
  "customer_first_name": "Max",
  "customer_last_name": "Mustermann",
  "customer_email": "max@example.com",
  "customer_phone": "+491642321232",
  "service_name": "Ladies - Wash & Wet Haircut",
  "service_related": "Ladies - Fringe Trim; Ladies - Brazilian Blow Dry",
  "user_name": "Chris",
  "user_email": "chris@example.com",
  "user_phone": "+495122312322"
}
```
