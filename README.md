# **Auditoría de Sostenibilidad** (ASG)

# Fase 1: Inventario y Dimensión Ambiental (A)

1. ## **Medición inicial**. 

   Vamos a utilizar la herramienta *Website Carbon Calculator* para poder obtener la huella de carbono estimada por visita a la web.  
     
<img width="877" height="678" alt="image" src="https://github.com/user-attachments/assets/8cee8d79-a2af-4b2c-9e44-748e258e6335" />

2. ## Identificación de *Bloatware*.   
   Estos son los tres recursos más pesados que se descargan al abrir la web:
   <img width="536" height="68" alt="image" src="https://github.com/user-attachments/assets/d8977ee2-01ac-4c3d-86b3-eaf7fb2deda7" />

   Estas tres son imágenes de fondo.
3. ## Análisis.
La página web experimenta una notable inflación de software. La web actúa como una landing page cuyo propósito es exponer la carta de hamburguesas, el horario comercial y los datos de contacto del local. Sin embargo, transferir más de 6 MB de datos para una estructura de contenidos tan simple demuestra que la web arrastra una severa "deuda técnica" ecológica. El uso de recursos gráficos gigantescos, librerías de scripts redundantes de terceros y hojas de estilo no minificadas obliga al hardware del cliente a realizar ciclos de computación innecesarios, lo que incrementa exponencialmente el consumo eléctrico y la huella de carbono digital de la empresa local.
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
<img width="934" height="108" alt="image" src="https://github.com/user-attachments/assets/71974212-17e4-4ea2-9e6b-3c7fc9949068" />
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
## Optimización de Imágenes: De JPG/PNG a WebP o AVIF 

Antes:

| \<img src="img/hero-burger.jpg"\> |
| :---- |

Después:

| \<img src="img/hero-burger.webp" alt="Hamburguesa ahumada" loading="lazy"\>  |
| :---- |

## Contraste Cromático y Accesibilidad en Botones de Acción 

Antes:  
/\* Texto dorado claro sobre fondo gris oscuro ahumado \*/  
.btn-ver-carta {  
    background-color: \#1a1a1a;  
    color: \#dfc15d;  
    padding: 12px 24px;  
}

Después:  
/\* Contraste mejorado aumentando la oscuridad del fondo y la saturación del texto \*/  
.btn-ver-carta {  
    background-color: \#0d0d0d;  
    color: \#ffdf6d; /\* Tonalidad ajustada para alta legibilidad \*/  
    font-weight: 700;  
    padding: 12px 24px;  
    border: 2px solid \#ffdf6d;  
}  
.btn-ver-carta:focus {  
    outline: 3px solid \#ffdf6d; /\* Facilita la navegación mediante teclado \*/  
}

—---------------------------------------------------------------

Y utilice WAVE para comprobar el código refactorizado:  
Antes:  
<img width="376" height="452" alt="Captura de pantalla 2026-05-27 121514" src="https://github.com/user-attachments/assets/4ab5f09b-fc78-4eae-a1a2-a936fea5e754" />  
Después:  
<img width="380" height="459" alt="Captura de pantalla 2026-05-27 121220" src="https://github.com/user-attachments/assets/8ae9f021-bf05-4c26-9ab6-f2e5ce6db866" />

# Paradoja de Jevons

Es un fenómeno económico y ecológico que dice: **"Cuanto más eficiente haces un recurso, más aumenta su consumo total"**.

Si optimizas la web para que cargue instantáneamente, la experiencia del usuario será genial. Esto atraerá a muchos más clientes diarios. Si pasas de tener 100 visitas al día a tener 10,000, **el consumo de energía global de la web subirá**, anulando por completo el ahorro energético que habías conseguido con tu código limpio.

Para que el aumento de tráfico no destruya el ahorro energético, debes aplicar dos soluciones técnicas: 

1. **Green Hosting:** Aloja la web en servidores que funcionen con **energía 100% renovable**. Si los servidores usan energía limpia, da igual cuántas miles de visitas reciba la web: la huella de carbono real seguirá siendo cercana a cero.  
2. **Uso de CDN y Caché:** Guarda copias estáticas de la web en servidores distribuidos geográficamente. Así, cuando un usuario entre a mirar la carta, la web se servirá desde el nodo más cercano a su casa sin necesidad de "despertar" ni poner a trabajar al servidor principal, ahorrando ciclos de computación en la red.
