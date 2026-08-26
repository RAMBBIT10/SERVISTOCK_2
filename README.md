# ServiStack — Sistema de Gestión de Inventario para Servingeniería

## ¿Qué es este proyecto?

Servingeniería es una empresa dedicada al mantenimiento y montaje de plantas de tratamiento de agua. Hasta ahora, todo el control de su inventario de materiales se ha llevado de forma manual en hojas de Excel, a cargo de una sola persona en la bodega: Diana Marcela González Posada. Esto ha generado descuadres, pérdidas de material y demoras, porque nadie más puede saber con certeza qué hay disponible sin depender de esa persona o de un archivo que se puede perder o desactualizar.

ServiStack es el sistema que resuelve ese problema: una aplicación web y móvil, disponible en la nube, que permite a cualquier empleado consultar el stock en tiempo real, gestionar pedidos, entradas y salidas de material, y asociar ese material a los proyectos de mantenimiento o montaje donde se usa. Todo esto reemplazando el Excel manual por una fuente de información confiable y compartida.

---

## Objetivo del sistema

Permitir a los empleados de Servingeniería consultar el stock de materiales en tiempo real, gestionar pedidos, entradas y salidas de productos, y administrar los proyectos de mantenimiento y montaje, con el fin de reducir los descuadres, pérdidas monetarias y demoras generados por el control manual actual.

### Objetivos específicos

- Registrar, categorizar y consultar productos por nombre, código QR o código de barras.
- Agilizar la gestión de pedidos a proveedores y su recepción.
- Registrar salidas de productos asociadas a proyectos específicos, con trazabilidad de cantidades.
- Dar visibilidad en tiempo real de la disponibilidad de cada producto, sin depender de una sola persona ni de un archivo de Excel.
- Generar alertas automáticas cuando el stock de un producto esté por debajo del mínimo establecido.
- Consultar el historial de pedidos, entradas, salidas y proyectos realizados.

---

## Alcance

### Incluye

- Registro y categorización de productos identificados por código QR o código de barras.
- Gestión de pedidos a proveedores y su recepción mediante entradas de mercancía.
- Registro de salidas de productos asociadas a proyectos específicos.
- Consulta en tiempo real de disponibilidad de productos.
- Notificaciones automáticas de stock bajo y de eventos de pedidos.
- Historial de movimientos: pedidos, entradas, salidas y proyectos.
- Exportación de información a Excel.
- Disponibilidad como aplicación web y aplicación móvil, en la nube.

### No incluye

- Manejo de precios, facturación electrónica o reportes contables para la DIAN.
- Gestión de nómina, ventas o compras a clientes finales.
- Tratamiento especial para productos regulados.
- Niveles de permisos más allá de la distinción entre empleado y administrador. Solo el administrador puede crear y eliminar cuentas de empleado.
- Inactivación o baja de productos, empleados o categorías registradas.

---

## Usuarios del sistema

En el sistema solo existen **dos roles de acceso**:

| Rol del sistema | Qué puede hacer |
|-----------------|-----------------|
| Empleado | Todo lo operativo: productos, pedidos, entradas, salidas, proyectos, historial, notificaciones y exportación. |
| Administrador | Exactamente lo mismo que el empleado, más crear y eliminar cuentas de empleado. |

### Tipos de personas que usan el sistema

Aunque solo hay dos roles de acceso, en la práctica el sistema lo van a usar diferentes tipos de personas dentro de Servingeniería. Todos entran con el rol de **Empleado**, excepto quien tenga el rol de **Administrador**.

| Tipo de persona | Cómo entra al sistema | Qué hace principalmente |
|-----------------|-----------------------|-------------------------|
| Empleado de inventario | Como Empleado | Maneja productos, pedidos, entradas y consulta de stock en bodega. |
| Empleado de campo | Como Empleado | Registra salidas, trabaja con proyectos y escanea códigos QR o de barras desde el celular. |
| Empleado contable | Como Empleado | Consulta historiales y exporta información a Excel. |
| Empleado administrador del sistema | Como Administrador | Hace todo lo anterior y además crea o elimina cuentas de empleado. |

Esto se definió así para que todos tengan la misma información y no dependan de una sola persona o de un archivo de Excel.

---

## Requisitos funcionales

