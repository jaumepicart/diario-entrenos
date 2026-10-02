# Diario de Entrenos

Web instalable (PWA) con cuentas de usuario. Cada persona crea su cuenta con correo y contraseña y solo ve sus datos.

## Qué hay aquí
- `index.html`: la app entera.
- `vendor/supabase.js`: librería de cuentas y base de datos (copia local).
- `manifest.webmanifest`, `sw.js`, `icons/`: instalación en el móvil y uso sin conexión.

La base de datos ya está creada en Supabase (proyecto `diario-entrenos`) con seguridad por usuario.
La clave que aparece en `index.html` es la clave pública (publishable): está pensada para ir en la web.

## Publicarla (cualquiera de las dos)
1. **Netlify Drop**: entra en https://app.netlify.com/drop y arrastra esta carpeta.
2. **GitHub Pages**: sube la carpeta a un repositorio, Settings > Pages > Deploy from branch > main / root.

## Dos ajustes en Supabase (una sola vez, con la web ya publicada)
Dashboard de Supabase > proyecto `diario-entrenos` > Authentication.

1. **URL Configuration**: pon la dirección de tu web en *Site URL* y añádela también en *Redirect URLs*.
   Sin esto, los enlaces de confirmar correo y de recuperar contraseña apuntan a localhost.
2. **Sign In / Providers > Email**:
   - Si quieres que cualquiera entre al instante al registrarse, desactiva *Confirm email*.
   - Si lo dejas activado, configura un servidor de correo propio (Authentication > SMTP). El correo
     incluido por defecto solo envía unos pocos mensajes por hora y no sirve para varias personas.

## Instalar en el móvil
- iPhone: abrir la web en Safari > Compartir > Añadir a pantalla de inicio.
- Android: abrir en Chrome > menú > Instalar aplicación.

## Cambiar de móvil
Instalar la web otra vez, entrar con el mismo correo y contraseña. Todo vuelve a aparecer.
