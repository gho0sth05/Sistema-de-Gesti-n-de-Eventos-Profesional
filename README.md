# 🎉 EventHub - Sistema de Gestión de Eventos Profesional
###  PROBLEMA

#### Situación Actual:
En la industria de eventos, existen múltiples puntos que afectan tanto a organizadores como a asistentes como lo son :

**Para Organizadores de Eventos:**
-  **Gestión fragmentada**: Uso de 5-7 herramientas diferentes (Excel, email, WhatsApp, plataformas de pago) para un solo evento
-  **Pérdida de ingresos**: 30-40% de deserción en ventas por procesos complicados de compra
-  **Tiempo desperdiciado**: 15-20 horas semanales en tareas manuales repetitivas
-  **Falta de visibilidad**: Sin datos en tiempo real sobre ventas, asistencia o ROI de patrocinadores
-  **Comunicación ineficiente**: Dificultad para notificar cambios o actualizaciones a cientos de asistentes

**Para Asistentes:**
-  **Experiencia fragmentada**: Múltiples plataformas para buscar, comprar y gestionar tickets
-  **Procesos confusos**: Check-in manual lento y propenso a errores
-  **Falta de información**: Sin actualizaciones en tiempo real sobre el evento

**Para Patrocinadores:**
-  **ROI incierto**: No hay métricas claras del retorno de inversión
-  **Falta de seguimiento**: Dificultad para medir la exposición de marca obtenida

#### Características Principales:

#####  Gestión Completa de Eventos
- Creación y publicación de eventos con categorización inteligente
- Administración de ubicaciones y capacidades
- Estados de eventos en tiempo real (borrador, publicado, en curso, finalizado, cancelado)
- Dashboard con estadísticas y métricas clave

#####  Sistema Inteligente de Ticketing
- Múltiples tipos de tickets por evento (VIP, General, Estudiante, etc.)
- Control de inventario en tiempo real
- Códigos de descuento personalizables
- Sistema de compra simplificado (3 clics)
- Generación automática de tickets digitales con QR

#####  Gestión Avanzada de Asistentes
- Registro y perfiles detallados
- Check-in instantáneo mediante QR code
- Historial de asistencia
- Sistema de encuestas post-evento
- Exportación de datos para marketing

#####  Módulo de Patrocinios
- Niveles de patrocinio configurables (Platinum, Gold, Silver, Bronze)
- Seguimiento de beneficios entregados
- Reportes de ROI y exposición de marca
- Gestión de relaciones con patrocinadores

#####  Sistema de Notificaciones
- Emails automáticos para:
  - Confirmación de compra
  - Recordatorios de eventos
  - Cambios o cancelaciones
  - Encuestas de satisfacción
- Notificaciones personalizables por evento

#####  Analytics y Reportes
- Estadísticas en tiempo real
- Reportes de ventas y asistencia
- Métricas de conversión
- Dashboard ejecutivo para toma de decisiones

---
#  Distribución de Responsabilidades por Integrante

---

##  Sarah — App: **EVENTS**
**Responsabilidad Principal:** Gestión de eventos, categorías y ubicaciones

### 📌 Tareas Asignadas

#### **Modelos** (`apps/events/models.py`)
- ✅ `Category` — Categorías de eventos  
- ✅ `Venue` — Ubicaciones/Lugares  
- ✅ `Event` — Eventos principales con todas sus relaciones  

#### **Serializers** (`apps/events/serializers.py`)
- ✅ `CategorySerializer` (básico y con conteo)  
- ✅ `VenueSerializer` (básico y detallado)  
- ✅ `EventSerializer` (listado, detalle y creación)  

#### **ViewSets** (`apps/events/views.py`)
- ✅ `CategoryViewSet` — CRUD categorías  
- ✅ `VenueViewSet` — CRUD ubicaciones  
- ✅ `EventViewSet` — CRUD completo con acciones adicionales:  
  - Publicar / Despublicar eventos  
  - Cancelar eventos  
  - Obtener estadísticas  

#### **Filtros** (`apps/events/filters.py`)
`EventFilter` con filtros por:
- Título, descripción  
- Categoría, ubicación  
- Fechas (inicio, fin, específica)  
- Estado, capacidad  

#### **URLs** (`apps/events/urls.py`)
- ✅ Router con endpoints de categorías, ubicaciones y eventos  

#### **Tests** (`apps/events/tests.py`)
- ✅ Pruebas unitarias para modelos y endpoints  

#### **Admin** (`apps/events/admin.py`)
- ✅ Configuración del panel administrativo  

---

##  Karen — App: **TICKETS**
**Responsabilidad Principal:** Gestión de tickets, precios y descuentos

###  Tareas Asignadas

#### **Modelos** (`apps/tickets/models.py`)
- ✅ `TicketType` — Tipos de ticket por evento  
- ✅ `Ticket` — Tickets individuales  
- ✅ `DiscountCode` — Códigos de descuento  

