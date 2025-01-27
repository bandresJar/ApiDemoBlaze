# Conclusiones del ejercicio en DemoBlaze API

## Hallazgos:
1. **Estatus de los servicios**: Los endpoints de signup y login en DemoBlaze funcionan correctamente al enviar las peticiones POST con los datos requeridos en formato JSON. Todas las pruebas pasaron correctamente, tanto para la creación de nuevos usuarios como para los inicios de sesión.

2. **Control de errores**: La API devuelve mensajes de error claros en caso de errores, como cuando se intenta registrar un usuario ya existente o cuando se utiliza una combinación incorrecta de nombre de usuario y contraseña en el login.

3. **Validación de usuarios existentes**: El sistema permite validar correctamente cuando un usuario ya está registrado, lo que indica que el manejo de duplicados está bien implementado.

4. **Mensajes de error**: Los mensajes de error están bien definidos, como "This user already exist." o "User does not exist.", lo cual facilita la identificación de los problemas desde el punto de vista del cliente.

5. **Códigos de estado HTTP**: Sin embargo, es importante notar que la API responde con un código de estado `200` (éxito) incluso en situaciones donde se esperan errores como credenciales incorrectas o usuario inexistente. Normalmente, en estos casos se esperaría un código `4xx` (errores de cliente). Esto es algo que se debe tener en cuenta para mejorar la robustez del API.

## Conclusiones generales:
- Las pruebas han demostrado que los servicios básicos de registro y autenticación en la API de DemoBlaze funcionan según lo esperado.
- La API responde con códigos de estado `200` incluso en escenarios de error, lo cual podría mejorarse para alinear mejor la semántica HTTP con las respuestas esperadas.
- Karate resulta ser una herramienta eficiente para pruebas automatizadas en servicios REST, permitiendo manejar tanto casos exitosos como fallos en la API con facilidad.
- Se crearon las clases y feature Login y SignUp por separado para darle mejor mantenimiento el las distintas APIs.
- La clase TestSuite permite generar las pruebas en un orden en específico
