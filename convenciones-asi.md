# Convenciones de cátedra — ASI (auditoría para Actividad créditos 1, Cookies Club)

> Este archivo es la vara de auditoría del Paso 6. Cada regla cita el texto exacto de donde sale.
> Donde no hay cita, se marca explícitamente como **sin fuente de cátedra provista** — no se completa con conocimiento general.

## 0. Alcance de esta actividad

La consigna de "Cookies Club" pide: (1) objetivo del sistema, (2) requerimientos funcionales globales, (3) Modelo de Objetos del Dominio (diagrama de clases). **No pide modelado de procesos de negocio (BPMN)**, por lo tanto las convenciones típicas de esa cátedra sobre nomenclatura de procesos/actividades en infinitivo, niveles de modelado BPMN, ficha de proceso, proveedores internos o cliente externo en BPMN **no aplican a esta entrega** y no se documentan acá con contenido inventado. Si en algún momento aparecen en el material que compartas, se agregan.

## 1. Nomenclatura de clases, atributos y métodos

**Sin regla formal explícita en el material provisto.** Lo que hay es un patrón *observado* (no enunciado como regla) en los ejemplos del apunte "Patrones y Software UML 2.0" (Ing. Judith Meles):

- Nombres de clase: PascalCase, sustantivo singular. Ejemplos textuales del apunte: *"Venta"*, *"DetalleDeVenta"*, *"PuntoDeVenta"*, *"EspecificacionDeProducto"*, *"PagoTarjeta"*, *"PagoCheque"*, *"TarjetaCredito"*, *"AgenteAlmacenamientoPersistente"*, *"Contenedor"*, *"Contenido"*, *"Plan"*, *"Paso"*, *"EjecucionPlan"*, *"EjecucionPaso"*, *"VersionPlan"*.
- Nombres de atributo: minúscula inicial, camelCase. Ejemplos textuales: *"numero"*, *"nombre"*, *"capacidad"*, *"sobreMi"*, *"fecha"*, *"hora"*, *"estado"*, *"cantidad"*, *"descripcion"*, *"duracionEstimada"*, *"requerimientoRecursos"*, *"estadoOperacional"*, *"rangoOperativo"*.
- Nombres de método: minúscula inicial, camelCase, con paréntesis. Ejemplos textuales: *"cuantos()"*, *"cuanto()"*, *"calcularSobreContenido()"*, *"clasificarContenido()"*, *"calcularParaMi()"*, *"crear()"*, *"autorizar()"*, *"calcularDuracionEstimada()"*, *"reunirRqsRecursos()"*, *"activar()"*, *"desactivar()"*.

**Decisión de resolución**: en el Paso 3 voy a seguir este patrón observado (PascalCase para clases, camelCase para atributos/métodos) porque es lo único que hay como referencia visual de la cátedra, pero lo marco como **convención inferida de ejemplos, no regla citada explícitamente** — si tu docente exige otra convención, avisame antes de la entrega.

## 2. Niveles de modelado y qué está prohibido en cada uno

**No aplica / sin material.** Esta actividad no pide modelado de procesos (BPMN, mapa de procesos). No hay contenido de cátedra sobre niveles de modelado en los archivos que compartiste hasta ahora relevante a un diagrama de clases.

## 3. Proveedores internos en la ficha de proceso

**No aplica.** Esta actividad no incluye ficha de proceso.

## 4. Modelado del cliente externo

**No aplica.** Esta actividad no incluye modelado BPMN de cliente externo.

## 5. Campos obligatorios del diagrama de clases (equivalente a "campos obligatorios de la ficha de proceso" para esta actividad)

Tomado directamente de la consigna, textual: *"Definir clases (con sus atributos y métodos), relaciones, navegabilidad y multiplicidad."*

Por lo tanto, cada clase del Modelo de Objetos del Dominio debe tener obligatoriamente:
- Nombre de clase.
- Atributos (con tipo, según buena práctica de UML — no está explicitado el formato exacto de tipo en el material, se marca como supuesto en Paso 3).
- Métodos.
- Relaciones con las demás clases.
- Navegabilidad de cada relación.
- Multiplicidad en cada extremo de cada relación.

**Notación exacta de multiplicidad/navegabilidad**: en los diagramas del apunte de patrones se ve la notación `1` y `1..*` en los extremos de las asociaciones (ej. Contenedor 1 — 1..* Contenido), pero el apunte no explica en texto qué significa cada símbolo ni lista el catálogo completo de multiplicidades (0..1, 0..*, 1, 1..*, etc.) — es notación UML estándar que se ve en los diagramas de ejemplo, no una regla redactada. **Sin regla textual explícita en el material provisto** más allá de esos ejemplos gráficos.

