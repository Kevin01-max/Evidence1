# Evidence1


o	BPMN diagram.
Cliente         Cajero                Sistema
   │               │                     │
   │──────────────▶│ Inicia compra       │
   │               │───────────────────▶│ Verifica si cliente existe
   │               │                     │
   │               │◀───────────────────│ Solicita registro si no existe
   │               │ Registra nuevo cliente
   │──────────────▶│ Selecciona productos
   │               │───────────────────▶│ Registra compra y genera ticket
   │               │                     │
   │               │◀───────────────────│ Muestra confirmación
   │               │                     │
   │──────────────▶│ Fin del proceso


o	Class diagrams
+----------------+       +----------------+        +-----------------+
|   Cliente      |       |   Compra       |        |   Producto      |
+----------------+       +----------------+        +-----------------+
| id_cliente     |◄─────┐| id_compra      |◄──┐    | id_producto     |
| nombre         |       | fecha           |  └──▶| nombre          |
| apellidos      |       | id_cliente (FK) |       | precio          |
| calle, número  |       | productos       |       +-----------------+
| id_colonia     |       +----------------+       
+----------------+                                       
          │                                             
          ▼                                             
+----------------+
|   Colonia      |
+----------------+
| id_colonia     |
| nombre         |
+----------------+


o	Activity diagrams
Inicio
  │
  ▼
¿Cliente existe?
  ├─> Sí
  │     ▼
  └─> No ─> Registrar cliente
         ▼
Seleccionar productos
  ▼
Confirmar compra y generar ticket
  ▼
Fin


o	Use case diagrams
[Cliente] ──► (Realizar compra)
             └──► (Seleccionar productos)

[Cajero] ──► (Registrar cliente)
            └──► (Generar ticket)
            └──► (Consultar historial)

Refleccion
Diseñar flujos BPMN, modelos de clases y diagramas de casos de uso me hizo pensar en cómo los procesos de la vida real también se benefician de ser visualizados. Cuando tomamos distancia y mapeamos cómo fluye la información ya sea en un software o en nuestras relaciones es más fácil identificar patrones, ineficiencias y oportunidades.
