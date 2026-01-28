# Modelo de Datos - GlucoReset 📊

Este documento detalla la estructura lógica de la base de datos para la aplicación GlucoReset, diseñada para ser implementada en **Microsoft Dataverse**.

## 1. Tabla: `GlucoseLogs` (Registros de Glucosa)
Almacena las mediciones diarias del usuario.

| Campo | Tipo de Dato | Descripción |
| :--- | :--- | :--- |
| `LogID` | GUID (PK) | Identificador único del registro. |
| `Timestamp` | DateTime | Fecha y hora de la medición. |
| `GlucoseLevel` | Decimal | Nivel de azúcar en sangre (mg/dL). |
| `Moment` | Choice | Pre-prandial, Post-prandial, Ayunas, Antes de dormir. |
| `Notes` | Multiline Text | Observaciones sobre síntomas o malestar. |

## 2. Tabla: `NutritionRegistry` (Gestión de Alimentos)
Base de datos de alimentos y su impacto glucémico.

| Campo | Tipo de Dato | Descripción |
| :--- | :--- | :--- |
| `FoodID` | GUID (PK) | Identificador único del alimento. |
| `FoodName` | String | Nombre del alimento o producto natural. |
| `GlycemicIndex` | Integer | Bajo (1-55), Medio (56-69), Alto (70+). |
| `Carbs_per_100g` | Decimal | Cantidad de carbohidratos. |
| `NaturalRemedy` | Boolean | Indica si es un recurso natural (ej. Vinagre de Manzana). |

## 3. Tabla: `ActivityPlanner` (Plan de Ejercicios)
Seguimiento de la actividad física para el control natural.

| Campo | Tipo de Dato | Descripción |
| :--- | :--- | :--- |
| `ActivityID` | GUID (PK) | Identificador único de la actividad. |
| `Type` | Choice | Caminata, Yoga, Resistencia, HIIT. |
| `Duration` | Integer | Tiempo en minutos. |
| `Intensity` | Choice | Baja, Media, Alta. |

---
*Este esquema servirá como base para la automatización de alertas mediante **Power Automate**.*
