# MuleSoft Product Order API

A comprehensive MuleSoft application demonstrating product and order management APIs with advanced features.

## 🚀 Overview

This MuleSoft application provides REST APIs for managing products and orders in an e-commerce system. It demonstrates:

- **RESTful API Design**: Clean, well-structured endpoints following REST principles
- **RAML API Specifications**: Comprehensive API documentation with examples
- **Object Store Integration**: In-memory data persistence using MuleSoft Object Store
- **Error Handling**: Robust error handling with proper HTTP status codes
- **DataWeave Transformations**: Advanced data transformation capabilities
- **Comprehensive Testing**: Postman collections with realistic test scenarios

## 🏗️ Architecture

### API Endpoints

#### Products API
- `GET /api/products` - Retrieve all products
- `POST /api/products` - Create a new product
- `GET /api/products/{id}` - Get product by ID
- `PUT /api/products/{id}` - Update product

#### Orders API
- `GET /api/orders` - Retrieve all orders
- `POST /api/orders` - Create a new order
- `GET /api/orders/{id}` - Get order by ID
- `PUT /api/orders/{id}` - Update order

### Technology Stack
- **MuleSoft Runtime**: 4.11.2
- **Java**: 17
- **HTTP Connector**: 1.11.1
- **Object Store Connector**: 1.3.0

## 📁 Project Structure

```
src/
├── main/
│   ├── api/
│   │   ├── product-api.raml      # Product API specification
│   │   └── order-api.raml        # Order API specification
│   ├── mule/
│   │   ├── global.xml            # Global configurations
│   │   └── product-order-api.xml # Main application flows
│   └── resources/
│       ├── config.properties     # Configuration properties
│       └── log4j2.xml           # Logging configuration
└── test/
    ├── munit/                   # MUnit test files
    └── resources/
        └── log4j2-test.xml      # Test logging configuration
```

## 🛠️ Setup & Installation

### Prerequisites
- **Java 17** or higher
- **Maven 3.6+**
- **MuleSoft Anypoint Studio** (optional, for development)
- **Anypoint CLI** (optional, for deployment)

### Local Development

1. **Clone the repository:**
   ```bash
   git clone https://github.com/konaparthi-vishal/mulesoft-vibes-demo.git
   cd mulesoft-vibes-demo
   ```

2. **Build the application:**
   ```bash
   mvn clean compile
   ```

3. **Run the application:**
   ```bash
   mvn mule:run
   ```

4. **Access the API:**
   - Base URL: `http://localhost:8081`
   - Products: `http://localhost:8081/api/products`
   - Orders: `http://localhost:8081/api/orders`

## 🧪 Testing

### Postman Collections
The project includes comprehensive Postman collections for testing:

- `Product-Order-API.postman_collection.json` - Complete API test suite
- `Product-Order-API.postman_environment.json` - Environment variables
- `ENHANCED_POSTMAN_GUIDE.md` - Detailed testing guide

### Test Scenarios
- **Realistic Product Catalog**: Gaming laptops, wireless mice, mechanical keyboards
- **E-commerce Workflows**: Complete purchase flows
- **Corporate Procurement**: Bulk order scenarios
- **Customer Service**: Order modifications and cancellations

### Running Tests
1. Import collections into Postman
2. Set up environment variables
3. Run individual tests or complete workflows

## 🔧 Configuration

### Environment Properties (`config.properties`)
```properties
# HTTP Configuration
http.host=0.0.0.0
http.port=8081
```

### Object Store Configuration
- **Product Store**: Manages product data with 1000 max entries
- **Order Store**: Manages order data with 1000 max entries
- **No Expiration**: Data persists for the application lifetime

## 📊 Features

### Advanced Data Management
- **Auto-Generated IDs**: Products and orders get unique identifiers
- **Data Validation**: Input validation with proper error responses
- **Relationships**: Orders reference product IDs for data integrity

### Error Handling
- **404 Not Found**: When products/orders don't exist
- **400 Bad Request**: For invalid input data
- **405 Method Not Allowed**: For unsupported HTTP methods
- **500 Internal Server Error**: For system errors

### DataWeave Transformations
- **JSON Processing**: Complex data transformations
- **UUID Generation**: Unique ID creation for entities
- **Data Mapping**: Request/response format conversion

## 🚀 Deployment

### CloudHub 2.0 Deployment
1. Build the deployable archive:
   ```bash
   mvn clean package
   ```

2. Deploy using Anypoint CLI:
   ```bash
   anypoint-cli runtime-mgr cloudhub2-application deploy --environment=<env> --name=product-order-api target/product-order-api-1.0.0-SNAPSHOT-mule-application.jar
   ```

### Runtime Fabric Deployment
1. Build and deploy:
   ```bash
   mvn clean deploy -DmuleDeploy
   ```

## 📈 Monitoring & Logging

### Application Logs
- **Log Level**: INFO (configurable)
- **Log File**: `product-order-api.log`
- **Rolling Policy**: 10MB files, max 10 files
- **Pattern**: Includes processor path and correlation ID

### Performance Monitoring
- HTTP request/response logging
- Error tracking and reporting
- Processing time metrics

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Support

For questions and support:
- **GitHub Issues**: [Create an issue](https://github.com/konaparthi-vishal/mulesoft-vibes-demo/issues)
- **Documentation**: Check the `/docs` directory for additional guides
- **MuleSoft Community**: [MuleSoft Community Forum](https://help.mulesoft.com/s/forum)

## 🎯 Roadmap

- [ ] Database integration (PostgreSQL/MySQL)
- [ ] Authentication & authorization
- [ ] API rate limiting
- [ ] Caching mechanisms
- [ ] Batch processing capabilities
- [ ] Event-driven architecture integration
- [ ] OpenAPI 3.0 specification migration
- [ ] Container deployment (Docker/Kubernetes)

---

**Happy Coding! 🚀**