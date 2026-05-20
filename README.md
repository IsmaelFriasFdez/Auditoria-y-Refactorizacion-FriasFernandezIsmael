# **Auditoría de Sostenibilidad** (ASG)

# Fase 1: Inventario y Dimensión Ambiental (A)

1. ## **Medición inicial**. 

   Vamos a utilizar la herramienta *Lighthouse* que ofrece Google en las herramientas para desarrolladores para poder obtener la huella de carbono estimada por visita a la web.  
     
<img width="877" height="678" alt="image" src="https://github.com/user-attachments/assets/8cee8d79-a2af-4b2c-9e44-748e258e6335" />

2. ## Identificación de *Bloatware*.   
   Estos son los tres recursos más pesados que se descargan al abrir la web:
   <img width="536" height="68" alt="image" src="https://github.com/user-attachments/assets/d8977ee2-01ac-4c3d-86b3-eaf7fb2deda7" />

   Estas tres son imágenes de fondo.
3. ## Análisis.

# Fase 2: Dimensión Social y Equidad (S)

1. ## **Test de Accesibilidad**. 

   Para evaluar la accesibilidad que tiene la página web y ver el grado de sostenibilidad social para que pueda ser utilizable por todos los usuarios que entren a la web, vamos a pasar de nuevo la herramienta Lighthouse y marcamos solo accesibilidad.  
   Este sería el test:  
   <img width="538" height="320" alt="image" src="https://github.com/user-attachments/assets/59269a4f-4a50-47b4-bfcd-637befcb2de4" />
2. ## **Identificación de barreras**.
   **Ausencia de descripción en las imágenes:** Las imágenes de las hamburguesas estrella como *La Pantoja* o *La Niño Prodigio* carecen de texto descriptivo alternativo. Los lectores de pantalla utilizados por personas con diversidad funcional visual leen únicamente el nombre genérico del archivo o ignoran el contexto culinario por completo.  
   **Dificultad de lectura:** La identidad visual de la marca gira en torno al ahumado, los botones críticos de navegación de la carta como *"VER CARTA"* o *"PEDIR A DOMICILIO"* presentan ratios de contraste texto-fondo. Esto dificulta la legibilidad para usuarios con baja visión o bajo la luz solar directa.

# Fase 3: Dimensión de Gobernanza y Ética (G)

1. ## **Transparencia**. 
El banner de consentimiento de cookies presenta formalmente los botones *"Rechazar"* y *"Aceptar"* a primer nivel. Sin embargo, se detecta un patrón oscuro por diseño asimétrico: el botón "Aceptar" está alterado mediante el color corporativo brillante, mientras que el botón "Rechazar" adopta un color gris plano que se camufla visualmente con el fondo oscuro de la interfaz. Esto manipula la atención del usuario e induce psicológicamente a una aceptación masiva e inconsciente de cookies de analítica.
   
2. ## **Datos innecesarios**. 
En un aspecto sumamente positivo de gobernanza, la web no incluye formularios complejos de registro o contacto que exijan datos personales excesivos o invasivos. Al resolver el flujo de comunicación mediante enlaces directos estáticos (info@smokedburger.es y número de teléfono), la empresa **cumple con el principio de minimización de datos del RGPD**, reduciendo drásticamente la huella de almacenamiento digital en servidores de bases de datos de terceros y blindarse frente a potenciales filtraciones de datos corporativas.
   
# Fase 4: Propuesta de Refactorización 

* ## **Optimización de activos**. 
* Sustituir todos los recursos .jpg y .png por formatos eficientes como **WebP** y **AVIF**, logrando compresiones de hasta un 75% sin sacrificar calidad.   
  * **Implementación de Lazy Loading nativo:** Diferir la carga de imágenes inferiores hasta que el usuario haga scroll sobre la página, ahorrando así carga y ancho de banda.
 
* ## **Reducción de peticiones**.
* Depurar y eliminar de forma definitiva el módulo JavaScript corrupto de la galería. En su lugar, se realizará un contenedor estático utilizando CSS, lo que elimina peticiones HTTP fallidas y tiempo de procesamiento en el cliente. 
 
* ## **Reflexión sobre la Paradoja de Jevons**.
* Al refactorizar, la velocidad de carga de la web será mucho más rápida y el consumo de datos móviles por cliente bajará considerablemente. Esto provocará un efecto positivo para el negocio: la experiencia de usuario óptima disparará la retención de visitas, atrayendo a nuevos usuarios a diario.
  
# Propuesta de refactorización

