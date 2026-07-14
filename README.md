# universidad-militar-prototipo-analitico-gerencia-estrategica-Cuellar
Prototipo analitico y matriz de indicadores para impementacion de sap.
# Tablero de Priorización

## Causa

| Causa |
|--------|
| Capacitación insuficiente poco práctica para el personal operativo. |

## Fase DT de origen

| Fase DT origen (E/D/I) |
|------------------------|
| E / Empatizar |

## Insight de empatía

| Insight de empatía |
|--------------------|
| Los operarios sienten frustración e inseguridad porque no reciben capacitación práctica ni acompañamiento suficiente para utilizar el nuevo ERP con confianza. |

## Supuesto central

| Supuesto central |
|------------------|
| Si al personal se le brinda capacitación práctica sobre SAP S/4HANA, entonces obtendrá mayor adopción del sistema por parte del personal operativo. |

## Pregunta analítica

| Pregunta analítica |
|--------------------|
| ¿La capacitación práctica sobre SAP S/4HANA incrementa la adopción del sistema por parte del personal operativo? |

## Variables del análisis

| Variable | Tipo |
|----------|------|
| employee_id | Control |
| department_name | Segmento |
| job_role | Segmento |
| training_hours_practical | Explicativa |
| training_score | Explicativa |
| training_completion_status | Explicativa |
| sap_error_count | Outcome |

## Transformaciones de datos

| Transformación |
|----------------|
| Filtrar registros donde **department_name = 'Producción'**. |
| Filtrar registros donde **training_completion_status = 'Completado'**. |
| Eliminar registros duplicados utilizando **employee_id**. |
| Clasificar colaboradores con **erp_adoption_score ≥ 80**. |
| Contar colaboradores con adopción satisfactoria. |
| Contar el total de colaboradores capacitados. |
| Calcular el porcentaje de adopción (IAOS). |

## Métrica

| **Nombre del indicador** | Fórmula |
|---------------------------|---------|
| **Índice de Adopción Operativa de SAP S/4HANA (IAOS)** | (Colaboradores que adoptaron SAP S/4HANA / Total de colaboradores capacitados) × 100 |

## Periodo de medición

| Periodo |
|----------|
| Mensual durante los primeros seis meses posteriores a la implementación de SAP S/4HANA. |

## Resultado esperado

| Patrón esperado | **Condición de refutación** |
|-----------------|-----------------------------|
| **≥ 85 %** | **≤ 60 %** |

## Valor esperado

| Valor esperado para el usuario |
|--------------------------------|
| El personal operativo utilizará SAP S/4HANA reduciendo errores en la ejecución de sus procesos. |

## Riesgo si el supuesto es falso

| Riesgo |
|---------|
| La organización perderá recursos económicos y credibilidad durante la implementación de SAP S/4HANA. |

## Acción si confirma

| Acción |
|---------|
| Establecer como política que ningún colaborador operativo inicie actividades en SAP S/4HANA sin haber completado y aprobado la capacitación práctica. |

## Acción si refuta

| Acción |
|---------|
| Implementar un plan de comunicación y acompañamiento operativo para el personal de producción que incluya reuniones semanales, usuarios líderes por turno y soporte en sitio durante el uso de SAP S/4HANA. |

## Experimento Analítico Mínimo

### Consulta SQL

```sql
SELECT
    department_name,
    DATE_TRUNC('month', training_date) AS mes,
    COUNT(CASE WHEN erp_adoption_score >= 80 THEN employee_id END) * 100.0 /
    COUNT(employee_id) AS iaos
FROM sap_training
WHERE department_name = 'Producción'
  AND training_completion_status = 'Completado'
GROUP BY
    department_name,
    DATE_TRUNC('month', training_date)
ORDER BY mes;
```

### Visualización

| Visualización |
|---------------|
| Gráfico de barras del IAOS mensual para el personal operativo del área de Producción. |

## Estado

| Estado |
|--------|
| V (Pendiente de validación). |
# Ficha de Indicador

## Supuesto central

| Supuesto central |
|------------------|
| Si al equipo de producción se le brinda capacitación práctica sobre SAP S/4HANA, obtendrá mayor adopción del sistema por parte del personal operativo. |

## Paso 1. Objetivo del Indicador

| ¿Qué hago? | ¿Cómo lo hago? | ¿Para qué lo hago? |
|-------------|----------------|--------------------|
| Implementar un programa de capacitación práctica sobre SAP S/4HANA dirigido al personal operativo. | Mediante talleres prácticos, simulaciones de procesos reales, ejercicios guiados y acompañamiento durante la ejecución de actividades en SAP S/4HANA. | Incrementar la adopción del sistema SAP S/4HANA por parte del personal operativo y reducir la resistencia al cambio. |

## Paso 2. Factor crítico

| Aspecto específico a medir | Público objetivo | Dimensión |
|----------------------------|------------------|-----------|
| Nivel de adopción del ERP SAP S/4HANA después de recibir capacitación práctica. | Personal operativo. | Eficacia (¿Logra el resultado?). |

## Paso 3. Fórmula

| **Nombre del indicador** | Numerador | Denominador | Fórmula | Prueba de estrés |
|---------------------------|-----------|-------------|----------|------------------|
| **Índice de Adopción Operativa de SAP S/4HANA (IAOS)** | Colaboradores que adoptaron correctamente SAP S/4HANA. | Total de colaboradores operativos capacitados. | (Colaboradores que adoptaron correctamente SAP S/4HANA / Total de colaboradores operativos capacitados) × 100 | El indicador puede verse afectado si los colaboradores utilizan el sistema de manera obligatoria sin comprender realmente los procesos, generando una sobreestimación de la adopción. También puede distorsionarse si existen registros incompletos o si no todos los colaboradores capacitados utilizan el ERP durante el período de evaluación. |

## Paso 4. Unidad

| Tipo |
|------|
| Porcentaje (%) |

## Paso 5. Fuentes

| Frecuencia de medición | Fuente de datos |
|------------------------|-----------------|
| Mensual | 1. Registros del sistema SAP S/4HANA (logs y reportes de uso).<br>2. Reportes del área de Talento Humano y del líder del proyecto de implementación.<br>3. Resultados de las evaluaciones prácticas de capacitación.<br>4. Registros de asistencia y finalización de la capacitación. |

## Paso 6. Seguimiento

| Línea base | Meta | **Condición de refutación** |
|-------------|------|-----------------------------|
| 0 % | **≥ 85 %** | **≤ 60 %** |

## Consulta asociada al indicador

```sql
SELECT
    COUNT(CASE WHEN erp_adoption_score >= 80 THEN employee_id END) * 100.0 /
    COUNT(employee_id) AS iaos
FROM sap_training
WHERE department_name = 'Producción'
  AND training_completion_status = 'Completado';
```

## Visualización sugerida

| Visualización |
|---------------|
| Indicador tipo KPI acompañado de un gráfico de barras que compare el IAOS mensual con la meta del 85 %. |

