Aquí tienes un ejemplo claro de cómo estructurar una base de datos tipo NoSQL (como en MongoDB) para un consultorio dental. En este modelo trabajas con **bases de datos → colecciones → documentos (JSON)**.

---

# 🦷 Base de datos: `dentista_db`

## 📁 Colección: `pacientes`

Cada documento representa un paciente.

```json
{
  "_id": "ObjectId",
  "nombre": "string",
  "apellido": "string",
  "fecha_nacimiento": "date",
  "telefono": "string",
  "email": "string",
  "direccion": {
    "calle": "string",
    "ciudad": "string",
    "codigo_postal": "string"
  },
  "historial_medico": [
    {
      "enfermedad": "string",
      "alergias": "string",
      "medicamentos": "string"
    }
  ],
  "fecha_registro": "date"
}
```

---

## 📁 Colección: `doctores`

Información de los dentistas.

```json
{
  "_id": "ObjectId",
  "nombre": "string",
  "especialidad": "string",
  "telefono": "string",
  "email": "string",
  "cedula_profesional": "string",
  "horario": {
    "dias": ["string"],
    "hora_inicio": "string",
    "hora_fin": "string"
  }
}
```

---

## 📁 Colección: `citas`

Registra las citas entre paciente y doctor.

```json
{
  "_id": "ObjectId",
  "paciente_id": "ObjectId",
  "doctor_id": "ObjectId",
  "fecha": "date",
  "hora": "string",
  "motivo": "string",
  "estado": "string", 
  "notas": "string"
}
```

📌 Ejemplo de valores para `estado`:

* "pendiente"
* "confirmada"
* "cancelada"
* "completada"

---

## 📁 Colección: `tratamientos`

Tratamientos realizados a pacientes.

```json
{
  "_id": "ObjectId",
  "paciente_id": "ObjectId",
  "doctor_id": "ObjectId",
  "tipo_tratamiento": "string",
  "descripcion": "string",
  "costo": "number",
  "fecha": "date"
}
```

---

## 📁 Colección: `pagos`

Registro de pagos realizados.

```json
{
  "_id": "ObjectId",
  "paciente_id": "ObjectId",
  "tratamiento_id": "ObjectId",
  "monto": "number",
  "metodo_pago": "string",
  "fecha_pago": "date",
  "estado": "string"
}
```

📌 Ejemplo de `metodo_pago`:

* "efectivo"
* "tarjeta"
* "transferencia"

---

# 🧠 Relación entre colecciones

Aunque NoSQL no usa relaciones estrictas como SQL, aquí se conectan mediante IDs:

* `pacientes` ↔ `citas`
* `doctores` ↔ `citas`
* `pacientes` ↔ `tratamientos`
* `tratamientos` ↔ `pagos`

---

# ✅ Ventajas de este modelo

* Flexible (puedes agregar nuevos campos sin romper la estructura)
* Ideal para historiales médicos complejos
* Escalable

---

Si quieres, puedo darte el mismo ejemplo pero en **SQL (MySQL/PostgreSQL)** o incluso ayudarte a diseñarlo para una app real (con validaciones, índices y mejores prácticas).
