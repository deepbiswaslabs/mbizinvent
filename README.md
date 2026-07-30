# MBizInvent

**GST-compliant inventory & invoicing system for distributors and small businesses.**

MBizInvent helps you manage customers, products, and stock — then generate professional tax invoices (CGST/SGST) as downloadable PDFs. Built for Indian GST workflows with HSN codes, GSTIN/PAN support, and CSV bulk operations.

[![Laravel](https://img.shields.io/badge/Laravel-12-FF2D20?style=flat-square&logo=laravel&logoColor=white)](https://laravel.com)
[![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?style=flat-square&logo=php&logoColor=white)](https://www.php.net)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

---

## Features

| Module | What it does |
|--------|----------------|
| **Dashboard** | Central hub for day-to-day operations |
| **Customers** | Full CRUD with GSTIN, PAN, state & address; CSV import/export |
| **Products** | Catalog with HSN code, rate, and GST %; CSV import/export |
| **Inventory** | Stock levels per product; CSV import/export |
| **Inventory History** | Track stock in/out movements |
| **Generate Invoice** | Line items, discounts, CGST/SGST, round-off → PDF download |
| **Bulk Invoicing** | Upload CSV to generate multiple invoices at once |
| **Invoice List** | Browse and paginate past invoices |
| **Settings** | Business/distributor profile (name, address, GSTIN, PAN, profit calc) |

---

## Tech Stack

- **Backend:** Laravel 12, PHP 8.2+
- **Frontend:** Blade, AdminLTE, Bootstrap Icons, Vite
- **PDF:** barryvdh/laravel-dompdf
- **Spreadsheet / CSV:** phpoffice/phpspreadsheet
- **Database:** MySQL / SQLite (configurable)

---

## Screenshots

> Add screenshots here for LinkedIn / GitHub portfolio impact  
> Suggested: Dashboard · Invoice form · Generated PDF · Inventory list

```text
docs/screenshots/dashboard.png
docs/screenshots/invoice-form.png
docs/screenshots/invoice-pdf.png
docs/screenshots/inventory.png
```

---

## Getting Started

### Prerequisites

- PHP 8.2+
- Composer
- Node.js & npm
- MySQL (or use SQLite for local demo)

### Installation

```bash
# Clone the repository
git clone https://github.com/deepcoder94/mbizinvent.git
cd mbizinvent

# Install PHP dependencies
composer install

# Environment setup
cp .env.example .env
php artisan key:generate

# Configure database in .env, then migrate
php artisan migrate

# Frontend assets
npm install
npm run build

# Create storage symlink (for invoice PDFs)
php artisan storage:link

# Run the app
php artisan serve
```

App will be available at `http://127.0.0.1:8000`.

### Development (all services)

```bash
composer run dev
```

Runs the Laravel server, queue worker, log viewer, and Vite in parallel.

---

## Project Structure

```text
app/
├── Http/Controllers/     # Customers, Products, Inventory, Invoices, Dashboard
└── Models/               # Customer, Product, Inventory, Invoice, Settings, …
resources/views/
├── components/           # Layout, sidebar, header
└── pages/                # Feature screens + invoice PDF template
routes/web.php            # Application routes
```

---

## Core Workflows

1. **Configure business settings** — GSTIN, PAN, address, profit calculation  
2. **Add customers & products** — manually or via CSV import  
3. **Maintain inventory** — stock updates with history tracking  
4. **Generate invoices** — select customer & products, apply tax/discount, download PDF  
5. **Bulk generate** — upload a prepared CSV (sample download available in-app)

---

## API / Route Overview

| Area | Routes |
|------|--------|
| Home | `GET /` |
| Customers | Resource `/customers` + `/customer/export` · `/customer/import` |
| Products | Resource `/products` + `/product/export` · `/product/import` |
| Inventory | Resource `/inventory` + `/invntry/export` · `/invntry/import` |
| History | `GET /inventoryhistory` |
| Settings | `GET /settings/view` · `POST /settings/update` |
| Invoices | `/invoice/form` · `/invoice/generate` · `/invoice/list` · bulk CSV endpoints |

---

## License

This project is open-sourced under the [MIT license](https://opensource.org/licenses/MIT).

---

## Author

**Deepak** · [@deepcoder94](https://github.com/deepcoder94)

Built as a practical inventory + GST invoicing tool for real distributor workflows.

---

⭐ If this project is useful, consider starring the repo on GitHub.
