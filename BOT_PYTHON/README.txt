====================================================
 DETECTOR DE NÚMEROS - EXE PORTABLE
====================================================

🟢 Bienvenido al sistema de detección automática de números desde contenido web o visual.

Este programa permite realizar lecturas periódicas desde una página web, buscando coincidencias numéricas definidas por el usuario. Si no se detectan mediante texto, se aplica OCR sobre capturas automáticas.

----------------------------------------------------
🖥️ Requisitos del sistema
----------------------------------------------------

✔️ Windows 10/11 (consola activa)  
✔️ Google Chrome versión recomendada: **v138.0.7204.158**  
✔️ Conexión a internet (si la URL lo requiere)  
✔️ No se requiere instalación de Python ni Tesseract  

----------------------------------------------------
📂 Archivos incluidos
----------------------------------------------------

📁 resultado/ ................ Carpeta donde se guardan las lecturas y capturas  
📁 tesseract/ ............... Incluye Tesseract OCR embebido  
📁 chrome_driver/ ........... Incluye ChromeDriver embebido  
🟩 main.exe .................. Ejecutable principal del sistema  
📝 config.json .............. Archivo de configuración personalizada  
📝 README.txt ............... Este documento de ayuda  

----------------------------------------------------
⚙️ Configuración (config.json)
----------------------------------------------------

Edita este archivo para definir:

🔗 URL objetivo  
🔢 Lista de números a detectar  
🔁 Número de repeticiones  
⏱️ Intervalo entre lecturas (segundos)  
📸 Activar OCR si no hay texto (usar_ocr)  
💬 Modo interactivo (true/false)  
🧩 Rutas locales para Tesseract y ChromeDriver  

Ejemplo:

{
    "url": "https://blank.page/",
    "target_list": ["2", "5", "11"],
    "repeticiones": 10,
    "intervalo_segundos": 3,
    "usar_ocr": true,
    "forzar_ocr": false,
    "modo_interactivo": false,
    "tesseract_path": "tesseract/tesseract.exe",
    "chromedriver_path": "chrome_driver/chromedriver.exe"
}

----------------------------------------------------
▶️ Modo de uso
----------------------------------------------------

📍 MODO INTERACTIVO (`modo_interactivo: true`)

Permite escribir directamente en la página web. Ideal para campos dinámicos como editores o apps que muestran contenido en tiempo real.

▪ El sistema lee el texto editable cada intervalo  
▪ Si no detecta coincidencias, realiza OCR sobre una captura  
▪ Para salir, puedes:
   ▸ Escribir "EXIT" en el campo editable  
   ▸ Presionar la tecla ESC  
   ▸ Presionar cualquier tecla en consola  

📍 MODO NO INTERACTIVO (`modo_interactivo: false`)

Ideal para páginas estáticas que no requieren intervención manual. El sistema:

▪ Refresca la página en cada lectura  
▪ Extrae texto directamente del HTML  
▪ Aplica OCR si no se detectan coincidencias o si se forza  
▪ Finaliza automáticamente tras las repeticiones definidas  

----------------------------------------------------
📂 Salida
----------------------------------------------------

El archivo `resultado_YYYYMMDD_HHMMSS.txt` se guarda en la carpeta `resultado/`, con el historial completo de detecciones por lectura y método utilizado.

Las capturas por OCR también se almacenan allí si fueron necesarias.

----------------------------------------------------
⚠️ Compatibilidad con Google Chrome
----------------------------------------------------

Este sistema utiliza ChromeDriver para controlar el navegador Chrome. Es esencial que la versión instalada de Chrome en el equipo coincida con la del ChromeDriver incluido.

🛠 ChromeDriver incluido:
Google Chrome v138.0.7204.158

Si la versión de Chrome del usuario es distinta, el sistema podría fallar al iniciar. En ese caso, aparecerá un error como:

SessionNotCreatedException: This version of ChromeDriver only supports Chrome version XX


🔧 ¿Cómo resolverlo?

1. Actualizar Chrome a la versión compatible  
2. Reemplazar `chrome_driver/chromedriver.exe` por uno que coincida con la versión del Chrome instalado:  
   https://chromedriver.chromium.org/downloads

----------------------------------------------------
❓ Soporte
----------------------------------------------------

Para modificar el comportamiento, ajustar el análisis o depurar el sistema, puedes contactar al autor o revisar los archivos generados dentro de la carpeta `resultado`.

¡Gracias por usar el sistema!