## 6. Requerimientos funcionales y objetivo del sistema

Del capítulo de Davis ("La Especificación de Requerimientos de Software"):

- *"Los requerimientos de comportamiento define que hace el sistema. Ellos describen todas las entradas y salidas desde y hacia el sistema así como la información concerniente a como las entradas y salidas se interrelacionan."* → esto es lo que la consigna llama "requerimientos funcionales".
- *"Los requerimientos no de comportamiento definen los atributos del sistema como él desarrolla su trabajo [...] eficiencia, confiabilidad, seguridad, mantenibilidad, portabilidad..."* → requerimientos no funcionales (la consigna de Cookies Club no los pide, solo pide "funcionales globales").
- Atributos de un buen SRS/requerimiento, citados textualmente: *"Correcto"*, *"No Ambigua"*, *"Completa"*, *"Verificable"*, *"Consistente"*, *"Entendible por no especialistas en computadores"*, *"Modificable"*, *"Rastreable"*, *"Anotado"*.
- Un requerimiento es no ambiguo si *"tiene una única interpretación"*; es verificable si *"existe algún proceso costo efectivo en el cual una persona o máquina puede chequear que el software [...] satisface ese requerimiento"*.

**No hay, en el material provisto, una plantilla específica de la cátedra** para cómo enumerar/formatear los "requerimientos funcionales globales" (¿por actor? ¿con código RF-01? ¿en tabla?) ni una definición cátedra-específica de "objetivo del sistema de información". Uso los criterios generales de Davis (correcto, no ambiguo, verificable) como estándar de calidad al redactar, y marco el formato de presentación (lista numerada RF-01, RF-02, ...) como **decisión propia, no dictada por una fuente citada** — te la muestro en el Paso 3 para que la confirmes.

## 7. Patrones de dominio disponibles para justificar clases/relaciones (Coad, vía el apunte de Judith Meles)

Citados textualmente porque los voy a usar para justificar decisiones del Paso 3:

- *"Actor-Participante"*: ejemplos de Participante incluyen *"miembro"*, *"subscriptor"*.
- *"Participante-Transacción"*: ejemplos de Transacción incluyen *"registración"*, *"pago"*, *"subscripción"*.
- *"Transacción-Detalle de Transacción"*: ejemplo *"pago-detalle de pago"*.
- *"Transacción-Transacción Subsiguiente"*: ejemplo *"compra-pago"*, con la nota: *"Diseñe las transacciones en secuencia temporal (en el orden en que ocurren usualmente)."*
- *"Plan-Ejecución de Plan"*, con la nota: *"Use este pattern cuando un plan pueda ser ejecutado varias veces."*

## 8. Patrones GRASP para asignación de métodos (mismo apunte)

- Patrón Experto: *"Asignar una responsabilidad al experto en información: la clase que cuenta con la información necesaria para cumplir con la responsabilidad."*
- Patrón Creador: *"Asignar a la clase B la responsabilidad de crear una instancia de la clase A"* cuando B agrega/contiene/registra/usa específicamente a A, o tiene los datos de inicialización de A.
- Patrón Controlador: *"Asignar la responsabilidad del manejo de un mensaje de los eventos de un sistema, a una clase que represente [...] El sistema 'global' [...] La empresa u organización global [...] Algo en el mundo real que es activo [...] Un manejador artificial [...] generalmente denominado 'Manejador \<Nombre de Caso de Uso\>'"*.

## 9. Condiciones formales de entrega (de la consigna misma)

- *"Resolución INDIVIDUAL"*.
- *"FECHA DE ENTREGA Miércoles 23/09/2026. Inicio de la clase. Tolerancia: 5 minutos."*
- Carátula / formato de archivo: **pendiente** — no está en el texto de la consigna pegado. Pendiente de confirmar con "Modelo de carátula.pdf" y "Algunas consideraciones para recordar TPI 1° entrega.pdf" que mencionaste tener mencionaste tener (Paso 5).

## 10. Contradicciones detectadas (a resolver por vos, no por mí en silencio)

- La consigna pide explícitamente **métodos** en las clases del "Modelo de Objetos del Dominio" (*"Definir clases (con sus atributos y métodos)..."*). En teoría general de análisis OO, un "modelo de dominio" puro a veces se define sin operaciones (solo estructura conceptual), reservando los métodos para el "modelo de diseño". El material de cátedra provisto (apunte de patrones) sí muestra métodos en sus diagramas de "modelo de objetos del dominio" de ejemplo (ej. Contenedor con `cuantos()`, `calcularSobreContenido()`). **No hay contradicción documental** entre la consigna y el apunte citado en este punto — ambos incluyen métodos — así que no lo marco como conflicto de fuentes, solo como algo a tener presente.
