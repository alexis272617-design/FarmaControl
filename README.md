<p align="center">
  <img src="banner.svg" alt="FarmaControl" width="720">
</p>

<p align="center">
  <img src="logo-mayos.jpg" alt="Mayos Pharmaceutical" width="420">
</p>

<p align="center">
  <b>Sistema de gestión integral para droguerías</b><br>
  Desarrollado en Java con programación orientada a objetos, para la droguería Mayos Pharmaceutical (Florencia, Caquetá).
</p>

<p align="center">
  <a href="https://alexis272617-design.github.io/FarmaControl/">Ver la demostración web</a>
</p>

> **Estado: en desarrollo.** El modelo no está completo y se actualiza a medida que avanza el proyecto.
> La demostración web es una réplica en JavaScript de la lógica del modelo Java; guarda sus datos solo en tu navegador.
> Sus usuarios de prueba son ficticios.

## Qué resuelve

Una droguería de barrio suele llevar sus cuentas en cuadernos: inventario, ventas, deudas con los depósitos y gastos. FarmaControl reúne todo en un solo lugar, rápido y con reglas que evitan errores de digitación y descuadres.

## Funciones

- **Inventario** con búsqueda por código y por nombre, alertas de stock bajo y control de lotes y vencimientos.
- **Clientes** que nunca se eliminan: se inactivan y conservan su historial.
- **Ventas** con validación de stock, medio de pago (efectivo, transferencia o tarjeta) y precio congelado en la factura.
- **Anulación de ventas** dentro de un plazo configurable, que devuelve el stock y deja constancia en el libro.
- **Compras y deudas con los depósitos**, con abonos y saldo pendiente.
- **Usuarios con roles** (administrador y cajero) y permisos distintos para cada operación.
- **Cierre diario con arqueo** (efectivo esperado contra efectivo contado) y **consolidados** por día, mes o periodo.

## Arquitectura

Paquete `mundo`, con las clases del negocio:

| Grupo | Clases |
|---|---|
| Núcleo | `InformacionDrogueria`, `Cliente`, `Producto`, `Proveedor` |
| Ventas | `Factura`, `DetalleFactura`, `MedioDePago` |
| Compras y deudas | `Compra`, `DetalleCompra`, `Deuda`, `Abono` |
| Dinero | `MovimientoFinanciero`, `TipoMovimiento`, `CierreDiario`, `ResumenVentasPeriodo` |
| Usuarios | `Usuario` (abstracta), `Administrador`, `Cajero` |
| Reglas | `ReglaNegocioException` |

Los cuatro pilares de la programación orientada a objetos están presentes: abstracción (cada clase modela una parte del negocio), encapsulamiento (atributos privados y acceso por `dar...`), herencia (`Usuario` con sus hijas) y polimorfismo (cada rol responde distinto a `permitirFacturarVenta()` y los demás permisos).

## Cómo ejecutarlo

1. Abre el proyecto en NetBeans (JDK 17 o superior).
2. Ejecuta la clase `Main` del paquete `mundo`.

## Hoja de ruta

- [x] Modelo de clases y relaciones
- [x] Ventas, anulaciones, compras y deudas
- [x] Usuarios, roles y permisos
- [x] Cierre diario y consolidados
- [ ] Movimientos de inventario y control de vencimientos
- [ ] Cálculo de utilidad
- [ ] Persistencia de datos
- [ ] Versión en la nube con base de datos

## Créditos

Proyecto de la asignatura Lógica y Algoritmos II, Programa de Ingeniería de Sistemas, Universidad de la Amazonia.
Autores: _completa aquí tu nombre_.
