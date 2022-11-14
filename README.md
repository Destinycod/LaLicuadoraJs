# LaLicuadoraJs

Nombre del grupo: La Licuadora

Integrante: Clara Rodriguez

Descripción: El negocio solicita una ecommerce para vender sus productos de indumentaria.

PRODUCTS
URL BASE: /api/products

POST /api/products/ -> Crea un producto.
body{
  title: title,
  description: description,
  img: img,
  categories: categories,
  size: size,
  color: color,
  price: price
}
201{
  Message: Product created 
}
500{
  Message: "Internal Server Error"
  Error: 500
}

PUT /api/products/{id} -> Actualiza un producto, se pueden actualizar algunos campos o todos.
body{
  title: title,
  description: description,
  img: img,
  categories: categories,
  size: size,
  color: color,
  price: price
}
200{
  Message: Product updated 
}
404{
  Message: "Not Found",
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/products/{id} -> Elimina un producto.
body{ }
204{
  Message: "Product has been deleted"
}
404{
  Message: "Not Found",
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/products/{id} -> Obtiene un producto mediante el id del mismo.
body{}
200{
  Message: Product
}
404{
  Message: "Not Found",
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/products/ -> Obtiene una lista de productos.
body{}
200{
  Message: List of all the Products
}
500{
  Message: "Internal Server Error"
  Error: 500
}

AUTHORIZATION
URL BASE: /api/auth/

POST /api/auth/register -> Registra un usuario, esto involucra la creación del mismo.
body{
  username: username,
  email: email,
  password: password
}
201{
  Message: User created 
}
400{
  Message: "Bad request. Some fields are empty",
  Error: 400
}
500{
  Message: "Internal Server Error"
  Error: 500
}

POST /api/auth/login -> Inicia sesión un usuario.
body{
  username: username,
  password: password
}
200{
  Message: User data and access token 
}
401{
  Message: "Wrong username",
  Error: 401
}
401{
  Message: "Wrong password",
  Error: 401
}
500{
  Message: "Internal Server Error"
  Error: 500
}

USERS
BASE URL: /api/users

PUT /api/users/{id} -> Actualiza un usuario, pueden ser todos los campos o algunos.
body{
  username: username,
  email: email,
  password: password,
  isAdmin: false
}
200{
  Message: User updated 
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/users/{id} -> Elimina un usuario.
body{ }
204{
  Message: "User has been deleted"
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/users/{id} -> Obtiene un usuario mediante un id.
body{}
200{
  Message: User data
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/users/ -> Otiene un lista de todos los usuarios.
body{}
200{
  Message: List of all the Users
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/users/{id}/orders -> Obtiene todas las ordenes de un usuario mediante su id.
body{}
200{
  Message: Order data
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/users/{id}/carts -> Obtiene todos los carritos de un usuario mediante su id.
body{}
200{
  Message: Cart data
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

CARTS
BASE URL: /api/carts

POST /api/carts/ -> Crea un carrito.
body{
  userId: userId,
  product: [{productId, quantity}]
}
200{
  Message: Cart created 
}
500{
  Message: "Internal Server Error"
  Error: 500
}

PUT /api/carts/{id} -> Actualiza un carrito, se pueden actualizar todos los campos o solo algunos.
body{
  userId: userId,
  product: {productId, quantity}
}
200{
  Message: Cart updated 
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/carts/{id} -> Elimina un carrito.
body{ }
204{
  Message: "Cart has been deleted"
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/carts/ -> Otiene un lista de todos los carritos.
body{}
200{
  Message: List of all the Carts
}
500{
  Message: "Internal Server Error"
  Error: 500
}

ORDERS
BASE URL: /api/orders

POST /api/orders/ -> Crea una orden.
body{
  userId: userId,
  product: {productId, quantity},
  amount: amount,
  address: address,
  status: "pending"
}
200{
  Message: Order created 
}
500{
  Message: "Internal Server Error"
  Error: 500
}

PUT /api/orders/{id} -> Actualiza una orden, se pueden actualizar un campo o todos.
body{
  userId: userId,
  product: [{productId, quantity}],
  amount: amount,
  address: address,
  status: "pending"
}
200{
  Message: Order updated 
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/orders/{id} -> Elimina una orden.
body{ }
204{
  Message: "Order has been deleted"
}
404{
  Message: "Not Found"
  Error: 404
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/orders/ -> Otiene un lista de todos las ordenes.
body{}
200{
  Message: List of all the Orders
}
500{
  Message: "Internal Server Error"
  Error: 500
}

