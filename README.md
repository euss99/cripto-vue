# Convertidor de Cripto a Moneda

Esta es una aplicación que te permite convertir criptomonedas a tu moneda local utilizando la API de CryptoCompare. Podrás obtener rápidamente la cotización actualizada y precisa de la criptomoneda deseada en tu moneda local.

## Componentes

Se crearon varios componentes para facilitar la experiencia del usuario:

- **Alerta**: El componente `Alerta` se utiliza para mostrar mensajes de validación del formulario. Si hay algún error al seleccionar la criptomoneda o la moneda, este componente mostrará una alerta para informar al usuario sobre el problema.

- **Cotizacion**: El componente `Cotizacion` es responsable de renderizar la respuesta de la API de conversión de cripto a moneda. Aquí se muestra la cotización actualizada y la información relacionada con la conversión.

- **Formulario**: El componente `Formulario` permite a los usuarios elegir la criptomoneda que desean convertir y la moneda en la que realizarán la conversión. Al enviar el formulario, se realizará la solicitud a la API para obtener la cotización.

- **Spinner**: El componente `Spinner` es una animación de carga (loading) que se muestra mientras se espera la respuesta de la API. Brinda una experiencia visual agradable y muestra que la aplicación está trabajando para obtener los datos.

## Composables

Se ha utilizado el composable `useCripto` para contener toda la lógica de la petición a la API de CryptoCompare. Este composable maneja la solicitud HTTP y el procesamiento de la respuesta para obtener la cotización actualizada.

## Funcionalidades y Conceptos Reforzados

- **State**: Hemos utilizado el estado del componente para almacenar la información relevante, como las criptomonedas seleccionadas y la cotización obtenida.

- **Emits**: Para comunicar datos entre componentes, se han utilizado emisiones de eventos personalizados. Por ejemplo, cuando el formulario se envía con la selección de criptomoneda y moneda, se emite un evento para que el composable `useCripto` realice la solicitud a la API.

- **v-model**: Para mejorar la interactividad, hemos empleado la directiva `v-model` para enlazar los datos ingresados por el usuario en el formulario con el estado del componente.

- **Conexión a la API**: Hemos integrado la API de CryptoCompare para obtener la cotización en tiempo real de las criptomonedas y realizar la conversión.

- **Composables**: Hemos utilizado el composable `useCripto` para encapsular y reutilizar la lógica relacionada con la petición a la API y el procesamiento de la respuesta.

- **Computed**: Hemos utilizado computed properties para calcular y derivar datos en base a la información almacenada en el estado del componente.

## Instalación y Uso

Para utilizar CryptoConverter en tu entorno local, sigue estos pasos:

1. Clona este repositorio: `git clone https://github.com/euss99/cripto-vue.git`
2. Navega a la carpeta del proyecto: `cd cripto-vue`
3. Instala las dependencias: `npm install`
4. Inicia el servidor de desarrollo: `npm run serve`
5. Abre tu navegador y visita: `http://localhost:5173`

¡Listo! Ahora puedes utilizar la app para realizar conversiones de criptomonedas a tu moneda local de manera rápida y sencilla.
