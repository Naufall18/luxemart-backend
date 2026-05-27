# ⚙️ Velvoria - Premium Multi-Vendor Backend API

<div align="center">
  <img src="https://images.unsplash.com/photo-1558494949-ef010cbdcc31?auto=format&fit=crop&q=80&w=1000" alt="Velvoria Backend Banner" width="100%" style="border-radius: 16px; margin-bottom: 20px;" />

  [![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=for-the-badge&logo=laravel&logoColor=white)](#)
  [![PHP](https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white)](#)
  [![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](#)
  [![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)](#)
</div>

---

## ✨ Overview

**Velvoria Backend** serves as the primary engine driving the Velvoria ecosystem. Engineered using **Laravel 11**, it manages multi-tenant vendor schemas, secure payment integrations, order processing queues, and real-time inventory databases. It is designed to scale dynamically, supporting heavy concurrency from buyer client apps and seller dashboard consoles.

---

## 🚀 Core API Modules

* **🔐 Authentication & Access Control** - Secure JWT & Sanctum integration, robust role permissions (Super Admin, Vendor, Buyer).
* **🏪 Vendor Hub** - Store registration, business validation, balance settlement, and custom shipping options.
* **📦 Product Catalog & Variants** - Detailed product listings supporting extensive attribute variations (size, color, material) and AR assets.
* **💳 Order Engine** - Checkout workflow, payment gateway integration (Midtrans/Stripe), escrow balance system, and delivery dispatch.
* **💬 Messaging & Live Hub** - API handlers supporting real-time chat threads and live stream scheduler logs.

---

## 🛠️ Technology Stack

- **Framework:** Laravel 11
- **Language:** PHP 8.2+
- **Database:** MySQL / PostgreSQL
- **Caching & Queue:** Redis
- **Security:** Laravel Sanctum (Token authentication) & Shield Middleware

---

## 📥 Getting Started

### Prerequisites

- PHP >= 8.2
- Composer
- Database engine (MySQL/PostgreSQL)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/Naufall18/velvoria-backend.git
   cd velvoria-backend
   ```

2. **Install composer dependencies**
   ```bash
   composer install
   ```

3. **Configure environment environment**
   ```bash
   cp .env.example .env
   php artisan key:generate
   ```
   *Edit `.env` and specify your DB credentials, Redis configs, and Payment Keys.*

4. **Run database migrations & seeders**
   ```bash
   php artisan migrate --seed
   ```

5. **Start Laravel dev server**
   ```bash
   php artisan serve
   ```
   API endpoints will be exposed at [http://127.0.0.1:8000](http://127.0.0.1:8000).

---

## 📐 Project Structure & Endpoints

```
velvoria-backend/
├── app/
│   ├── Http/Controllers/   # API Request handlers (Auth, Order, Product)
│   ├── Models/             # Database relationships & entities
│   └── Providers/          # Core services configuration
├── config/                 # System setting variables
├── database/               # Migrations, factories, and system seeders
├── routes/
│   └── api.php             # Main REST API routes
└── tests/                  # Automated integration tests
```

---

<div align="center">
  <sub>Developed by <a href="https://github.com/Naufall18">Naufall18</a>. Architected for peak security and speed.</sub>
</div>