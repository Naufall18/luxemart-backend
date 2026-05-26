# 🏗️ LuxeMart Backend - Microservices Architecture

Premium Multi-Vendor Marketplace Backend System

## 📋 Overview

LuxeMart Backend is a comprehensive microservices-based e-commerce platform built with Node.js, designed to handle luxury marketplace operations with high scalability and performance.

## 🎯 Key Features

- **Microservices Architecture** - 12 independent services
- **Multi-Vendor Support** - Complete vendor management system
- **Live Shopping** - Real-time streaming integration
- **Advanced Search** - Elasticsearch-powered product discovery
- **Real-time Chat** - Socket.io messaging system
- **Payment Integration** - Multiple payment gateways
- **Shipping Integration** - Major courier APIs
- **Analytics** - Comprehensive business intelligence

## 🏗️ Architecture

### Microservices

1. **Auth Service** (Port 3001) - Authentication & Authorization
2. **User Service** (Port 3002) - User management & profiles
3. **Product Service** (Port 3003) - Product catalog & search
4. **Vendor Service** (Port 3004) - Vendor operations
5. **Order Service** (Port 3005) - Order processing
6. **Payment Service** (Port 3006) - Payment processing
7. **Shipping Service** (Port 3007) - Logistics management
8. **Review Service** (Port 3008) - Reviews & ratings
9. **Chat Service** (Port 3009) - Real-time messaging
10. **Live Shopping Service** (Port 3010) - Live streaming
11. **Notification Service** (Port 3011) - Push/Email/SMS
12. **Analytics Service** (Port 3012) - Business analytics

### Tech Stack

- **Runtime:** Node.js 18+
- **Framework:** Express.js
- **Language:** TypeScript
- **API Gateway:** Kong
- **Message Queue:** RabbitMQ
- **Databases:**
  - PostgreSQL 15+ (Primary)
  - MongoDB 6+ (Chat, Logs)
  - Redis 7+ (Cache, Sessions)
  - Elasticsearch 8+ (Search)

## 🚀 Getting Started

### Prerequisites

```bash
node >= 18.0.0
npm >= 9.0.0
docker >= 20.0.0
docker-compose >= 2.0.0
```

### Installation

```bash
# Clone repository
git clone https://github.com/yourusername/luxemart-backend.git
cd luxemart-backend

# Install dependencies
npm install

# Setup environment variables
cp .env.example .env

# Start databases with Docker
docker-compose up -d

# Run migrations
npm run migrate

# Seed database
npm run seed

# Start development server
npm run dev
```

### Environment Variables

```env
# Application
NODE_ENV=development
PORT=3000

# Database
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_DB=luxemart
POSTGRES_USER=postgres
POSTGRES_PASSWORD=password

MONGODB_URI=mongodb://localhost:27017/luxemart
REDIS_URL=redis://localhost:6379
ELASTICSEARCH_URL=http://localhost:9200

# JWT
JWT_SECRET=your-secret-key
JWT_EXPIRES_IN=1h
REFRESH_TOKEN_SECRET=your-refresh-secret
REFRESH_TOKEN_EXPIRES_IN=7d

# AWS
AWS_ACCESS_KEY_ID=your-access-key
AWS_SECRET_ACCESS_KEY=your-secret-key
AWS_REGION=us-east-1
AWS_S3_BUCKET=luxemart-assets

# Payment Gateways
STRIPE_SECRET_KEY=sk_test_xxx
STRIPE_WEBHOOK_SECRET=whsec_xxx
PAYPAL_CLIENT_ID=xxx
PAYPAL_CLIENT_SECRET=xxx

# Email
SENDGRID_API_KEY=xxx
EMAIL_FROM=noreply@luxemart.com

# SMS
TWILIO_ACCOUNT_SID=xxx
TWILIO_AUTH_TOKEN=xxx
TWILIO_PHONE_NUMBER=+1234567890

# Push Notifications
FCM_SERVER_KEY=xxx

# Live Streaming
AGORA_APP_ID=xxx
AGORA_APP_CERTIFICATE=xxx
```

