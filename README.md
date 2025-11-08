# Especificación de Documentación Legal y Comercial - Sistema CJG Electrodomésticos

## 1. Factura preimpresa

* Formato: triplicado, con timbrado vigente de la SET.
* Campos obligatorios:

  * Número de factura (serie y secuencia)
  * Timbrado
  * Fecha de emisión
  * Nombre o razón social del cliente
  * RUC o C.I.
  * Dirección
  * Detalle de producto(s)
  * Precio unitario, total e IVA
  * Nombre del vendedor o secretaria
* Asociaciones automáticas:

  * Venta (contado o crédito)
  * Pagaré
  * Contrato
* Antes de emitir factura, el sistema permite seleccionar **sucursal y timbrado**.
* Registro obligatorio del número utilizado (sin duplicados ni saltos).
* El administrador puede cambiar número o timbrado solo con motivo; se guarda en auditoría.

---

## 2. Pagaré a la orden sin protesto

* Impresión en hoja preimpresa numerada correlativamente.
* Asociado a factura y crédito.
* Campos requeridos:

  * Número de pagaré
  * Fecha de emisión
  * Cliente y codeudores
  * Monto total financiado
  * Número de cuotas y vencimientos
  * Tasa de interés aplicada
* Generación automática de versión PDF.
* El número debe coincidir con el talonario físico y guardarse en historial.

---

## 3. Contrato de compra–venta a crédito (A4)

* El sistema completa automáticamente:

  * Nombre y C.I. del comprador y codeudores
  * Dirección
  * Producto adquirido
  * Monto total
  * Plan de cuotas
  * Fechas de vencimiento
  * Número de factura y pagaré
  * Nombre del vendedor o responsable
* Se genera PDF para impresión y firma.
* Se guarda copia digital firmada o escaneada.
* Asociado directamente a venta, factura y pagaré.

---

## 4. Asociación de documentos

Cada operación de crédito debe mantener la siguiente estructura:

```
VENTA → FACTURA → PAGARÉ → CONTRATO
```

Todos los documentos se visualizan desde la ficha del cliente.

---

## 5. Control de numeración

* Serie independiente por tipo de documento (factura, pagaré, contrato).
* Registro:

  * Número inicial y final del talonario.
  * Timbrado.
  * Vencimiento del timbrado.
  * Sucursal asignada.
* Alertas automáticas si:

  * El timbrado está vencido.
  * Se alcanza el final de la numeración.
* Auditoría fiscal para evitar duplicados o saltos.

---

## 6. Digitalización y respaldo

* Cada documento (factura, pagaré, contrato) se guarda automáticamente en formato PDF.
* Nombre de archivo estructurado:

```
[TipoDocumento]_[Sucursal]_[NroFactura o NroPagare]_[CICliente]_[Fecha].pdf
```

**Ejemplos:**

```
Factura_CDE_0020010004341_1234567_2025-11-08.pdf
Pagare_SALDIVAR_004_CI1021541_2025-11-08.pdf
Contrato_CDE_0010010004316_1021541_2025-11-08.pdf
```

* Las copias digitales están disponibles en:

  * Ficha del cliente
  * Auditoría
  * Documentos legales

---

## 7. Roles y permisos sobre documentos

* **Administrador:** crea/modifica talonarios y timbrados.
* **Secretaria:** emite facturas y contratos (sin editar timbrado/num.).
* **Cobrador:** accede solo a documentos de sus clientes.
* **Contabilidad:** visualiza facturas y contratos aprobados.
* Todos los accesos quedan registrados con usuario, hora y acción.

---

## 8. Campos dinámicos (para automatización)

```
CLIENTE: [NombreCompleto]
C.I.: [CICliente]
DIRECCIÓN: [DireccionCliente]
PRODUCTO: [DescripcionProducto]
MONTO TOTAL: [MontoTotal]
CUOTAS: [NumeroCuotas]
INTERÉS: [InteresAplicado]
FECHA: [FechaVenta]
NRO FACTURA: [NumeroFactura]
NRO PAGARÉ: [NumeroPagare]
VENDEDOR: [NombreVendedor]
SUCURSAL: [Sucursal]
```

---

**Encabezado oficial:**

> CJG ELECTRODOMÉSTICOS
> RUC: 2480083-0
> Ruta 1 Km. 37 entre Cerro Corá y Curupayty - Itá, Paraguay
> Tel.: (0981) 974 871
> "Mil soluciones, un solo lugar"
