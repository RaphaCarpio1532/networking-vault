# Guía: publicar tu bóveda con Quartz (gratis) — RaphaCarpio1532

Objetivo: convertir la carpeta `Networking-Cybersecurity-Vault` en una web pública con grafo
interactivo, búsqueda y modo oscuro, alojada gratis en GitHub Pages.

Resultado final: `https://raphacarpio1532.github.io/networking-vault`

---

## 0. Requisitos (instalar una sola vez)

- **Node.js** (v22 o superior): https://nodejs.org → descarga "LTS".
- **Git**: https://git-scm.com → descarga e instala.
- Tu cuenta de **GitHub**: RaphaCarpio1532 (ya la tienes).

Para comprobar que quedaron instalados, abre la terminal (PowerShell en Windows) y escribe:

```bash
node -v
git --version
```

Si te muestran números de versión, todo bien.

---

## 1. Descargar Quartz

En la terminal, ejecuta línea por línea:

```bash
git clone https://github.com/jackyzha0/quartz.git
cd quartz
npm i
npx quartz create
```

Cuando `npx quartz create` te pregunte:
- "How to initialize content" → elige **Empty Quartz** (lo llenaremos con tus notas).
- "Links resolved as" → elige **Treat links as shortest path** (recomendado).

---

## 2. Copiar tus notas dentro de Quartz

Tus notas deben ir en la carpeta `quartz/content/`.

1. Borra el archivo de ejemplo `content/index.md` que viene por defecto.
2. Copia TODOS los `.md` de tu carpeta `Networking-Cybersecurity-Vault` dentro de `quartz/content/`.
3. Renombra `00 Home MOC.md` a `index.md`. Ese será la página de inicio.
   - (Opcional) Dentro de ese index.md cambia el título `# 00 Home MOC` por `# Networking for Cybersecurity`.

> El grafo interactivo se genera solo a partir de tus enlaces `[[...]]`. No tienes que configurar nada.

---

## 3. Previsualizar en tu PC

Desde la carpeta `quartz`:

```bash
npx quartz build --serve
```

Abre en el navegador: **http://localhost:8080**

Verás tu sitio con el grafo. Mientras esto corre, cualquier cambio en las notas se actualiza solo.
Para detenerlo: `Ctrl + C`.

---

## 4. Personalizar nombre y autor (opcional pero recomendado)

Abre el archivo `quartz.config.ts` (en la raíz de `quartz`) y edita esta línea:

```ts
pageTitle: "Networking for Cybersecurity",
```

También puedes cambiar idioma y colores ahí. Guarda el archivo.

---

## 5. Crear el repositorio en GitHub

1. Entra a https://github.com/new (con tu cuenta RaphaCarpio1532).
2. Nombre del repositorio: `networking-vault`.
3. Visibilidad: **Public**.
4. **NO** marques "Add a README", ".gitignore" ni "license".
5. Crea el repositorio. GitHub te mostrará una URL parecida a:
   `https://github.com/RaphaCarpio1532/networking-vault.git`

---

## 6. Conectar tu Quartz local con ese repositorio

Desde la carpeta `quartz`, ejecuta:

```bash
git remote add origin https://github.com/RaphaCarpio1532/networking-vault.git
npx quartz sync --no-pull
```

`npx quartz sync` sube tus notas y la configuración a GitHub. Cada vez que quieras
actualizar el sitio en el futuro, solo vuelves a correr `npx quartz sync`.

---

## 7. Activar GitHub Pages (publicación automática)

1. En tu repositorio en GitHub: pestaña **Settings**.
2. Menú izquierdo → **Pages**.
3. En "Build and deployment" → "Source", selecciona **GitHub Actions**.

Quartz ya incluye el flujo de trabajo (workflow) que construye y publica el sitio.
Tras unos minutos, en la pestaña **Actions** verás el proceso en verde cuando termine.

Tu sitio quedará en:

**https://raphacarpio1532.github.io/networking-vault**

---

## 8. Cómo actualizar el sitio más adelante

Cada vez que agregues o edites notas en `quartz/content/`:

```bash
cd quartz
npx quartz sync
```

GitHub vuelve a construir y publicar automáticamente. Listo.

---

## Solución de problemas frecuentes

- **El grafo no aparece**: asegúrate de que las notas tengan enlaces `[[...]]` y que estén
  dentro de `content/`.
- **La página de inicio sale vacía**: revisa que exista `content/index.md`.
- **Error con `npx quartz sync`**: agrega `--no-pull` la primera vez (ya está en el paso 6).
- **El Action falla en GitHub**: en Settings → Pages confirma que "Source" = GitHub Actions.
- **Dominio propio** (ej. tunombre.com): se configura en Settings → Pages → "Custom domain".

---

## Alternativa de alojamiento: Netlify (también gratis)

Si prefieres Netlify en lugar de GitHub Pages: crea cuenta en netlify.com, conecta tu
repositorio `networking-vault`, y en build pon el comando `npx quartz build` y la carpeta
de publicación `public`. Netlify te da una URL automática y SSL gratis.