### Gestión de empleados

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-01 | Un administrador debe poder crear una cuenta de empleado, indicando nombre, usuario y contraseña de acceso. | Media |
| RU-71 | Un administrador debe poder eliminar la cuenta de un empleado. | Media |
| RU-02 | El sistema debe permitir consultar la información de un empleado específico. | Baja |
| RU-03 | El sistema debe permitir consultar el listado completo de empleados registrados. | Media |
| RU-04 | El sistema debe permitir editar la información de un empleado: nombre y usuario. | Baja |

### Gestión de productos

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-05 | El empleado debe poder registrar un nuevo producto especificando nombre, categoría, código QR o código de barras, y cantidad mínima de stock. | Alta |
| RU-06 | El empleado debe poder consultar el detalle y la disponibilidad actual de un producto específico en tiempo real. | Alta |
| RU-07 | El empleado debe poder consultar el detalle de un producto escaneando su código QR o de barras con la cámara del dispositivo. | Alta |
| RU-08 | El empleado debe poder consultar el listado completo de productos. | Media |
| RU-09 | El empleado debe poder consultar productos filtrando por nombre. | Media |
| RU-10 | El empleado debe poder consultar productos filtrando por categoría. | Media |
| RU-11 | El empleado debe poder editar la información de un producto ya registrado: nombre, categoría, código QR o de barras, cantidad mínima de stock. | Alta |

### Gestión de categorías de producto

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-12 | El sistema debe permitir crear una categoría de producto, indicando su nombre. | Media |
| RU-13 | El sistema debe permitir consultar el listado completo de categorías de producto. | Media |
| RU-14 | El sistema debe permitir editar el nombre de una categoría de producto ya existente. | Baja |

### Gestión de pedidos

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-15 | El empleado debe poder crear un pedido, indicando el proveedor al cual se le solicita la mercancía. | Alta |
| RU-16 | El empleado debe poder consultar el detalle de un pedido específico. | Alta |
| RU-17 | El empleado debe poder consultar el listado completo de pedidos. | Alta |
| RU-18 | El empleado debe poder consultar pedidos filtrando por estado. | Media |
| RU-19 | El empleado debe poder editar un pedido mientras no tenga entradas asociadas. | Media |
| RU-20 | El empleado debe poder cancelar un pedido. | Media |

### Gestión de entradas

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-21 | El empleado debe poder registrar una entrada de mercancía asociada a un pedido existente, indicando los productos recibidos y la cantidad de cada uno. | Alta |
| RU-22 | El empleado debe poder registrar una entrada de mercancía que no proviene de un pedido formal, indicando el tipo de entrada y los productos involucrados. | Media |
| RU-23 | El empleado debe poder consultar el detalle de una entrada específica, incluyendo el estado de cada producto dentro de ella. | Alta |
| RU-24 | El empleado debe poder consultar el listado completo de entradas. | Alta |
| RU-25 | El empleado debe poder consultar entradas filtrando por estado. | Media |
| RU-26 | El empleado debe poder editar los datos de una entrada o de una línea de producto dentro de ella, mientras no esté marcada como completada. | Media |
| RU-27 | El empleado debe poder marcar como completada la línea de un producto dentro de una entrada, una vez confirmada su llegada física. | Alta |
| RU-28 | El empleado que registra la entrada de mercancía puede ser distinto del empleado que generó el pedido asociado. | Media |

### Gestión de proyectos

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-29 | El empleado debe poder crear un proyecto de mantenimiento o montaje, indicando su nombre y descripción. | Alta |
| RU-30 | El empleado debe poder asignar uno o varios empleados a un proyecto, indicando su tipo de participación. | Media |
| RU-31 | El empleado debe poder consultar el detalle de un proyecto específico, incluyendo los empleados asignados y las salidas registradas. | Alta |
| RU-32 | El empleado debe poder consultar el listado completo de proyectos. | Media |
| RU-33 | El empleado debe poder consultar proyectos filtrando por estado. | Media |
| RU-65 | El empleado debe poder consultar proyectos filtrando por nombre. | Media |
| RU-34 | El empleado debe poder editar los datos de un proyecto mientras esté en curso. | Media |
| RU-35 | El empleado debe poder finalizar o cancelar un proyecto. | Media |
| RU-36 | El empleado debe poder reasignar o retirar a un empleado de un proyecto. | Baja |

