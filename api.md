BlogController
URL: /blog
Description: Handles blog-related operations.
Save Blog
Method: POST
Endpoint: /blog
Description: Saves a new blog.
Request Body:
```
{
  "title": "Blog Title",
  "content": "Blog content"
}
```
Response：
```
{
  "success": true,
  "data": {
    "id": 1,
    "title": "Blog Title",
    "content": "Blog content"
  }
}
```

Like Blog
Method: PUT
Endpoint: /blog/like/{id}
Description: Likes a blog by its ID.
Path Variable:
id (Long): Blog ID
Response：
```
{
  "success": true
}
```
Query My Blog
Method: GET
Endpoint: /blog/of/me
Description: Queries blogs of the logged-in user.
Request Parameter:
current (Integer, default = 1): Current page number
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "Blog Title",
      "content": "Blog content"
    }
  ]
}
```

Query Hot Blogs
Method: GET
Endpoint: /blog/hot
Description: Queries hot blogs.
Request Parameter:
current (Integer, default = 1): Current page number
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "Hot Blog Title",
      "content": "Hot Blog content"
    }
  ]
}
```

Query Blog By ID
Method: GET
Endpoint: /blog/{id}
Description: Queries a blog by its ID.
Path Variable:
id (Long): Blog ID
Response:
```
{
  "success": true,
  "data": {
    "id": 1,
    "title": "Blog Title",
    "content": "Blog content"
  }
}

```

Query Blog Likes
Method: GET
Endpoint: /blog/likes/{id}
Description: Queries likes of a blog by its ID.
Path Variable:
id (Long): Blog ID
Response:
```
{
  "success": true,
  "data": 10
}

```

Query Blog By User ID
Method: GET
Endpoint: /blog/of/user
Description: Queries blogs by user ID.
Request Parameter:
current (Integer, default = 1): Current page number
id (Long): User ID
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "User Blog Title",
      "content": "User Blog content"
    }
  ]
}

```

Query Blog of Followed Users
Method: GET
Endpoint: /blog/of/follow
Description: Queries blogs of followed users.
Request Parameter:
lastId (Long): Last blog ID
offset (Integer, default = 0): Offset for pagination
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "title": "Followed Blog Title",
      "content": "Followed Blog content"
    }
  ]
}
```


FollowController
URL: /follow
Description: Handles follow-related operations.
Follow User
Method: PUT
Endpoint: /follow/{id}/{isFollow}
Description: Follow or unfollow a user.
Path Variables:
id (Long): User ID to follow/unfollow
isFollow (Boolean): true to follow, false to unfollow
Response:
```
{
  "success": true
}
```


Check Follow Status
Method: GET
Endpoint: /follow/or/not/{id}
Description: Checks if the logged-in user follows another user.
Path Variable:
id (Long): User ID to check
Response:
```
{
  "success": true,
  "data": true
}
```


Query Common Follows
Method: GET
Endpoint: /follow/common/{id}
Description: Queries common follows with another user.
Path Variable:
id (Long): User ID to check
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Common User"
    }
  ]
}

```

ShopController
URL: /shop
Description: Handles shop-related operations.
Query Shop By ID
Method: GET
Endpoint: /shop/{id}
Description: Queries a shop by its ID.
Path Variable:
id (Long): Shop ID
Response:
```
{
  "success": true,
  "data": {
    "id": 1,
    "name": "Shop Name"
  }
}

```


Save Shop
Method: POST
Endpoint: /shop
Description: Saves a new shop.
Request Body:
```
{
  "name": "Shop Name",
  "type": "Shop Type"
}

```
```
{
  "success": true,
  "data": 1
}

```

Update Shop
Method: PUT
Endpoint: /shop
Description: Updates shop information.
Request Body:
```
{
  "id": 1,
  "name": "Updated Shop Name",
  "type": "Updated Shop Type"
}

```

```
{
  "success": true
}

```


Query Shops By Type
Method: GET
Endpoint: /shop/of/type
Description: Queries shops by type.
Request Parameters:
typeId (Integer): Shop type ID
current (Integer, default = 1): Current page number
x (Double): Longitude
y (Double): Latitude
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Shop Name",
      "type": "Shop Type"
    }
  ]
}

```


