# LaLicuadoraJs

Nombre del grupo: La Licuadora

Integrante: Clara Rodriguez

Descripción: El negocio solicita una ecommerce para vender sus productos de indumentaria.

PRODUCTS
URL BASE: /api/products

POST /api/products/ -> Crea un producto, sólo un usuario que es Administrador puede crear.
body{
  title: title,
  description: description,
  img: img,
  categories: categories,
  size: size,
  color: color,
  price: price
}
40{
  Message: "Token is not valid"
  Error: 40
}
201{
  Message: Product created 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

PUT /api/products/{id} -> Actualiza un producto, sólo un usuario que es Administrador puede actualizar.
body{
  title: title,
  description: description,
  img: img,
  categories: categories,
  size: size,
  color: color,
  price: price
}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Product updated 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/products/{id} -> Elimina un producto, sólo un usuario que es Administrador puede eliminar.
body{ }
40{
  Message: "Token is not valid"
  Error: 40
}
204{
  Message: "Product has been deleted"
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/products/{id} -> Obtiene un producto mediante el id del mismo, cualquier tipo de usuario puede verlo.
body{}
200{
  Message: Product
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/products/ -> Obtiene una lista de productos, cualquier tipo de usuario puede verlo.
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

POST /api/auth/register -> Registra un usuario.
body{
  username: username,
  email: email,
  password: password
}
201{
  Message: User created 
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
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: User data and access token 
}
401{
  Message: "Wrong Credentials"
  Error: 401
}
500{
  Message: "Internal Server Error"
  Error: 500
}

USERS
BASE URL: /api/users

PUT /api/users/{id} -> Actualiza un usuario, sólo un usuario que es Administrador puede actualizar.
body{
  username: username,
  email: email,
  password: password,
  isAdmin: false
}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: User updated 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/users/{id} -> Elimina un usuario, sólo un usuario que es Administrador puede eliminar.
body{ }
40{
  Message: "Token is not valid"
  Error: 40
}
204{
  Message: "User has been deleted"
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/users/{id} -> Obtiene un usuario mediante un id, sólo un usuario que es Administrador puede solicitar el recurso.
body{}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: User data
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/users/ -> Otiene un lista de todos los usuario, sólo un usuario que es Administrador puede obtener la lista.
body{}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: List of all the Users
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

CARTS
BASE URL: /api/carts

POST /api/carts/ -> Crea un carrito, cualquier usuario que tenga el token puede crear.
body{
  userId: userId,
  product: {productId, quantity}
}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Cart created 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
500{
  Message: "Internal Server Error"
  Error: 500
}

PUT /api/carts/{id} -> Actualiza un carrito, sólo un usuario que tenga el token o sea del tipo administrador puede actualizar.
body{
  userId: userId,
  product: {productId, quantity}
}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Cart updated 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/carts/{id} -> Elimina un carrito, sólo un usuario que tenga el token o sea del tipo administrador puede eliminar.
body{ }
40{
  Message: "Token is not valid"
  Error: 40
}
204{
  Message: "Cart has been deleted"
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/carts/{id} -> Obtiene el carrito de un usuario mediante un id, sólo un usuario que tenga el token o sea del tipo administrador puede solicitar el recurso.
body{}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Cart data
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/carts/ -> Otiene un lista de todos los carritos, sólo un usuario que es Administrador puede obtener la lista.
body{}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: List of all the Carts
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

ORDERS
BASE URL: /api/orders

POST /api/orders/ -> Crea una orden, cualquier usuario que tenga el token puede crear.
body{
  userId: userId,
  product: {productId, quantity},
  amount: amount,
  address: address,
  status: "pending"
}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Order created 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
500{
  Message: "Internal Server Error"
  Error: 500
}

PUT /api/orders/{id} -> Actualiza una orden, sólo un usuario que tenga el token o sea del tipo administrador puede actualizar.
body{
  userId: userId,
  product: {productId, quantity},
  amount: amount,
  address: address,
  status: "pending"
}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Order updated 
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

DELETE /api/orders/{id} -> Elimina una orden, sólo un usuario que tenga el token o sea del tipo administrador puede eliminar.
body{ }
40{
  Message: "Token is not valid"
  Error: 40
}
204{
  Message: "Order has been deleted"
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/orders/{id} -> Obtiene la orden de un usuario mediante un id, sólo un usuario que tenga el token o sea del tipo administrador puede solicitar el recurso.
body{}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: Order data
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

GET api/orders/ -> Otiene un lista de todos las ordenes, sólo un usuario que es Administrador puede obtener la lista.
body{}
40{
  Message: "Token is not valid"
  Error: 40
}
200{
  Message: List of all the Orders
}
401{
  Message: "You are not authenticated"
  Error: 401
}
403{
  Message: "You are not allowed"
  Error: 403
}
500{
  Message: "Internal Server Error"
  Error: 500
}