### Gestión de salidas

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-37 | El empleado debe poder registrar la salida de productos asociada a un proyecto específico, indicando el producto y la cantidad de cada uno. | Alta |
| RU-69 | El empleado debe poder agregar un producto a una salida escaneando su código QR o código de barras con la cámara del dispositivo. | Alta |
| RU-70 | El empleado debe poder agregar un producto a una salida buscándolo por nombre. | Alta |
| RU-38 | El empleado debe poder consultar con certeza cuántos productos y en qué cantidad se han usado en un proyecto específico. | Alta |
| RU-39 | El empleado debe poder consultar el detalle de una salida específica, incluyendo el estado de cada producto dentro de ella. | Media |
| RU-40 | El empleado debe poder consultar el listado completo de salidas. | Media |
| RU-41 | El empleado debe poder consultar salidas filtrando por estado. | Media |
| RU-42 | El empleado debe poder editar los datos de una salida o de una línea de producto dentro de ella, mientras no esté marcada como completada. | Media |
| RU-43 | El empleado debe poder cancelar una salida. | Baja |

### Módulo de historial

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-44 | El empleado debe poder consultar el historial de pedidos realizados, incluyendo cada cambio de estado registrado. | Media |
| RU-66 | El empleado debe poder consultar el historial de pedidos dentro de un rango de fechas específico. | Media |
| RU-45 | El empleado debe poder consultar el historial de entradas realizadas, incluyendo el detalle de los productos recibidos y cada cambio de estado. | Media |
| RU-67 | El empleado debe poder consultar el historial de entradas dentro de un rango de fechas específico. | Media |
| RU-46 | El empleado debe poder consultar el historial de salidas realizadas, incluyendo el detalle de los productos entregados y cada cambio de estado. | Media |
| RU-68 | El empleado debe poder consultar el historial de salidas dentro de un rango de fechas específico. | Media |
| RU-47 | El empleado debe poder consultar el historial de proyectos, incluyendo cada cambio de estado. | Baja |

### Módulo de notificaciones

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-48 | El sistema debe notificar automáticamente al empleado cuando el stock de un producto caiga por debajo del mínimo establecido. | Media |
| RU-49 | El sistema debe notificar al empleado responsable cuando se cree un nuevo pedido. | Baja |
| RU-50 | El sistema debe notificar al empleado responsable cuando un pedido cambie de estado. | Baja |
| RU-51 | El empleado debe poder consultar el listado de notificaciones de producto y de pedido recibidas. | Media |
| RU-52 | El empleado debe poder marcar una notificación como leída. | Media |

### Gestión de catálogos

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-53 | El sistema debe permitir crear, consultar y editar tipos de entrada. | Media |
| RU-54 | El sistema debe permitir crear, consultar y editar tipos de participación de un empleado dentro de un proyecto. | Baja |
| RU-55 | El sistema debe permitir crear, consultar y editar tipos de notificación de producto y de pedido. | Baja |

### Acceso al sistema

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-56 | El empleado debe poder iniciar sesión con usuario y contraseña para acceder al sistema. | Alta |

### Exportación de información a Excel

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-57 | El empleado debe poder exportar el historial de pedidos a un archivo Excel. | Media |
| RU-58 | El empleado debe poder exportar el historial de entradas, incluyendo el detalle de productos por entrada, a un archivo Excel. | Media |
| RU-59 | El empleado debe poder exportar el historial de salidas, incluyendo el detalle de productos por salida, a un archivo Excel. | Media |
| RU-60 | El empleado debe poder exportar el listado de proyectos junto con los productos y cantidades utilizadas en cada uno, a un archivo Excel. | Media |
| RU-61 | El empleado debe poder exportar el inventario actual de productos a un archivo Excel. | Media |

### Funcionalidades de valor diferencial

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RU-62 | El empleado debe poder consultar, al ingresar al sistema, un resumen general con los productos en stock bajo y los proyectos actualmente en curso. | Media |
| RU-63 | El empleado debe poder escanear el código QR o de barras de un producto para agregarlo directamente a una entrada en curso. | Alta |
| RU-64 | El empleado debe poder consultar el listado de proyectos en los que participa un empleado específico. | Baja |

---

## Requisitos no funcionales

| Código | Descripción | Prioridad |
|--------|-------------|-----------|
| RNU-01 | El sistema debe estar disponible en la nube, tanto como aplicación web como aplicación móvil. | Alta |
| RNU-02 | Las consultas de productos, pedidos, entradas y salidas deben responder en un tiempo aproximado menor a 1.5 segundos. | Alta |
| RNU-03 | El sistema debe permitir usar la cámara del dispositivo móvil para leer códigos QR o de barras al registrar productos, entradas o salidas. | Alta |
| RNU-04 | El sistema debe ser fácil de usar, requiriendo una capacitación muy básica para empleados con conocimiento tecnológico limitado. | Alta |
| RNU-05 | El sistema no requiere niveles de seguridad avanzados ni manejo de información de pago, ya que solo será usado internamente por los empleados. | Media |
| RNU-06 | El sistema debe restringir la creación y eliminación de cuentas de empleado exclusivamente al administrador. El resto de las funcionalidades estarán disponibles por igual para todos los usuarios. | Alta |

