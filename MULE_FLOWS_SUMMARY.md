# MuleSoft Application Flows Summary

## Application Architecture

This MuleSoft application implements a complete Product and Order management system with the following flows:

## Product API Flows

### 1. product-apiFlow
- **Endpoint**: `/api/products`
- **Methods**: GET, POST
- **Description**: Main product endpoint routing
- **GET**: Retrieves all products from Object Store
- **POST**: Creates new products with auto-generated IDs

### 2. product-by-id-apiFlow
- **Endpoint**: `/api/products/{id}`
- **Methods**: GET, PUT
- **Description**: Individual product operations
- **GET**: Retrieves specific product by ID
- **PUT**: Updates existing product

## Order API Flows

### 3. order-apiFlow
- **Endpoint**: `/api/orders`
- **Methods**: GET, POST
- **Description**: Main order endpoint routing
- **GET**: Retrieves all orders from Object Store
- **POST**: Creates new orders with product references

### 4. order-by-id-apiFlow
- **Endpoint**: `/api/orders/{id}`
- **Methods**: GET, PUT
- **Description**: Individual order operations
- **GET**: Retrieves specific order by ID
- **PUT**: Updates existing order status and details

## Sub-flows (Business Logic)

### Product Sub-flows
- **get-products-subFlow**: Retrieves all products with error handling
- **get-product-by-id-subFlow**: Retrieves single product with 404 handling
- **create-product-subFlow**: Creates products with UUID generation
- **update-product-subFlow**: Updates products with existence validation

### Order Sub-flows
- **get-orders-subFlow**: Retrieves all orders with error handling
- **get-order-by-id-subFlow**: Retrieves single order with 404 handling
- **create-order-subFlow**: Creates orders with product ID references
- **update-order-subFlow**: Updates orders with validation

## Key Features

1. **Object Store Integration**: Products and orders stored in separate Object Stores
2. **Auto-ID Generation**: UUIDs automatically generated for new entities
3. **Error Handling**: Comprehensive 404, 400, and 500 error responses
4. **DataWeave Transformations**: JSON processing and data mapping
5. **HTTP Status Management**: Proper status codes for all operations
6. **Method Validation**: 405 responses for unsupported HTTP methods

## Data Flow

1. **HTTP Request** → **Router** → **Sub-flow** → **Object Store** → **Response**
2. **Validation** → **Transformation** → **Storage** → **Response Generation**

## Object Store Configuration

- **Product_ObjectStore**: Max 1000 entries, no expiration
- **Order_ObjectStore**: Max 1000 entries, no expiration
- **In-Memory**: Data persists during application runtime

## Error Scenarios Handled

- Product/Order not found (404)
- Invalid request data (400)
- Unsupported methods (405)
- Internal server errors (500)
- Empty collections (200 with empty array)

The complete flow implementations are in `src/main/mule/product-order-api.xml`.