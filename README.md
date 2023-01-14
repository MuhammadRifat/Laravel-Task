**Documentation for APIs**

**Table of Contents**

|

**[# Customer Section](#_q535khpncm4v) 3**[1. Customer Register:](#_c9oehxqlxnm) 3[2. Customer Register Verify:](#_xg4vfuy0t3uh) 4[3. Get All Customer:](#_wbtb9sf4tvwu) 5[4. Get a Customer by Id:](#_gxlnibuf6syf) 5[5. Customer Update:](#_755s56drgj5c) 5[6. Customer Delete:](#_wb8krjbm859r) 7[7. Customer Login:](#_vokmyo6p0flb) 7[8. Customer Login Verify:](#_f1nxfdblw97d) 8[9. Send OTP:](#_gwddcf3q578e) 8[10. Reset Password:](#_rwlhtqld5hzu) 9[11. Change Password:](#_45tiyjjrqgs) 9[12. Verify Forget Password OTP:](#_hdwd0i9kjccr) 10**[# Enum Section](#_315gcmc2e7e) 11**[1. Get Enums:](#_qn401lvf70gm) 11[2. Get Enum by Id:](#_drhuf2es0eaw) 12[3. Create Enum:](#_6sk0f1wwo66f) 12**[# User Section](#_3wrwlmc8hj0z) 14**[1. User Register:](#_lngfcppe41xc) 14[2. Get all Users:](#_brimis5mr1ye) 14[3. Get User by Id:](#_nyrixk9egzv2) 14[4. Update User:](#_9v152xukmxd6) 15**[# Auth Section](#_jfvdiwuang13) 16**[1. Login:](#_nycluadal4wb) 16[2. Is Logged In:](#_tax8u4e8u7qm) 16


 |
| --- |

# # Customer Section

### 1. Customer Register:

- API: [http://localhost:3000/v1/api/customer/register](http://localhost:3000/v1/api/customer)
- Method: POST
- Request body:

{

"first\_name": "John",

"last\_name": "Doe",

"phone": "+8801719133113",

"email": "johndoe@gmail.com",

"password": "123456",

"customer\_type": "business",

"country": "BD",

"chain": "KFC",

"addresses": [

{

"description": "Street: 1, Road: 1, Mirpur, Dhaka",

"default": **true**

}

],

"business\_info": {

"employee\_id": 1,

"company\_name": "BDLC",

"department": "MIS",

"department\_code": 4,

"internal\_customer\_number": "800",

"customer\_group": "New",

"street\_name": "bijoy soroni",

"street\_number": 99,

"street\_letter": "L",

"floor\_number": "99",

"zip": "2045",

"city": "Dhaka",

"company\_code": "K-1",

"street\_description": "Street: 1, Road: 1, Mirpur, Dhaka"

}

}

- Response:

{

"success": **true** ,

"data": {

"\_id": "63be58d19558c44f7b858547",

"first\_name": "John",

"last\_name": "Doe",

"email": "johndoe@gmail.com",

"phone": "+8801719133113",

"customer\_type": "private",

"otp": 9554,

"addresses": [

{

"description": "Street: 1, Road: 1, Mirpur, Dhaka",

"default": **true** ,

"\_id": "63be58d19558c44f7b858548"

}

],

"business\_info": {

"employee\_id": 1,

"company\_name": "BDLC",

"department": "MIS",

"department\_code": 4,

"internal\_customer\_number": "800",

"customer\_group": "New",

"street\_name": "bijoy soroni",

"street\_number": 99,

"street\_letter": "L",

"floor\_number": "99",

"zip": "2045",

"city": "Dhaka",

"company\_code": "K-1",

"street\_description": "Street: 1, Road: 1, Mirpur, Dhaka"

}

}

}

### 2. Customer Register Verify:

- API: [http://localhost:3000/v1/api/customer/verify-registration](http://localhost:3000/v1/api/customer/verify-registration)
- Method: POST
- Request body:

{

"phone":"+8803336",

"otp":3501

}

- Response:

{

"success": **true** ,

"message": "OTP Verified"

}

Or,

{

"success": **false** ,

"otp": 4651,

"message": "New Otp Sent"

}

### 3. Get All Customer:

- API: [http://localhost:3000/v1/api/customer](http://localhost:3000/v1/api/customer)
- Method: GET

### 4. Get a Customer by Id:

- API: [http://localhost:3000/v1/api/customer/\_customer\_id](http://localhost:3000/v1/api/customer/63be58d19558c44f7b858547)
- Method: GET

### 5. Customer Update:

- API: [http://localhost:3000/v1/api/customer/\_customer\_id](http://localhost:3000/v1/api/customer/63be58d19558c44f7b858547)
- Method: PUT
- Request body:

{

"first\_name": "John",

"last\_name": "Doe",

"phone": "+8801719133111",

"email": "johndoe1@gmail.com",

"customer\_type": "business",

"country": "BD",

"chain": "KFC",

"addresses": [

{

"description": "Street: 1, Road: 1, Mirpur, Dhaka",

"default": **true**

}

],

"business\_info": {

"employee\_id": 1,

"company\_name": "BDLC",

"department": "MIS",

"department\_code": 4,

"internal\_customer\_number": "800",

"customer\_group": "New",

"street\_name": "bijoy soroni",

"street\_number": 99,

"street\_letter": "L",

"floor\_number": "99",

"zip": "2045",

"city": "Dhaka",

"company\_code": "K-1",

"street\_description": "Street: 1, Road: 1, Mirpur, Dhaka"

}

}

- Response:

{

"success": **true** ,

"data": {

"\_id": "63be7034b61ea0c85d6c2704",

"first\_name": "John",

"last\_name": "Doe",

"email": "johndoe1@gmail.com",

"phone": "+8801719133111",

"customer\_type": "business",

"otp": 1448,

"business\_info": {

"employee\_id": 1,

"company\_name": "BDLC",

"department": "MIS",

"department\_code": 4,

"internal\_customer\_number": "800",

"customer\_group": "New",

"street\_name": "bijoy soroni",

"street\_number": 99,

"street\_letter": "L",

"floor\_number": 99,

"zip": 2045,

"city": "Dhaka",

"company\_code": "K-1",

"street\_description": "Hello"

},

"addresses": [

{

"description": "Street: 1, Road: 1, Mirpur, Dhaka",

"default": **true** ,

"\_id": "63be725db61ea0c85d6c2722"

}

]

}

}

### 6. Customer Delete:

- API: [http://localhost:3000/v1/api/customer/\_customer\_id](http://localhost:3000/v1/api/customer/63be58d19558c44f7b858547)
- Method: DELETE

### 7. Customer Login:

- API: [http://localhost:3000/v1/api/customer/login](http://localhost:3000/v1/api/customer/login)
- Method: POST
- Request body:

{

"phone": "+8801719133111",

"password": "123456"

}

- Response:

{

"success": **true** ,

"otp": 6967,

"data": {

"phone": "+8801719133111"

}

}

### 8. Customer Login Verify:

- API: [http://localhost:3000/v1/api/customer/verify-login](http://localhost:3000/v1/api/customer/verify-login)
- Method: POST
- Request body:

{

"phone":"+8801719133111",

"otp":9188

}

- Response:

{

"success": **true** ,

"data": {

"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjYzYmViM2JkYTQ2NDdmZDU0OGZkZGNmNyIsInBob25lIjoiKzg4MDE3MTkxMzMxMTEiLCJpYXQiOjE2NzM1MjI1MDJ9.UL0H8KJ9lPSGJyZnyj7HttAnJki3Uje2JjcEgjekrFY",

"customer": {

"\_id": "63beb3bda4647fd548fddcf7",

"first\_name": "John",

"last\_name": "Doe",

"email": "johndoe1@gmail.com",

"phone": "+8801719133111"

}

}

}

Or,

{

"success": **false** ,

"otp": 2920,

"message": "New Otp Sent"

}

### 9. Send OTP:

- API: [http://localhost:3000/v1/api/customer/send-otp](http://localhost:3000/v1/api/customer/send-otp)
- Method: POST
- Request body:

{

"phone":"+8801719133111"

}

- Response:

{

"success": **true** ,

"otp": 9276,

"message": "OTP sent"

}

### 10. Reset Password:

- API: [http://localhost:3000/v1/api/customer/reset-password](http://localhost:3000/v1/api/customer/reset-password)
- Method: POST
- Request body:

{

"phone": "+8801719133111",

"password": "654321"

}

- Response:

{

"success": **true,**

"message": **"** Password successfully reset **"**

}

#


### 11. Change Password:

- API: [http://localhost:3000/v1/api/customer/change-password](http://localhost:3000/v1/api/customer/change-password)
- Method: POST
- Request body:

{

"phone": "+8801719133111",

"old\_password": "123456",

"new\_password": "654321"

}

- Response:

{

"success": **true** ,

"data": {

"phone": "+8801719133111"

}

}

### 12. Verify Forget Password OTP:

- API: [http://localhost:3000/v1/api/customer/verify-fp-otp](http://localhost:3000/v1/api/customer/verify-fp-otp)
- Method: POST
- Request body:

{

"phone":"+8801719133111",

"otp":8485

}

- Response:

{

"success": **true** ,

"message": "Otp Verified"

}

# # Enum Section

### 1. Get Enums:

- API: [http://localhost:3000/v1/api/enum](http://localhost:3000/v1/api/enum)
- Method: POST
- Request body:

{

"names": [

"order\_status\_code",

"customer\_group"

]

}

- Response:

{

"success": **true** ,

"data": [

{

"\_id": "63b57f96bc1d0857da3226b8",

"name": "customer\_group",

"data": {

"TYPE1": "1",

"TYPE2": "2",

"TYPE3": "3"

},

"\_\_v": 0

},

{

"\_id": "63abc5fb3d4f76818801e3f7",

"name": "order\_status\_code",

"data": {

"10": "New",

"20": "Printed",

"30": "Produced",

"40": "Driven",

"50": "Delivered",

"60": "Paid",

"70": "Settled",

"80": "Included in Z-report"

}

}

]

}

### 2. Get Enum by Id:

- API: [http://localhost:3000/v1/api/enum/\_enum\_id](http://localhost:3000/v1/api/enum/_enum_id)
- Method: GET

- Response:

{

"\_id": "63abc5fb3d4f76818801e3f7",

"name": "order\_status\_code",

"data": {

"10": "New",

"20": "Printed",

"30": "Produced",

"40": "Driven",

"50": "Delivered",

"60": "Paid",

"70": "Settled",

"80": "Included in Z-report"

}

}

### 3. Create Enum:

- API: [http://localhost:3000/v1/api/enum/create](http://localhost:3000/v1/api/enum/create)
- Method: POST
- Request body:

{

"name": "order\_status\_code",

"data": {

"10": "New",

"20": "Printed",

"30": "Produced",

"40": "Driven",

"50": "Delivered",

"60": "Paid",

"70": "Settled",

"80": "Included in Z-report"

}

}

- Response:

{

"success": **true**

"name": "order\_status\_code",

"data": {

"10": "New",

"20": "Printed",

"30": "Produced",

"40": "Driven",

"50": "Delivered",

"60": "Paid",

"70": "Settled",

"80": "Included in Z-report"

}

}

# # User Section

### 1. User Register:

- API: [http://localhost:3000/v1/api/enum](http://localhost:3000/v1/api/enum)
- Method: POST
- Request body:

{

"user\_name": "Sadi",

"phone": "01000000002",

"password": "123456"

}

- Response:

{

"user\_name": "Sadi",

"phone": "01000000002",

"\_id": "63bfcab7050004c0d5aabf1b",

"\_\_v": 0

}

### 2. Get all Users:

- API: [http://localhost:3000/v1/api/user](http://localhost:3000/v1/api/user)
- Method: GET
- Response:

[

{

"\_id": "63bfc32fe073e59d901bfdb7",

"user\_name": "Sadi",

"phone": "01000000003",

"\_\_v": 0

}

]

### 3. Get User by Id:

- API: [http://localhost:3000/v1/api/user/\_user\_Id](http://localhost:3000/v1/api/user/63bfc318e073e59d901bfdb3)
- Method: GET
- Response:

{

"\_id": "63bfc318e073e59d901bfdb3",

"user\_name": "Sadi",

"phone": "01000000001",

"\_\_v": 0

}

### 4. Update User:

- API: [http://localhost:3000/v1/api/user/\_user\_Id](http://localhost:3000/v1/api/user/63bfc318e073e59d901bfdb3)
- Method: PUT
- Request body:

{

"user\_name": "Sadi",

"phone": "01000000005"

}

- Response:

{

"\_id": "63bfc318e073e59d901bfdb3",

"user\_name": "Sadi",

"phone": "01000000005",

"\_\_v": 0

}

# # Auth Section

### 1. Login:

- API: [http://localhost:3000/v1/api/auth/login](http://localhost:3000/v1/api/auth/login)
- Method: POST
- Request body:

{

"phone": "01000000002",

"password": "123456"

}

- Response:

{

"success": **true** ,

"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjYzYmZjYWI3MDUwMDA0YzBkNWFhYmYxYiIsInBob25lIjoiMDEwMDAwMDAwMDIiLCJpYXQiOjE2NzM1MTUxMjJ9.RLDtFLYx7U\_s35NHPQ0fJUgdQsC-aJboHEW-b04D9e0"

}

### 2. Is Logged In:

- API: [http://localhost:3000/v1/api/auth/is-logged-in](http://localhost:3000/v1/api/auth/login)
- Method: GET
- Request header:

"Authorization": "Bearer \_token"

- Response:

{

"success": **true** ,

"logged\_in": **true** ,

"phone": "01000000002"

}