---

## Requisitos de información

| Código | Entidad | Datos que maneja |
|--------|---------|------------------|
| RI01 | Empleado | Nombre, usuario, contraseña. |
| RI02 | Producto | Nombre, categoría, código QR o de barras, cantidad mínima de stock, stock actual. |
| RI03 | Categoría de producto | Nombre. |
| RI04 | Pedido | Proveedor, estado. |
| RI05 | Entrada | Pedido asociado si aplica, tipo de entrada, productos y cantidades, estado general y por línea de producto. |
| RI06 | Proyecto | Nombre, descripción, empleados asignados con su tipo de participación, estado, salidas asociadas. |
| RI07 | Salida | Proyecto asociado, productos y cantidades, estado general y por línea de producto. |
| RI08 | Notificación | Tipo, estado de lectura. |
| RI09 | Historial | Registro de cambios de estado de pedidos, entradas, salidas y proyectos. |
| RI10 | Catálogos | Tipo de entrada, tipo de participación en proyecto, tipo de notificación. |

---

## Atributos de calidad priorizados

Después de caracterizar escenarios y votar con los roles involucrados, estos son los atributos que más pesan:

| Prioridad | Atributo | Puntaje total | Por qué importa |
|-----------|----------|---------------|-----------------|
| 1 | Rendimiento | 28 | El stock tiene que responder rápido. Si alguien pregunta si hay material disponible, no puede esperar. |
| 2 | Disponibilidad | 22 | Si el sistema se cae seguido, vuelven al Excel. Se busca alta disponibilidad en horario laboral. |
| 3 | Seguridad | 18 | Login con usuario y contraseña, contraseñas cifradas, y solo el administrador crea o elimina cuentas. |
| 3 | Integridad | 18 | El stock debe ser exacto. No puede haber descuadres por salidas concurrentes o estados inconsistentes. |
| 3 | Interoperabilidad | 18 | Exportar a Excel y usar la cámara del dispositivo son partes clave del flujo diario. |
| 6 | Portabilidad | 17 | Tiene que funcionar bien en web y en móvil. |
| 7 | Usabilidad | 15 | Empleados de bodega y de campo con poco conocimiento técnico. La interfaz debe ser clara. |
| 8 | Modificabilidad | 8 | Hay reglas de negocio aún pendientes de definir. El sistema va a seguir cambiando. |

### Tabla de escenarios más votados

| Código | Atributo | Escenario | Inventario | Admin | Campo | Contable | Total |
|--------|----------|-----------|------------|-------|-------|----------|-------|
| ESC-CAL-INTG-0007 | Integridad | Salida válida asociada a proyecto | 2 | 0 | 2 | 0 | 4 |
| ESC-CAL-INTG-0008 | Integridad | Salida rechazada por stock insuficiente | 2 | 0 | 2 | 0 | 4 |
| ESC-CAL-REN-0005 | Rendimiento | Registro rápido de salida | 2 | 0 | 2 | 0 | 4 |
| ESC-CAL-DIS-0001 | Disponibilidad | Disponibilidad del sistema en horario laboral | 0 | 0 | 3 | 0 | 3 |
| ESC-CAL-INT-0002 | Interoperabilidad | Exportación de historial de pedidos con datos | 0 | 0 | 0 | 3 | 3 |
| ESC-CAL-INT-0005 | Interoperabilidad | Exportación de proyectos con datos | 0 | 0 | 0 | 3 | 3 |
| ESC-CAL-INT-0006 | Interoperabilidad | Exportación de inventario actual con datos | 0 | 0 | 0 | 3 | 3 |
| ESC-CAL-INT-0017 | Interoperabilidad | Consulta de producto mediante código válido | 0 | 0 | 3 | 0 | 3 |
| ESC-CAL-INT-0020 | Interoperabilidad | Agregar producto a salida por escaneo | 1 | 0 | 2 | 0 | 3 |
| ESC-CAL-INTG-0003 | Integridad | Consulta de stock actualizado | 3 | 0 | 0 | 0 | 3 |
| ESC-CAL-POR-0001 | Portabilidad | Acceso al sistema desde web y móvil | 0 | 0 | 3 | 0 | 3 |
| ESC-CAL-REN-0001 | Rendimiento | Consulta rápida de stock | 3 | 0 | 0 | 0 | 3 |
| ESC-CAL-SEG-0007 | Seguridad | Administrador crea una cuenta de empleado | 0 | 3 | 0 | 0 | 3 |
| ESC-CAL-SEG-0011 | Seguridad | Intento de modificación libre de TipoEmpleado | 0 | 3 | 0 | 0 | 3 |
| ESC-CAL-INT-0003 | Interoperabilidad | Exportación de historial de entradas con datos | 0 | 0 | 0 | 2 | 2 |

