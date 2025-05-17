# APP

Proyecto **Angular 19 + Ionic** completamente dockerizado.

| Entorno | Servicio (imagen)        | Puerto | Propósito                              |
|---------|--------------------------|--------|----------------------------------------|
| Dev     | `frontend-dev` (Node 20) | 4200   | `ng serve` con recarga en vivo         |
---

## 🛠 Requisitos

* Docker 20 o superior  
* Docker Compose v2 (`docker compose`)  
* 4 GB de RAM libres recomendados para el watcher de Angular

---

## 🚀 Puesta en marcha

```bash
git clone https://github.com/DiegoDelgadoMao/parcial-corte2
cd parcial-corte2
```

### 1 · Entorno **desarrollo**

```bash
docker compose up -d --build dbmysql backend frontend-test
```

* Navega a **http://localhost:4200**  
* Cambios en `src/` → recarga automática  
* Detener:

```bash
docker compose --profile dev stop frontend-dev
```

* Abre **http://localhost:8080**  
* Re‑build tras cambios:

```bash
docker compose build frontend
docker compose up -d frontend
```

---

## 📂 Estructura

```
directorio/
├── .vscode/
│   ├── settings.json
│   └── launch.json
├── backend/
│   ├── app-movil/
│   │   ├── controllers/
│   │   ├── models/
│   │   ├── routes/
│   │   └── index.js
│   ├── config/
│   │   └── database.js
│   └── server.js
├── frontend/
│   ├── .angular/
│   ├── dist/
│   ├── node_modules/
│   ├── public/
│   ├── src/
│   │   ├── app/
│   │   │   ├── shared/
│   │   │   │   ├── ionic-standalone.ts
│   │   │   ├── pages/
│   │   │   │   ├── factura-encabezado/
│   │   │   │   │   ├── factura-encabezado.component.html
│   │   │   │   │   └── home.component.ts
│   │   │   │   ├── home/
│   │   │   │   │   ├── home.component.html
│   │   │   │   │   └── factura-encabezado.component.ts
│   │   │   │   ├── pago-método/
│   │   │   │   │   ├── pago-metodo.component.html
│   │   │   │   │   └── pago-metodo.component.ts
│   │   │   │   ├── productos/
│   │   │   │   │   ├── productos.component.html
│   │   │   │   │   └── productos.component.ts
│   │   │   ├── app.component.css
│   │   │   ├── app.component.html
│   │   │   ├── app.component.ts
│   │   │   ├── app.config.ts
│   │   │   └── app.routes.ts
│   │   ├── theme/
│   │   │   └── variables.css
│   │   ├── main.ts
│   │   ├── styles.css
│   │   └── index.html
│   ├── angular.json
│   ├── ionic.config.json
│   ├── package.json
│   ├── Dockerfile
│   └── capacitor.config.ts
├── .editorconfig
├── .gitignore
├── README.md
└── docker-compose.yml
```

---

## 📂 API SWAGGER BACKEND
Ingresar en el navegador la ruta:
```
http://localhost:9000/swagger-ui/index.html
```

---

## ♻️ Limpieza

```bash
docker compose down --rmi all --volumes --remove-orphans
```

---

## 📚 Recursos

* [Angular CLI](https://angular.dev/tools/cli)  
* [Ionic Docs](https://ionicframework.com/docs)  
* [Docker Compose](https://docs.docker.com/compose/)