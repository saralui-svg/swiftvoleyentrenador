# VolleyManager

Aplicación web profesional para que entrenadores y profesores de vóley gestionen la información de sus estudiantes.

## Características

- **Panel principal** con estadísticas, cumpleaños próximos y accesos rápidos
- **Lista de estudiantes** con foto, datos básicos, buscador y filtros por categoría/edad
- **Perfil individual** de cada estudiante con toda su información
- **Calendario de cumpleaños** organizado por proximidad
- **Diseño responsive** optimizado para móvil y escritorio
- **Interfaz SaaS moderna** con animaciones suaves y paleta deportiva

## Tecnologías

- [Next.js 15](https://nextjs.org/) (App Router)
- [React 19](https://react.dev/)
- [TypeScript](https://www.typescriptlang.org/)
- [Tailwind CSS 4](https://tailwindcss.com/)
- [Supabase](https://supabase.com/) (base de datos)
- [Lucide React](https://lucide.dev/) (iconos)
- [date-fns](https://date-fns.org/) (fechas)

## Inicio rápido

### 1. Instalar dependencias

```bash
cd volley-manager
npm install
```

### 2. Configurar Supabase (opcional)

La aplicación funciona con datos de demostración sin Supabase. Para conectar tu base de datos:

1. Crea un proyecto en [supabase.com](https://supabase.com)
2. Ejecuta el script SQL en `supabase/schema.sql` desde el SQL Editor
3. Copia las credenciales:

```bash
cp .env.local.example .env.local
```

4. Edita `.env.local` con tu URL y anon key de Supabase

### 3. Ejecutar en desarrollo

```bash
npm run dev
```

Abre [http://localhost:3000](http://localhost:3000) en tu navegador.

## Estructura del proyecto

```
volley-manager/
├── src/
│   ├── app/                  # Páginas (App Router)
│   │   ├── page.tsx          # Panel principal
│   │   ├── estudiantes/      # Lista y perfiles
│   │   └── cumpleanos/       # Calendario de cumpleaños
│   ├── components/
│   │   ├── dashboard/        # Componentes del panel
│   │   ├── layout/           # Sidebar, header, shell
│   │   ├── students/         # Tarjetas, filtros, búsqueda
│   │   └── ui/               # Componentes base reutilizables
│   └── lib/
│       ├── data.ts           # Capa de acceso a datos
│       ├── mock-data.ts      # Datos de demostración
│       ├── types.ts          # Tipos TypeScript
│       └── utils.ts          # Utilidades (edad, fechas, filtros)
└── supabase/
    └── schema.sql            # Esquema de base de datos
```

## Páginas

| Ruta | Descripción |
|------|-------------|
| `/` | Panel principal con estadísticas |
| `/estudiantes` | Lista con búsqueda y filtros |
| `/estudiantes/[id]` | Perfil individual |
| `/cumpleanos` | Próximos cumpleaños |

## Licencia

Proyecto educativo — uso libre.