**Lo que más importa según los votos:**
- Que las salidas se asocien bien a los proyectos y no se pueda sacar más stock del disponible.
- Que el registro de salidas y la consulta de stock sean rápidos.
- Que el sistema esté disponible en horario laboral y funcione tanto en web como en móvil.
- Que se pueda exportar a Excel: pedidos, proyectos e inventario.
- Que se pueda escanear códigos QR y de barras.
- Que solo el administrador pueda crear cuentas y que no se pueda modificar libremente el tipo de empleado.

---

## Restricciones de negocio

| Tipo | Restricción de negocio | Justificación | Plan de acción |
|------|------------------------|---------------|----------------|
| Humano | El equipo de desarrollo es pequeño y es un trabajo académico. Nadie queda dando soporte después de la entrega. | Si se diseña algo muy complejo, después no va a haber quién lo mantenga. | Se opta por una arquitectura simple y bien documentada, dividiendo el trabajo por módulos según la disponibilidad de cada integrante. |
| Humano | El equipo de negocio solo cuenta con una hora diaria para trabajar en el proyecto. | Hay que aprovechar ese tiempo limitado y priorizar lo más urgente cada semana. | Distribuir las tareas según esa hora disponible al día y priorizar semanalmente lo más urgente. |
| Tiempo | El proyecto tiene un tiempo límite definido por la universidad. | Es un proyecto académico con fechas establecidas por la institución. | Dividir el proyecto en etapas claras y cumplir con las fechas definidas. |
| Presupuesto | No hay presupuesto definido para hosting ni servicios en la nube. | Elegir mal el servicio de hospedaje podría comprometer la disponibilidad del sistema. | Usar servicios en la nube con planes gratuitos como Render, Railway o Firebase, suficientes para esta fase. |
| Legal | El sistema no debe incumplir la normativa de facturación electrónica de la DIAN. | Si el sistema tocara precios o facturación sin cumplir esa normativa, expondría a Servingeniería a sanciones que hoy no le corresponden. | Se delimita el alcance para que no gestione precios ni facturación. Eso se deja en el área contable de la empresa. |
| Organizacional | Servingeniería nunca ha usado un sistema digital para este proceso. Siempre ha sido con Excel o de forma manual. | Un cambio muy brusco puede dificultar que el equipo lo adopte. | Se diseña la primera versión imitando la lógica y el lenguaje que ya usan en su Excel, para que la transición se sienta natural. |
| Proceso | Algunas reglas de negocio aún se están definiendo y el cliente indica que se debe ir implementando lo que se vaya identificando. | Hay decisiones pendientes sobre cancelaciones, estados y permisos. | Ir documentando e implementando cada necesidad a medida que el cliente la vaya confirmando. |
| Tecnológico | El equipo no tiene experiencia previa construyendo apps con escaneo de cámara. | Es una parte clave del sistema y podría tomar más tiempo del esperado. | Se desarrolla un prototipo del escaneo QR desde las primeras semanas, para resolver esa curva de aprendizaje antes de que afecte el cronograma. |

---

## Restricciones técnicas

