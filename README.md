# 🏬 Showroom Colocio Outlet | Maqueta 3D & Plano Comercial Interactivo

Sistema web interactivo Three.js de última generación para el diseño espacial, visualización 3D y control comercial a escala real 1:1, adaptado a los planos arquitectónicos de la tienda **Colocio Outlet** (`PLANO OUTLET.pdf`) del **Grupo Anipa**.

- **Repositorio Oficial:** [https://github.com/ikerreyna3942-debug/colosio](https://github.com/ikerreyna3942-debug/colosio)
- **Enlace Público en GitHub Pages:** [https://ikerreyna3942-debug.github.io/colosio/](https://ikerreyna3942-debug.github.io/colosio/)

---

## 📐 Especificaciones Arquitectónicas Reales (`PLANO OUTLET.pdf`)

- **Longitud Total (Eje X):** `38.50 metros` (7 módulos estructurales definidos por las vigas maestras).
- **Ancho Total (Eje Z):** `12.00 metros` (luz transversal libre).
- **Altura Libre:** `3.50 metros`.
- **Estructura Portante:** 7 vigas transversales de techo ("PROYECCIÓN DE VIGA") espaciadas a 5.50m.
- **Acceso Comercial:** Vano de `5.00 metros` de anchura.
- **Zonificación Comercial Mapeada:**
  - Área de Exhibición de Tapetes
  - Área de Exhibición de Mesas de Centro
  - Área de Exhibición de Sillas
  - Área de Exhibición de Blancos
  - Área de Cuadros y Espejos
  - Proyección de Repisas y Vigas

---

## 🌟 Características Implementadas

### 1. Construcción del Plano 3D a Medida Exacta
- **Escala 1:1:** 1 unidad de Three.js equivale a 1 metro arquitectónico.
- **Muro Slider Dinámico:** Control deslizante de 0% (plano diáfano a nivel de suelo) a 100% (muros sólidos a 3.50m).
- **Superposición de Plano AutoCAD 2D:** Proyección del plano original (`TIENDA/PLANOS/plano_outlet.png`) directamente sobre el suelo.

### 2. Catálogo 3D Indexado (.GLB)
- **28 Modelos 3D Reales:** Camas, Sofás, Sillones, Bufeteras, Burós, Credenzas y Sillería.
- **Script `auto_sync_catalog.py`:** Extrae las cotas métricas reales de los accessors binarios de los `.glb` y genera `modelos_glb_data.js`.

### 3. Semáforo Técnico de Ventas Ultrabrillante (+20% Luminosidad)
Siluetas métricas en el suelo bajo cada mueble:
- **Baja (< 15 unidades):** `#ff8f8f` (Coral vivo)
- **Baja-Media (15–30 unidades):** `#ffe285` (Amarillo oro)
- **Alta-Media (30–50 unidades):** `#ffd2a8` (Naranja durazno)
- **Alta (> 50 unidades):** `#b6e6a4` (Verde menta brillante)
- *Material:* `opacity: 0.30`, borde `1.0`, y `toneMapped: false` (inmune a la atenuación de la iluminación 3D).

### 4. Adosamiento Inteligente y Micro-desplazamiento
- **D-Pad de 5 cm (◀ ▶ ▲ ▼):** Ajuste milimétrico para calzar muebles.
- **Botón `[ 🧲 Pegar ]`:** Alineación magnética inmediata contra el mueble adyacente sin penetración de mallas.
- **Rotación:** Giro rápido de 90°.

### 5. Google Sheets en Tiempo Real
- Endpoint GViz con polling cada 30 segundos (`setInterval`).
- Actualiza sin recargar el catálogo, la Ficha Técnica y los semáforos 3D.

### 6. Persistencia y Distribuciones
- Prefijo LocalStorage exclusivo: `colocio_outlet_distribs_`.
- Guardado rápido con `Ctrl + S` y Toast flotante.
- Gestor modal de distribuciones (Cargar, Guardar, Eliminar, Exportar/Importar JSON).
- Enlaces compartibles con hash Base64 (`#distrib=...`).

---

## 🚀 Cómo Ejecutar en Local

Abre una terminal en la carpeta `TIENDA` y ejecuta:
```bash
python -m http.server 8080
```
Y abre tu navegador en: **`http://localhost:8080`**

---

## 📦 Sincronización y Despliegue

- **`ACTUALIZAR_CATALOGO.bat`:** Reindexa modelos 3D y fotografías.
- **`DESPLEGAR_A_GITHUB.bat`:** Sincroniza y despliega la aplicación a [https://github.com/ikerreyna3942-debug/colosio](https://github.com/ikerreyna3942-debug/colosio).
