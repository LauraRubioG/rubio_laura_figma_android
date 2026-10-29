# 🦆 PicoPato - Interfaz de Usuario (UI) y Desarrollo Android

Este repositorio contiene la implementación nativa en Android de la pantalla de inicio de sesión e interfaz principal para **PicoPato**, una aplicación móvil orientada a una tienda de ropa infantil. El proyecto forma parte del ciclo de Desarrollo de Aplicaciones Multiplataforma (DAM) y se centra en la traducción fiel de un diseño de Figma a código XML, aplicando buenas prácticas de arquitectura y optimización de recursos.

## 📌 Enlaces Rápidos

*   🎨 **[Ver Diseño Original en Figma](https://www.figma.com/design/Z7zB8doIT20S0F7ZJQeOlc/T1-%C2%B7-PicoPato-%C2%B7-Laura-Rubio?node-id=33-62&t=ydM9QgFqPOi2LJWG-1)**
*   📄 **[Leer Memoria Técnica del Proyecto (PDF)](docs/rubio_laura_figma_android.pdf)**

---

## 🛠️ Tecnologías y Herramientas

*   **Entorno:** Android Studio
*   **Lenguaje de UI:** XML (ConstraintLayout)
*   **Diseño y Prototipado:** Figma
*   **Control de Versiones:** Git & GitHub

---

## 📂 Estructura del Proyecto

La arquitectura del repositorio sigue los estándares de Android Studio, separando claramente el código fuente de la documentación técnica:

```text
📦 PicoPato
 ┣ 📂 app/            # Código fuente, layouts XML y recursos (Assets)
 ┣ 📂 docs/           # Documentación y memoria del proyecto
 ┃ ┗ 📜 rubio_laura_figma_android.pdf
 ┣ 📂 gradle/         # Wrappers y configuración de compilación
 ┣ 📜 .gitignore      # Reglas de exclusión para Git
 ┗ 📜 build.gradle.kts # Scripts de construcción de Gradle
```

---

## ✨ Características de la Implementación

El desarrollo se ha planteado bajo una mentalidad estructurada, priorizando el "Clean Code" y la separación de responsabilidades en la interfaz gráfica:

### 1. Desacoplamiento de Recursos (Clean Architecture)
Todo el diseño se ha centralizado en el directorio `res/values/` para garantizar una alta mantenibilidad:
*   **`colors.xml`**: Paleta de colores semántica (Primary, Outline, Surface).
*   **`strings.xml`**: Textos internacionalizables.
*   **`styles.xml`**: Tipografías y tamaños estandarizados (TextoTitulo, TextoInput, TextoBotonPrimario).

### 2. Optimización de Assets (Rendimiento)
Se ha evitado la carga innecesaria de mapas de bits pesados para optimizar el tamaño del APK y el consumo de RAM:
*   **Imágenes Ligeras:** El logotipo principal (patos) ha sido exportado en la densidad correcta (`xxhdpi`) y convertido de PNG a **WebP**, logrando una compresión brutal (de 579.8 KB a 28.9 KB, reduciendo el peso a un 4%).
*   **Iconografía Escalable:** El icono del botón de Google (SSO) se ha importado desde el formato SVG oficial de la marca a **VectorDrawable** (`ic_google.xml`), garantizando nitidez infinita sin pixelado en cualquier resolución.

### 3. Instrucciones de Dibujo (Programmatic UI)
Los fondos de los elementos interactivos no son imágenes estáticas, sino archivos `<shape>` programados directamente en XML dentro de la carpeta `res/drawable/`. Esto permite aplicar bordes dinámicos y radios de curvatura adaptables con coste cero de rendimiento:
*   `bg_btn_entrar.xml`
*   `bg_btn_google.xml`
*   `bg_input_correo.xml`
*   `bg_input_contrasena.xml`

### 4. Layout Reactivo
Estructura construida mediante `ConstraintLayout` en `activity_main.xml`, asegurando que todos los componentes mantengan sus anclajes y proporciones exactas independientemente del tamaño de la pantalla del dispositivo.

---

## 👩‍💻 Autoría

**Laura Rubio Gallardo** ([@LauraRubioG](https://github.com/LauraRubioG))
*Desarrollo de Aplicaciones Multiplataforma (DAM)*