| Tipo | Categoría | Restricción técnica | Justificación |
|------|-----------|---------------------|---------------|
| Impuesta por el cliente | Tecnología base | La aplicación debe ser accesible tanto desde un navegador web como desde un dispositivo móvil. | Fue solicitado explícitamente por la encargada de bodega, ya que el personal opera tanto desde la bodega como desde los sitios de los proyectos. |
| Impuesta por el cliente | Tecnología base | La aplicación debe permitir usar la cámara del dispositivo para leer códigos QR y de barras. | Se identificó como una necesidad puntual para agilizar el registro y la búsqueda de productos sin tener que escribir cada dato manualmente. |
| Impuesta por el cliente | Rendimiento | La consulta del stock de un producto debe responder en un tiempo muy corto, cercano al tiempo real. | La stakeholder fue explícita en que no quería depender de preguntar a otra persona ni de revisar un archivo desactualizado. |
| Propia del proyecto | Reactividad | El sistema debe apoyarse en principios de reactividad, propagando los cambios de forma automática para que la información se mantenga al día sin que el empleado deba refrescar. | Es la forma en que el equipo decidió resolver la necesidad de no depender de una actualización manual del stock, y permite que el sistema responda bien aunque varios empleados generen cambios al mismo tiempo. |
| Propia del proyecto | Capacidad concurrente | El sistema debe permitir que varios empleados registren movimientos al mismo tiempo sin generar inconsistencias en el stock. | Es una condición necesaria para que el sistema sea confiable en un entorno con varios usuarios simultáneos, tanto en bodega como en distintos proyectos. |
| Propia del proyecto | Disponibilidad | El sistema debe poder funcionar con alta disponibilidad en horario laboral. | El usuario indicó que la disponibilidad prioritaria es en horario laboral. |
| Propia del proyecto | Prácticas de diseño | El diseño y desarrollo del software debe seguir los principios SOLID. | Para lograr un software más mantenible y fácil de ajustar, considerando que el sistema seguirá evolucionando después de la primera entrega. |
| Propia del proyecto | Prácticas de diseño | El sistema debe diseñarse con bajo acoplamiento entre sus módulos: productos, pedidos, entradas, salidas, proyectos y notificaciones. | Para que un cambio en un módulo, como notificaciones, no afecte el funcionamiento de los demás. |
| Propia del proyecto | Prácticas de diseño | El sistema debe diseñarse de forma que los catálogos de tipos y de estados puedan ampliarse sin modificar el código existente. | Coincide con la decisión de que estos catálogos sean editables sin afectar la lógica de los módulos que los usan. |
| Propia del proyecto | Patrones de diseño | Propender por el uso de patrones como DRY y KISS. | Ayudan a evitar la duplicación de código y a mantener el sistema simple, reduciendo el riesgo de errores al hacer cambios. |
| Propia del proyecto | Código limpio | Propender por prácticas de código limpio, evitando código desordenado o difícil de entender. | Facilita que cualquier persona del equipo entienda y modifique el sistema, considerando que el equipo de desarrollo es pequeño. |
| Propia del proyecto | Organización | El sistema debe construirse con una organización clara entre sus distintas capas o módulos. | Facilita el mantenimiento y permite que el sistema crezca sin volverse desordenado. |
| Propia del proyecto | Metodología | El desarrollo debe llevarse a cabo con una metodología ágil que permita ajustes progresivos sobre lo ya construido. | Varias decisiones de diseño, como las reglas de estados y de permisos, se han ido ajustando durante el proceso y es previsible que sigan cambiando. |
| Propia del proyecto | Prácticas DevOps | Propender por prácticas que permitan automatizar las pruebas y los despliegues del sistema. | Ayuda a reducir errores manuales y a que el equipo pueda entregar cambios de forma más rápida y confiable. |

---

## Supuestos y restricciones adicionales

### Supuestos
- Servingeniería opera desde una sola bodega física de materiales.
- El área de contabilidad seguirá gestionando precios y facturación de forma independiente al sistema.

### Restricciones
- El sistema no incluye precios, facturación electrónica ni reportes para la DIAN.
- No se contemplan productos que requieran tratamiento regulatorio especial.
- No se implementan más niveles de permisos que la distinción entre empleado y administrador.
- El catálogo de estados no es editable desde la operación diaria, porque está ligado al avance automático de pedidos, entradas, salidas y proyectos.
- El producto, el empleado, las categorías y los catálogos no manejan un estado de activo o inactivo en esta versión. Solo se pueden crear, consultar y editar.

### Pendientes de confirmar
- Qué ocurre cuando se cancela un pedido o proyecto que ya tiene entradas o salidas parcialmente completadas.
- Si el pedido debe registrar los productos y cantidades solicitados desde el momento de su creación, o si es suficiente registrarlos al momento de la entrada.
- Si eliminar por completo la cuenta de un empleado puede afectar el historial de pedidos, entradas y salidas que ese empleado haya registrado.
- Nivel de conocimiento tecnológico real de los empleados de campo.
- Qué funcionalidades quedan fuera de la primera fase en caso de restricción de presupuesto o tiempo.
- Catálogo de estados: fijo, no editable por el usuario
