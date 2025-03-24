# 📦 Redistribución Inteligente de Packing List con IA

Esta aplicación permite redistribuir automáticamente el contenido de un pedido (packing list) entre múltiples clientes a partir de sus requerimientos específicos, utilizando inteligencia artificial generativa.

---

## 🎯 ¿Qué problema resuelve?

En muchos entornos logísticos, un proveedor recibe un pedido grande (por ejemplo, 15 cajas con distintos talles de camisas) que luego debe ser repartido entre varios clientes, cada uno con requerimientos diferentes (distintos talles y cantidades).

Este proceso puede ser tedioso, manual y propenso a errores.

**Esta app automatiza ese proceso utilizando IA**, proponiendo la mejor manera de redistribuir las cajas y generando los documentos necesarios para la entrega.

---

## 🧠 ¿Cómo funciona?

1. El usuario carga dos archivos Excel:
   - 📄 **Packing List original**
   - 📄 **Tabla con pedidos de clientes**

2. (Opcional) Agrega:
   - Instrucciones para el formato de etiquetas
   - Observaciones adicionales (por ejemplo, máximo de unidades por caja, no dividir talles, etc.)

3. La IA (modelo **Gemini 2.0 Flash**) analiza los datos y genera:
   - 🧠 Una explicación de la estrategia utilizada
   - 📊 Una tabla detallada con la redistribución (cliente, caja nueva, caja origen, producto, talle, cantidad)
   - 🏷️ Etiquetas para cada caja nueva, listas para imprimir

4. El programa permite **descargar**:
   - Un archivo **Excel** con el detalle de redistribución
   - Un archivo **Word** con todas las etiquetas

---

## 🧱 Estructura del programa

- `app.py`: archivo principal, escrito con Streamlit
- `secrets.toml`: contiene la API KEY de Gemini (no debe subirse al repositorio)
- `requirements.txt`: contiene todas las librerías necesarias

---

## 🚀 Instalación y ejecución

### 1. Clonar el repositorio

```bash
git clone https://github.com/tu_usuario/redistribucion-ia.git
cd redistribucion-ia
```

### 2. Crear entorno virtual

```bash
python -m venv venv
```

### 3. Activar entorno virtual

- En Windows:

```bash
venv\Scripts\activate
```

- En macOS/Linux:

```bash
source venv/bin/activate
```

### 4. Instalar dependencias

```bash
pip install -r requirements.txt
```

### 5. Configurar API Key

Crear un archivo llamado `secrets.toml` con el siguiente contenido:

```toml
[gemini]
api_key = "TU_API_KEY_AQUI"
```

### 6. Ejecutar la app

```bash
streamlit run app.py
```

---

## 📦 Requisitos del archivo de entrada

### Packing List

Debe tener columnas similares a:

| CTN# | Artículo | S | M | L | XL |
|------|----------|---|---|---|----|

### Pedidos de Clientes

Debe tener una fila por talle, y columnas por cliente:

| Talle | Cliente A | Cliente B | Cliente C |
|-------|-----------|-----------|-----------|
| S     | 200       | 100       | 50        |

---

## 🧩 Librerías necesarias

Estas son algunas de las librerías que utiliza el proyecto:

- `streamlit`
- `pandas`
- `xlsxwriter`
- `python-docx`
- `google-generativeai`

Todas se instalan automáticamente con el archivo `requirements.txt`.

---

## 🧪 Consideraciones adicionales

- El modelo Gemini puede no ser perfecto. Esta es una **versión beta** centrada en demostrar el potencial de la IA aplicada a logística.
- Se prioriza simplicidad: la IA decide la redistribución, y Python solo procesa la salida.
- Para mejorar la lógica de distribución, se puede avanzar hacia un enfoque mixto IA + lógica de negocio en Python.

---

## 🧑‍💻 Autor

Este proyecto fue desarrollado por **Lautaro**, como parte de un trabajo práctico integrador sobre el uso de IA en aplicaciones reales con interfaces interactivas.

---

## 📬 Contacto

Si querés sugerir mejoras, podés abrir un issue o contactar al autor directamente.