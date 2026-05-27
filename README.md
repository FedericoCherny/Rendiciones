# Rendiciones IA — PWA

App para analizar comprobantes de gastos con IA (Claude) y exportar los datos a Excel.  
Funciona en celular y desktop, instalable como app (PWA).

---

## Cómo publicar en GitHub Pages (paso a paso)

### 1. Crear cuenta en GitHub
Si no tenés cuenta, creá una en https://github.com

### 2. Crear un repositorio nuevo
- Entrá a https://github.com/new
- Nombre: `rendiciones-ia` (o el que quieras)
- Visibilidad: **Public** (necesario para GitHub Pages gratis)
- No agregues README ni nada extra
- Hacé clic en "Create repository"

### 3. Subir los archivos

**Opción A — desde el browser (más fácil):**
1. En el repositorio vacío, hacé clic en "uploading an existing file"
2. Arrastrá TODOS los archivos y carpetas de esta carpeta
3. Hacé clic en "Commit changes"

**Opción B — con Git:**
```bash
cd rendiciones-pwa
git init
git add .
git commit -m "primera versión"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/rendiciones-ia.git
git push -u origin main
```

### 4. Activar GitHub Pages
1. En el repositorio, entrá a **Settings** → **Pages**
2. En "Source" seleccioná **Deploy from a branch**
3. Branch: **main**, carpeta: **/ (root)**
4. Hacé clic en **Save**
5. Esperá 2-3 minutos

### 5. Tu URL
La app va a estar en:
```
https://TU-USUARIO.github.io/rendiciones-ia/
```

---

## Cómo instalarla en el celu

### Android (Chrome):
1. Abrí la URL en Chrome
2. Aparece un banner "Agregar a pantalla de inicio" → tocá **Instalar**
3. O desde el menú ⋮ → "Instalar app"

### iPhone (Safari):
1. Abrí la URL en **Safari** (no Chrome)
2. Tocá el botón compartir (cuadrado con flecha)
3. → "Agregar a pantalla de inicio"
4. → "Agregar"

---

## Primer uso

1. Abrí la app → tocá **Admin**
2. Creá un PIN (mínimo 4 dígitos) — este PIN protege la configuración
3. Ingresá la **API key de Anthropic** (conseguila en https://console.anthropic.com)
4. Ajustá los campos a extraer si querés
5. ¡Listo! Compartí la URL con tu equipo

---

## Estructura de archivos

```
rendiciones-pwa/
├── index.html       ← app principal
├── manifest.json    ← configuración PWA
├── sw.js            ← service worker (offline)
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

---

## Notas

- La API key se guarda en el dispositivo (localStorage), no en ningún servidor
- Los resultados también se guardan localmente hasta que exportás el Excel
- Cada miembro del equipo necesita configurar la app con la API key (una vez)
- El PIN es por dispositivo — no se sincroniza entre celuares
