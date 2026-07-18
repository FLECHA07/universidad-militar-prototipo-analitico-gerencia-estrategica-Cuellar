# TABLA PRIORIZACIÓN

## Estructura de la hoja

| Columna | Encabezado |
|---------|------------|
| A | Causa |
| B | Fase DT origen (E/D/I) |
| C | Insight de empatía |
| D | Supuesto central |
| E | Pregunta analítica |
| F | Variables (nombres exactos) |
| G | Tipo (Outcome / Explic / Control / Segmento) |
| H | Cálculo / Transformación |
| I | Métrica (nombre + fórmula) |
| J | Periodo / Segmento |
| K | Patrón esperado (si cierta) |
| L | Condición refutación |
| M | Valor esperado para usuario/ciudadano |
| N | Riesgo si falsa |
| O | Acción si confirma |
| P | Acción si refuta |
| Q | Experimento analítico mínimo (query + visual 1 línea) |
| R | Estado (V/A/R) |

---

# Registro Fila 2

## A. Causa

Capacitación insuficiente poco práctica para el personal operativo.

---

## B. Fase DT origen

**E / Empatizar**

---

## C. Insight de empatía

Los operarios sienten frustración e inseguridad porque no reciben capacitación práctica ni acompañamiento suficiente para utilizar el nuevo ERP con confianza.

---

## D. Supuesto central

Si al personal se le brinda capacitación práctica sobre SAP S/4HANA, entonces obtendrá una mayor adopción del sistema por parte del personal operativo.

---

## E. Pregunta analítica

¿La capacitación práctica sobre SAP S/4HANA incrementa la adopción del sistema por parte del personal operativo?

---

## F. Variables

1. employee_id
2. department_name
3. job_role
4. training_hours_practical
5. training_score
6. training_completion_status
7. sap_error_count

---

## G. Tipo de variables

| Variable | Tipo |
|----------|------|
| employee_id | Control |
| department_name | Segmento |
| job_role | Segmento |
| training_hours_practical | Explicativa |
| training_score | Explicativa |
| training_completion_status | Explicativa |
| sap_error_count | Outcome |

---

## H. Cálculo / Transformación

1. Filtrar `department_name = Producción`.
2. Filtrar `training_completion_status = Completado`.
3. Depurar registros duplicados (`employee_id`).
4. Clasificar empleados con `erp_adoption_score ≥ 80`.
5. Contar usuarios con adopción satisfactoria.
6. Contar total de usuarios capacitados.
7. Calcular el porcentaje de adopción (IAOS).

---

## I. Métrica

### Nombre

**Índice de Adopción Operativa de SAP S/4HANA (IAOS)**

### Fórmula

```text
IAOS =
(Colaboradores que adoptaron SAP /
Total de colaboradores capacitados)
× 100
```

---

## J. Periodo

Mensual, durante los primeros seis meses posteriores a la implementación de SAP S/4HANA.

---

## K. Patrón esperado

**≥ 85 %**

---

## L. Condición de refutación

**≤ 60 %**

---

## M. Valor esperado para el usuario

El personal operativo utilizará SAP S/4HANA reduciendo errores durante la implementación.

---

## N. Riesgo si la hipótesis es falsa

La organización perderá recursos económicos y credibilidad en el proceso de implementación de SAP S/4HANA.

---

## O. Acción si confirma

Establecer como política que ningún colaborador operativo inicie actividades en SAP S/4HANA sin haber completado y aprobado la capacitación práctica.

---

## P. Acción si refuta

Implementar inmediatamente un plan de comunicación y acompañamiento operativo para el personal de producción, incluyendo:

- reuniones semanales de seguimiento;
- espacios de aclaración de dudas;
- usuarios líderes por turno;
- soporte en sitio durante el uso de SAP S/4HANA.

---

## Q. Experimento analítico mínimo

*Sin diligenciar.*

---

## R. Estado

*Sin diligenciar.*

---

# Estado de la hoja

| Fila | Estado |
|------|--------|
| 1 | Encabezados |
| 2 | Registro completo |
| 3 | Vacía |
| 4 | Vacía |
| 5 | Vacía |
| 6 | Vacía |
| 7 | Vacía |
| 8 | Vacía |
| 9 | Vacía |
| 10 | Vacía |
| 11 | Vacía |
| 12 | Vacía |
| 13 | Vacía |
| 14 | Vacía |
| 15 | Vacía |
