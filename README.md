# Generador de Firma para Gmail

Este proyecto es una herramienta sencilla que permite generar una firma personalizada para Gmail a partir de un formulario. El formulario recopila los datos necesarios y genera una vista previa de la firma que se puede copiar directamente y pegar en el cajón de firma de Gmail.

## Características

- **Formulario de entrada**: Permite ingresar el nombre, apellidos, puesto, teléfono, correo electrónico, dirección, código postal y ciudad.
- **Vista previa dinámica**: Muestra una previsualización en tiempo real de la firma generada.
- **Botón de copia**: Permite copiar la firma generada en formato visual con un solo clic.
- **Diseño responsivo**: El formulario y la vista previa están alineados uno al lado del otro para una mejor experiencia de usuario.

## Requisitos

- Navegador moderno que soporte JavaScript y HTML5.

## Cómo usar

1. Descarga los archivos del proyecto.
2. Abre el archivo `index.html` en cualquier navegador.
3. Llena el formulario con la información requerida:
   - **Nombre y Apellidos**
   - **Puesto**
   - **Teléfono**
   - **Email**
   - **Dirección**
   - **Código Postal** y **Ciudad**
4. Haz clic en el botón "Generar Firma" para generar la vista previa.
5. Haz clic en "Copiar Firma" para copiar la firma al portapapeles.
6. Pega la firma directamente en el campo de configuración de firma de Gmail.

## Estructura del Proyecto

```
/
|-- index.html    # Archivo principal con el código HTML, CSS y JS
```

## Funciones principales

### Generar Firma

La función `generateSignature()` toma los datos del formulario y genera un bloque de HTML que se muestra como una vista previa en el panel derecho.

```javascript
function generateSignature() {
    const name = document.getElementById('name').value;
    const job = document.getElementById('job').value;
    const phone = document.getElementById('phone').value;
    const email = document.getElementById('email').value;
    const address = document.getElementById('address').value;
    const postalCode = document.getElementById('postalCode').value;
    const city = document.getElementById('city').value;

    const signatureHTML = `...`;
    document.getElementById('signaturePreview').innerHTML = signatureHTML;
}
```

### Copiar Firma

La función `copySignature()` selecciona visualmente el contenido generado y lo copia al portapapeles utilizando el comando `document.execCommand('copy')`.

```javascript
function copySignature() {
    const signaturePreview = document.getElementById('signaturePreview');
    const range = document.createRange();
    range.selectNodeContents(signaturePreview);
    const selection = window.getSelection();
    selection.removeAllRanges();
    selection.addRange(range);

    try {
        document.execCommand('copy');
        alert('Firma copiada al portapapeles');
    } catch (err) {
        console.error('Error al copiar la firma:', err);
        alert('Hubo un error al copiar la firma');
    }

    selection.removeAllRanges();
}
```

## Personalización

- **Logo y enlace**: Puedes reemplazar el logo y el enlace en la función `generateSignature()`.
- **Colores y estilos**: Modifica las propiedades CSS en la etiqueta `<style>` dentro del archivo `index.html`.

## Vista previa

![Vista previa de la firma](https://via.placeholder.com/700x400.png?text=Generador+de+Firma+Preview)

## Créditos

Creado por Enrique para su empresa. Puedes personalizarlo según las necesidades de tu negocio.

---

**Nota:** Este proyecto está diseñado para ser utilizado localmente. No se requieren instalaciones adicionales ni configuraciones externas.
