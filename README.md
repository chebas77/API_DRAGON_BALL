# API DRAGON BALL

Este proyecto es una aplicación React que consume la API pública de Dragon Ball para mostrar información sobre personajes, específicamente aquellos que son de la raza Saiyan y tienen la afiliación Z fighter.

## Funcionalidades principales

- **Visualización de personajes:**
  - La aplicación muestra una lista de personajes Saiyan afiliados a los Z fighters.
  - Navegación entre la página principal y la lista de tarjetas de personajes.
- **Componentes principales:**
  - `Header`: Encabezado de la aplicación.
  - `Footer`: Pie de página.
  - `Home`: Página de inicio.
  - `Cardlist`: Muestra las tarjetas de los personajes obtenidos de la API.

## Uso de la API

- **API utilizada:** [https://dragonball-api.com/api/characters](https://dragonball-api.com/api/characters)
- **Tipo de API:** Pública (no requiere autenticación ni clave de acceso).
- **Método de acceso:** `GET`
- **Parámetros utilizados:**
  - `race=Saiyan`
  - `affiliation=Z fighter`
- **Ejemplo de endpoint:**
  ```
  https://dragonball-api.com/api/characters?race=Saiyan&affiliation=Z%20fighter
  ```

## Método de obtención de datos

La aplicación utiliza el método `fetch` de JavaScript dentro de un `useEffect` para obtener los datos de la API al cargar la aplicación:

```js
useEffect(() => {
  const fetchData = async () => {
    try {
      const response = await fetch('https://dragonball-api.com/api/characters?race=Saiyan&affiliation=Z%20fighter');
      if (!response.ok) {
        throw new Error('Network response was not ok');
      }
      const data = await response.json();
      setCharacters(data.results || data);
    } catch (error) {
      console.error('Error fetching data:', error);
    }
  };
  fetchData();
}, []);
```

## Instalación y uso

1. Clona el repositorio.
2. Instala las dependencias con `npm install`.
3. Inicia la aplicación con `npm run dev`.

---