Query Shops By Name
Method: GET
Endpoint: /shop/of/name
Description: Queries shops by name.
Request Parameters:
name (String, optional): Shop name keyword
current (Integer, default = 1): Current page number
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Shop Name",
      "type": "Shop Type"
    }
  ]
}

```


ShopTypeController
URL: /shop-type
Description: Handles shop type-related operations.
Query Shop Types
Method: GET
Endpoint: /shop-type/list
Description: Queries all shop types.
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Shop Type"
    }
  ]
}
```


UploadController
URL: /upload
Description: Handles file upload operations.
Upload Blog Image
Method: POST
Endpoint: /upload/blog
Description: Uploads an image for a blog.
Request Parameters:
file (MultipartFile): Image file
Response:
```
{
  "success": true,
  "data": "file_path"
}

```



Delete Blog Image
Method: GET
Endpoint: /upload/blog/delete
Description: Deletes a blog image by its file name.
Request Parameters:
name (String): File name
Response:
```
{
  "success": true
}

```


UserController
URL: /user
Description: Handles user-related operations.
Send Verification Code
Method: POST
Endpoint: /user/code
Description: Sends a verification code to the user's phone.
Request Parameters:
phone (String): User's phone number
Response:
```
{
  "success": true
}
```


Login
Method: POST
Endpoint: /user/login
Description: Logs in the user.
Request Body:
```
{
  "phone": "1234567890",
  "code": "1234"
}

```

Response:
```
{
  "success": true,
  "data": {
    "token": "user_token"
  }
}

```

Logout
Method: POST
Endpoint: /user/logout
Description: Logs out the user.
Response:
```
{
  "success": true
}

```

Get Current User
Method: GET
Endpoint: /user/me
Description: Gets the current logged-in user's information.
Response:
```
{
  "success": true,
  "data": {
    "id": 1,
    "name": "User Name"
  }
}
```

Get User Info by ID
Method: GET
Endpoint: /user/info/{id}
Description: Gets user information by user ID.
Path Variable:
id (Long): User ID
Response:
```
{
  "success": true,
  "data": {
    "id": 1,
    "name": "User Name",
    "info": "User Info"
  }
}
```

Get User by ID
Method: GET
Endpoint: /user/{id}
Description: Gets user information by user ID.
Path Variable:
id (Long): User ID
Response:
```
{
  "success": true,
  "data": {
    "id": 1,
    "name": "User Name"
  }
}
```

Sign In
Method: POST
Endpoint: /user/sign
Description: Signs in the user.
Response:
```
{
  "success": true
}

```


VoucherController
URL: /voucher
Description: Handles voucher-related operations.
Add Voucher
Method: POST
Endpoint: /voucher
Description: Adds a new voucher.
Request Body:
```
{
  "name": "Voucher Name",
  "discount": "10%"
}

```

Response:
```
{
  "success": true,
  "data": 1
}

```

Add Seckill Voucher
Method: POST
Endpoint: /voucher/seckill
Description: Adds a new seckill voucher.
Request Body:
```
{
  "name": "Seckill Voucher Name",
  "discount": "10%",
  "seckillInfo": "Seckill Info"
}

```
Response:
```
{
  "success": true,
  "data": 1
}
```


Query Vouchers By Shop ID
Method: GET
Endpoint: /voucher/list/{shopId}
Description: Queries vouchers by shop ID.
Path Variable:
shopId (Long): Shop ID
Response:
```
{
  "success": true,
  "data": [
    {
      "id": 1,
      "name": "Voucher Name",
      "discount": "10%"
    }
  ]
}
```

VoucherOrderController
URL: /voucher-order
Description: Handles voucher order-related operations.
Seckill Voucher
Method: POST
Endpoint: /voucher-order/seckill/{id}
Description: Performs a seckill operation on a voucher.
Path Variable:
id (Long): Voucher ID
Response:
```
{
  "success": true
}

```

