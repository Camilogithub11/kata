# kata
# Reporte de pruebas de API

## 1. GET `/products`

### GET exitoso

**URL:** `https://fakestoreapi.com/products`  
**Código de estado esperado:** `200`  
**Código recibido:** `200`

**Resultado:** 
Se obtuvo un listado completo de productos en formato JSON. La respuesta incluyó 20 productos con sus propiedades: `id`, `title`, `price`, `description`, `category`, `image`, y `rating`.

### GET fallido

**URL:** `https://fakestoreapi.com/productos` 
**Código de estado esperado:** `200`  
**Código recibido:** `404`

**Resultado:**  
La API devolvió una página de error HTML indicando que no se encontró la ruta solicitada.

---

## 2. POST `/products`

### POST exitoso

**URL:** `https://fakestoreapi.com/products`  
**Código de estado esperado:** `200`  
**Código recibido:** `200`

**Body enviado:**
```json
{
  "title": "nuevo producto",
  "price": 29.99
}
```

**Respuesta recibida:**
```json
{
  "id": 21,
  "title": "nuevo producto",
  "price": 29.99
}
```

---

## 3. PUT `/products/1`

### PUT exitoso

**URL:** `https://fakestoreapi.com/products/1`  
**Código de estado esperado:** `200`  
**Código recibido:** `200`

**Body enviado:**
```json
{
  "title": "Ejemplo",
  "price": 99.99
}
```

**Respuesta recibida:**
```json
{
  "id": 1,
  "title": "Ejemplo",
  "price": 99.99
}
```

### PUT fallido

**URL:** `https://fakestoreapi.com/productos/1`  
**Código de estado esperado:** `200`  
**Código recibido:** `404`

**Resultado:**  
Se recibió un mensaje de error HTML: `Cannot PUT /productos/1`.

---

## 4. DELETE `/products/1`

### DELETE exitoso

**URL:** `https://fakestoreapi.com/products/1`  
**Código de estado esperado:** `200`  
**Código recibido:** `200`

**Respuesta recibida:**
```json
{
  "id": 1
}
```

### DELETE fallido

**URL:** `https://fakestoreapi.com/productos/1`  
**Código de estado esperado:** `200`  
**Código recibido:** `404`

**Resultado:**  
Respuesta en HTML indicando que no se encontró la ruta: `Cannot DELETE /productos/1`.

---

## 5. POST `/carts`

### POST exitoso

**URL:** `https://fakestoreapi.com/carts`  
**Código de estado esperado:** `200`  
**Código recibido:** `200`

**Body enviado:**
```json
{
  "userId": 1,
  "date": "2020-03-02",
  "products": [
    { "productId": 1, "quantity": 4 },
    { "productId": 2, "quantity": 1 },
    { "productId": 3, "quantity": 6 }
  ]
}
```

**Respuesta recibida:**
```json
{
  "id": 1,
  "userId": 1,
  "date": "2020-03-02T00:00:00.000Z",
  "products": [
    { "productId": 1, "quantity": 4 },
    { "productId": 2, "quantity": 1 },
    { "productId": 3, "quantity": 6 }
  ],
  "__v": 0
}
```
