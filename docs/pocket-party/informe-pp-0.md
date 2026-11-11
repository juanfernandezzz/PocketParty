# Informe PP-0 · Nacimiento de Pocket Party (2026-11-11)

## A1 · Lectura de ChatCouncil-Unity (sin cambios)

- git status: vacío. Rama main. HEAD 953fbbcfea3914116a23c8c084a93e54d93951b9.
- git fetch; origin/main 953fbbcfea3914116a23c8c084a93e54d93951b9; git rev-list --left-right --count HEAD...origin/main: 0 0.
- Visibilidad en GitHub: PUBLIC, no archivado.
- Workflows (.github/workflows):
  - ci.yml: push a main y pull_request. No publica Release ni usa secretos.
  - prueba-login.yml: push a main con paths prototipos/login-google/** y el propio workflow; workflow_dispatch. Publica el Release prueba-login-google-v1 (gh release create/upload); firma el APK con un keystore generado en el runner.
  - unity.yml: push a main con paths unity/**, panel/**, motor/**, pagina/**, instalador/**, scripts/unity/** y el propio workflow; workflow_dispatch. Publica el Release chatcouncil-unity-v1; usa los secretos UNITY_EMAIL, UNITY_PASSWORD, ANDROID_KEYSTORE_BASE64 y ANDROID_KEYSTORE_PASS; firma Android.
  - Ninguno se dispara con tags.
- Actualizador: unity/Assets/Interfaz/Actualizador.cs:20, const Release = "https://github.com/juanfernandezzz/ChatCouncil-Unity/releases/download/chatcouncil-unity-v1/".
- ProjectSettings (unity/ProjectSettings/ProjectSettings.asset): productName ChatCouncil (línea 16), companyName ChatCouncil (línea 15), bundleVersion 0.1.0 (línea 150), applicationIdentifier Android com.chatcouncil.app (línea 174).
- Git LFS: no (.gitattributes sin filtros lfs; git lfs ls-files: 0).
- LICENSE: no hay archivo LICENSE en la raíz.
- Apariciones de «chatcouncil» (sin distinguir mayúsculas, git grep -o -i en HEAD) por carpeta de primer nivel:

```
.github/ 24
apps/ 44
docs/ 4421
instalador/ 17
motor/ 42
packages/ 9
pagina/ 0
panel/ 6
prototipos/ 7
scripts/ 4
unity/ 79
(archivos de la raíz) 22
```

## A2 · Tag de referencia

- Ningún workflow se dispara con tags (A1).
- Tag anotado referencia-port-chatcouncil sobre 953fbbcfea3914116a23c8c084a93e54d93951b9, mensaje «Referencia de funciones del port ChatCouncil (Rust + Slint). No mover.».
- Subida solo del tag: «* [new tag] referencia-port-chatcouncil -> referencia-port-chatcouncil». git ls-remote: e32132dc85946b3aba32d2faefd7b1b0eed6f252 refs/tags/referencia-port-chatcouncil, ^{} 953fbbcfea3914116a23c8c084a93e54d93951b9.
- https://github.com/juanfernandezzz/ChatCouncil-Unity/releases/tag/referencia-port-chatcouncil

## A3 · Repo nuevo

- juanfernandezzz/PocketParty y la carpeta PocketParty no existían.
- gh repo create juanfernandezzz/PocketParty --public, con la descripción pedida, vacío: https://github.com/juanfernandezzz/PocketParty
- git clone del repo local ChatCouncil-Unity a la carpeta hermana PocketParty; origin reemplazado. git remote -v:

```
origin	https://github.com/juanfernandezzz/PocketParty.git (fetch)
origin	https://github.com/juanfernandezzz/PocketParty.git (push)
```

- Sin LFS: no hubo objetos que traer.

## A4 · Primer commit

- prueba-login.yml y unity.yml quedan con workflow_dispatch como único disparador (publican Release y firman; unity.yml usa secretos). ci.yml no se tocó.
- docs/pocket-party/ORIGEN.md con el texto literal, fecha 2026-11-11 y sha 953fbbcfea3914116a23c8c084a93e54d93951b9.
- Commit d348905838db5be2065203c7bfc6cd96b9a9c377 «Nace Pocket Party desde ChatCouncil-Unity 953fbbc: deja manuales los workflows de publicación y documenta el origen»: 3 archivos, 8 inserciones, 6 borrados.
- Subida normal de main: «* [new branch] main -> main» (sin tags, espejo ni forzado).