#### **Serializers** (`apps/tickets/serializers.py`)
- ✅ `TicketTypeSerializer` (básico y detallado)  
- ✅ `TicketSerializer` (listado, detalle, creación)  
- ✅ `TicketPurchaseSerializer` — Para compras  
- ✅ `DiscountCodeSerializer`  

#### **ViewSets** (`apps/tickets/views.py`)
- ✅ `TicketTypeViewSet`  
  - Verificar disponibilidad  
  - Actualizar inventario  

- ✅ `TicketViewSet`  
  - Compra de tickets  
  - Cancelación  
  - Verificación  
  - Descarga de PDF  

- ✅ `DiscountCodeViewSet`  

#### **Filtros** (`apps/tickets/filters.py`)
- `TicketTypeFilter` — Por evento, disponibilidad, precio  
- `TicketFilter` — Por evento, estado, usuario, código  

#### **URLs** (`apps/tickets/urls.py`)
- Router con endpoints de tipos, tickets y descuentos  

#### **Tests** (`apps/tickets/tests.py`)
- Pruebas para compra, cancelación y descuentos  

#### **Admin** (`apps/tickets/admin.py`)
- Configuración del panel administrativo  

---

##  Neyireth — App: **ATTENDEES**
**Responsabilidad Principal:** Gestión de asistentes, registros y check-in

###  Tareas Asignadas

#### **Modelos** (`apps/attendees/models.py`)
- ✅ `Attendee`  
- ✅ `CheckInLog`  
- ✅ `Survey`  
- ✅ `SurveyQuestion`  
- ✅ `SurveyResponse`  

#### **Serializers** (`apps/attendees/serializers.py`)
- `AttendeeSerializer`  
- `CheckInLogSerializer`  
- `SurveySerializer` (básico y detallado)  
- `SurveyQuestionSerializer`  
- `SurveyResponseSerializer`  

#### **ViewSets** (`apps/attendees/views.py`)
- `AttendeeViewSet`  
  - Check-in  
  - Historial de check-ins  
  - Exportación  

- `SurveyViewSet`  
  - Responder encuesta  
  - Ver resultados  
  - Estadísticas  

#### **Filtros** (`apps/attendees/filters.py`)
- `AttendeeFilter` — Por nombre, email, evento, estado  

#### **URLs** (`apps/attendees/urls.py`)
- Router con endpoints de asistentes y encuestas  

#### **Admin** (`apps/attendees/admin.py`)
- Configuración del panel administrativo  

---

##  Aslhy — App: **SPONSORS** *(Líder del Proyecto)*
**Responsabilidad Principal:** Gestión de patrocinadores y coordinación general

###  Tareas Asignadas

#### **Modelos** (`apps/sponsors/models.py`)
- `SponsorTier`  
- `Sponsor`  
- `Sponsorship`  
- `SponsorBenefit`  

#### **Serializers** (`apps/sponsors/serializers.py`)
- `SponsorTierSerializer`  
- `SponsorSerializer` (básico y detallado)  
- `SponsorshipSerializer`  
- `SponsorBenefitSerializer`  

#### **ViewSets** (`apps/sponsors/views.py`)
- `SponsorTierViewSet` — CRUD  
- `SponsorViewSet` — CRUD con:  
  - Historial  
  - ROI y estadísticas  
- `SponsorshipViewSet` — Gestión con:  
  - Activar/desactivar  
  - Beneficios entregados  
  - Reporte de exposición  
- `SponsorBenefitViewSet`  

#### **Filtros** (`apps/sponsors/filters.py`)
- `SponsorFilter` — Por nombre, industria, tier, estado  
- `SponsorshipFilter` — Por evento, patrocinador, tier, estado  

#### **URLs** (`apps/sponsors/urls.py`)
- Router de todos los endpoints de sponsors  

#### **Tareas de Coordinación (Líder)**
- Configuración inicial del proyecto  
- Exception handler global  
- Permisos personalizados  
- URLs principales  
- Health check  
- Script `init_db.py`  
- Configuración de Docker y Render  
- README y documentación  
- Integración entre apps  

#### **Admin** (`apps/sponsors/admin.py`)
- Configuración del panel administrativo  

---

##  Dependencias Entre Apps
┌─────────────┐
│   EVENTS    │◄─────┐
│   (Sarah)   │      │
└──────┬──────┘      │
       │             │
       ├─────────────┼─────────────┐
       │             │             │
       ▼             ▼             ▼
┌─────────────┐ ┌─────────────┐ ┌─────────────┐
│   TICKETS   │ │  ATTENDEES  │ │  SPONSORS   │
│   (Karen)   │ │ (Neyireth)  │ │   (Aslhy)   │
└─────────────┘ └─────────────┘ └─────────────┘
- Todas las apps dependen de EVENTS como modelo central

**Todas las apps dependen de EVENTS como modelo central.**

---

##  Tareas Compartidas (Todos)

### Instalación y Configuración Inicial
- Crear entorno virtual  
- Instalar dependencias (`requirements.txt`)  
- Configurar base de datos MySQL  
- Configurar archivo `.env`  

### Testing
- Cada integrante crea tests para su app  

### Migraciones
- Aplicación de migraciones completa para cada app  

---





