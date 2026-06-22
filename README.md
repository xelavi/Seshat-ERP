# Sazed ERP

Sistema ERP web para la gestión de pymes y autónomos, desarrollado como
Trabajo de Fin de Grado. Incluye módulos de productos, clientes, proveedores,
facturas, compras, personal y un CRM social, además de integraciones con Odoo
y PrestaShop.

## Tecnologías

- **Backend:** Django 5 + Django REST Framework, PostgreSQL.
- **Frontend:** Vue 3 (Composition API) + Vite.
- **Integraciones:** Odoo y PrestaShop vía Docker Compose.

## Requisitos

- Python 3.12
- Node.js 18+
- PostgreSQL

## Puesta en marcha

### Backend

```bash
cd backend
python -m venv .venv
source .venv/bin/activate        # En Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Crea un archivo `backend/.env` con la configuración de la base de datos y las
claves necesarias (no se incluye en el repositorio). Después:

```bash
python manage.py migrate
python manage.py runserver
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

El frontend queda disponible en `http://localhost:5173` y consume la API del
backend en `http://localhost:8000`.

## Integraciones (opcional)

Los servicios de Odoo y PrestaShop se levantan con Docker:

```bash
docker compose -f docker-compose.odoo.yml up -d
docker compose -f docker-compose.prestashop.yml up -d
```

## Estructura del proyecto

- `backend/` — API REST con Django (un módulo por app).
- `frontend/` — SPA en Vue 3.
- `odoo_addons/`, `odoo_config/` — configuración de la integración con Odoo.
- `scripts/` — utilidades de apoyo.