## 📁 Project Structure

```
luxemart-backend/
├── services/
│   ├── auth-service/
│   │   ├── src/
│   │   │   ├── controllers/
│   │   │   ├── models/
│   │   │   ├── routes/
│   │   │   ├── middleware/
│   │   │   ├── utils/
│   │   │   └── index.ts
│   │   ├── tests/
│   │   ├── package.json
│   │   └── tsconfig.json
│   ├── user-service/
│   ├── product-service/
│   ├── vendor-service/
│   ├── order-service/
│   ├── payment-service/
│   ├── shipping-service/
│   ├── review-service/
│   ├── chat-service/
│   ├── live-shopping-service/
│   ├── notification-service/
│   └── analytics-service/
├── api-gateway/
│   ├── src/
│   │   ├── config/
│   │   ├── middleware/
│   │   └── index.ts
│   └── kong.yml
├── shared/
│   ├── types/
│   ├── utils/
│   ├── constants/
│   └── interfaces/
├── infrastructure/
│   ├── docker/
│   │   ├── Dockerfile.auth
│   │   ├── Dockerfile.user
│   │   └── ...
│   ├── kubernetes/
│   │   ├── deployments/
│   │   ├── services/
│   │   └── ingress/
│   └── terraform/
├── scripts/
│   ├── migrate.sh
│   ├── seed.sh
│   └── deploy.sh
├── docs/
│   ├── api/
│   ├── architecture/
│   └── deployment/
├── docker-compose.yml
├── package.json
├── tsconfig.json
└── README.md
```

## 🔧 Development

### Running Services

```bash
# Run all services
npm run dev

# Run specific service
npm run dev:auth
npm run dev:user
npm run dev:product

# Run with watch mode
npm run dev:watch
```

### Testing

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:coverage

# Run specific service tests
npm run test:auth
npm run test:user

# Run e2e tests
npm run test:e2e
```

### Database Migrations

```bash
# Create migration
npm run migration:create -- AddUsersTable

# Run migrations
npm run migration:run

# Revert migration
npm run migration:revert
```

## 🐳 Docker

### Build Images

```bash
# Build all services
docker-compose build

# Build specific service
docker-compose build auth-service
```

### Run with Docker

```bash
# Start all services
docker-compose up

# Start in detached mode
docker-compose up -d

# Stop services
docker-compose down

# View logs
docker-compose logs -f auth-service
```

## ☸️ Kubernetes Deployment

```bash
# Apply configurations
kubectl apply -f infrastructure/kubernetes/

# Check deployments
kubectl get deployments

# Check services
kubectl get services

# View logs
kubectl logs -f deployment/auth-service
```

## 📊 Monitoring

- **Prometheus:** http://localhost:9090
- **Grafana:** http://localhost:3000
- **Kibana:** http://localhost:5601

## 🔐 Security

- JWT-based authentication
- Role-based access control (RBAC)
- Rate limiting
- Input validation
- SQL injection prevention
- XSS protection
- CORS configuration
- Helmet.js security headers

## 📈 Performance

- Redis caching
- Database query optimization
- Connection pooling
- Load balancing
- Horizontal scaling
- CDN integration

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📝 API Documentation

API documentation available at: http://localhost:3000/api-docs

## 📄 License

This project is licensed under the MIT License.

## 👥 Team

- Backend Lead: [Your Name]
- DevOps Engineer: [Name]
- Database Admin: [Name]

## 📞 Support

- Email: support@luxemart.com
- Slack: #luxemart-backend
- Documentation: https://docs.luxemart.com

## 🗺️ Roadmap

- [x] Microservices architecture
- [x] Authentication system
- [x] Product catalog
- [x] Order processing
- [ ] AI recommendations
- [ ] Blockchain integration
- [ ] Advanced analytics
- [ ] Mobile SDK

---

**Built with ❤️ by LuxeMart Team**
