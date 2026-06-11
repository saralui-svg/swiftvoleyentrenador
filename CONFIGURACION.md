# Guía de configuración — Swift Voley

## ¿Necesito configurar Supabase?

**No, no es obligatorio.** La aplicación ya funciona con los **87 jugadores de Swift Voley** que compartiste en tu HTML.

Puedes:
- Ver la lista de estudiantes
- Buscar y filtrar
- Ver cumpleaños
- **Agregar nuevos estudiantes** (se guardan en `data/estudiantes-local.json`)

Supabase solo es necesario si quieres guardar todo en la nube (recomendado para uso en varios dispositivos).

---

## Cómo ejecutar la app

```bash
cd volley-manager
npm install
npm run dev
```

Abre http://localhost:3000

---

## ¿Qué es el archivo `.env.local`?

Es un archivo de configuración **privado** (no se sube a Git) donde pones las credenciales de Supabase.

Ya está creado en tu proyecto. Ábrelo y verás algo así:

```
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
```

Están **vacíos a propósito**. La app funciona así.

---

## Si quieres usar Supabase (opcional)

### Paso 1: Crear cuenta
1. Entra a https://supabase.com
2. Regístrate gratis
3. Crea un nuevo proyecto (elige nombre y contraseña de base de datos)

### Paso 2: Obtener credenciales
1. En tu proyecto, ve a **Settings** (engranaje) → **API**
2. Copia **Project URL** → pégala en `.env.local`:
   ```
   NEXT_PUBLIC_SUPABASE_URL=https://abcdefgh.supabase.co
   ```
3. Copia **anon public** (la clave pública) → pégala en:
   ```
   NEXT_PUBLIC_SUPABASE_ANON_KEY=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
   ```

### Paso 3: Crear la tabla
1. Ve a **SQL Editor** en Supabase
2. Abre el archivo `supabase/schema.sql` de este proyecto
3. Copia todo el contenido y pégalo en el editor
4. Haz clic en **Run**

### Paso 4: Reiniciar
```bash
npm run dev
```

¡Listo! Los nuevos estudiantes se guardarán en Supabase.

---

## Agregar un nuevo estudiante

1. Abre la app
2. En el menú lateral, clic en **"Nuevo estudiante"**
3. Llena el formulario
4. Clic en **"Registrar estudiante"**

Sin Supabase → se guarda en `data/estudiantes-local.json`
Con Supabase → se guarda en la nube

## Editar un estudiante existente

1. Ve a **Estudiantes** y abre el perfil de un jugador
2. Clic en el botón **"Editar"** (arriba a la derecha)
3. Modifica los datos que necesites
4. Clic en **"Guardar cambios"**

Los cambios se guardan automáticamente. Si editas un jugador del equipo original, los cambios se guardan en `data/estudiantes-local.json`.

---

## Tu HTML de cumpleaños

El HTML que compartiste **sí sirvió**. De ahí saqué:
- Los 87 nombres del equipo Swift Voley
- Las fechas de cumpleaños
- El género de cada jugador
- Los colores dorado y azul marino del diseño

Todo eso ya está integrado en la aplicación Next.js.
