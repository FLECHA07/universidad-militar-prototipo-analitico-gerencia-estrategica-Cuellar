| Causa | Fase DT origen (E/D/I) | Insight de empatía | Supuesto central | Pregunta analítica | Variables (nombres exactos) | Tipo (Outcome / Explic / Control / Segmento) | Cálculo / Transformación | Métrica (nombre + fórmula) | Periodo / Segmento | Patrón esperado (si cierta) | Condición refutación | Valor esperado para usuario/ciudadano | Riesgo si falsa | Acción si confirma | Acción si refuta | Experimento analítico mínimo (query + visual 1 línea) | Estado (V/A/R) |
|-------|-------------------------|--------------------|------------------|--------------------|-----------------------------|---------------------------------------------|--------------------------|----------------------------|--------------------|-----------------------------|----------------------|---------------------------------------|-----------------|--------------------|-----------------|-------------------------------------------------------|----------------|
| Capacitación insuficiente poco práctica para el personal operativo | E / Empatizar | Los operarios sienten frustración e inseguridad porque no reciben capacitación práctica ni acompañamiento suficiente para utilizar el nuevo ERP con confianza. | Si al personal se le brinda capacitación práctica sobre SAP S/4HANA, entonces obtendrá una mayor adopción del sistema por parte del personal operativo. | ¿La capacitación práctica sobre SAP S/4HANA incrementa la adopción del sistema por parte del personal operativo? | employee_id<br>department_name<br>job_role<br>training_hours_practical<br>training_score<br>training_completion_status<br>sap_error_count | employee_id = Control<br>department_name = Segmento<br>job_role = Segmento<br>training_hours_practical = Explicativa<br>training_score = Explicativa<br>training_completion_status = Explicativa<br>sap_error_count = Outcome | Filtrar department_name = Producción.<br>Filtrar training_completion_status = Completado.<br>Eliminar registros duplicados (employee_id).<br>Clasificar erp_adoption_score ≥ 80.<br>Contar usuarios con adopción satisfactoria.<br>Contar usuarios capacitados.<br>Calcular IAOS. | **Índice de Adopción Operativa de SAP S/4HANA**<br><br>IAOS = (Colaboradores que adoptaron SAP / Total de colaboradores capacitados) × 100 | Mensual durante los primeros seis meses posteriores a la implementación de SAP S/4HANA. | ≥ 85 % | ≤ 60 % | El personal operativo utilizará SAP S/4HANA reduciendo errores durante la implementación. | La organización perderá recursos económicos y credibilidad en el proceso de implementación de SAP S/4HANA. | Establecer como política que ningún colaborador operativo inicie actividades en SAP S/4HANA sin haber completado y aprobado la capacitación práctica. | Implementar un plan de comunicación y acompañamiento operativo para el personal de producción, con reuniones semanales, usuarios líderes por turno y soporte en sitio durante el uso de SAP S/4HANA. | | Confirmada|
| | | | | | | | | | | | | | | | | | |

| Supuesto central | ¿QUÉ HAGO? (Acción) | ¿CÓMO LO HAGO? (Método) | ¿PARA QUÉ LO HAGO? (Propósito) | Aspecto específico a medir | Público objetivo (Para quién) | Dimensión | Nombre del indicador | Numerador (Variable Y) | Denominador (Población) | Fórmula (Matemática) | Prueba de estrés | Tipo | Frecuencia de medición | Fuente de datos (Verificación) | Línea base (Patrón actual) | Patrón esperado (Meta) | Condición de refutación (Fallo) |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---:|---|---|
| **Si al equipo de producción se le brinda capacitación práctica sobre SAP S/4HANA, obtendrá mayor adopción del sistema por parte del personal operativo.** | Implementar un programa de capacitación práctica sobre SAP S/4HANA dirigido al personal operativo. | Mediante talleres prácticos, simulaciones de procesos reales, ejercicios guiados y acompañamiento durante la ejecución de actividades en SAP S/4HANA. | Incrementar la adopción del sistema SAP S/4HANA por parte del personal operativo y reducir la resistencia al cambio. | Nivel de adopción del ERP SAP S/4HANA después de recibir capacitación práctica. | Personal operativo | Eficacia (¿Logra el resultado?) | Índice de Adopción Operativa de SAP S/4HANA | Colaboradores que adoptaron correctamente SAP S/4HANA | Total de colaboradores operativos capacitados × 100 | `#VALUE!` *(en el archivo de Excel)* | El indicador puede verse afectado si los colaboradores utilizan el sistema de manera obligatoria, pero sin comprender realmente los procesos, generando una sobreestimación de la adopción. También puede distorsionarse si existen registros incompletos o si no todos los colaboradores capacitados utilizan el ERP durante el período de evaluación. | Porcentaje (%) | *(Vacío)* | 1. Registros del sistema SAP S/4HANA (logs y reportes de uso).<br>2. Reportes del área de Talento Humano y del líder del proyecto de implementación.<br>3. Resultados de las evaluaciones prácticas de capacitación.<br>4. Registros de asistencia y finalización de la capacitación. | 0 | Mayor o igual a **85 %** | Menor o igual a **60 %** |


| employee_id | department_name | training_hours_practical | training_score | training_completion_status | sap_error_count | adoption_status |
|---|---|---|---|---|---|---|
| EMP001 | Producción | 20 | 83 | Completado | 2 | ADOPTO |
| EMP002 | Producción | 20 | 84 | Completado | 4 | ADOPTO |
| EMP003 | Producción | 20 | 85 | Completado | 3 | ADOPTO |
| EMP004 | Producción | 20 | 86 | Completado | 2 | ADOPTO |
| EMP005 | Producción | 20 | 87 | Completado | 2 | ADOPTO |
| EMP006 | Producción | 20 | 88 | Completado | 5 | ADOPTO |
| EMP007 | Producción | 20 | 89 | Completado | 4 | ADOPTO |
| EMP008 | Producción | 20 | 90 | Completado | 3 | ADOPTO |
| EMP009 | Producción | 20 | 91 | Completado | 2 | ADOPTO |
| EMP010 | Producción | 20 | 92 | Completado | 2 | ADOPTO |
| EMP011 | Producción | 20 | 93 | Completado | 5 | ADOPTO |
| EMP012 | Producción | 20 | 94 | Completado | 4 | ADOPTO |
| EMP013 | Producción | 20 | 95 | Completado | 3 | ADOPTO |
| EMP014 | Producción | 20 | 96 | Completado | 2 | ADOPTO |
| EMP015 | Producción | 20 | 97 | Completado | 2 | ADOPTO |
| EMP016 | Producción | 20 | 98 | Completado | 5 | ADOPTO |
| EMP017 | Producción | 20 | 99 | Completado | 4 | ADOPTO |
| EMP018 | Producción | 20 | 100 | Completado | 3 | ADOPTO |
| EMP019 | Producción | 20 | 81 | Completado | 2 | ADOPTO |
| EMP020 | Producción | 20 | 82 | Completado | 2 | ADOPTO |
| EMP021 | Producción | 20 | 83 | Completado | 5 | ADOPTO |
| EMP022 | Producción | 20 | 84 | Completado | 4 | ADOPTO |
| EMP023 | Producción | 20 | 85 | Completado | 3 | ADOPTO |
| EMP024 | Producción | 20 | 86 | Completado | 2 | ADOPTO |
| EMP025 | Producción | 20 | 87 | Completado | 2 | ADOPTO |
| EMP026 | Producción | 20 | 88 | Completado | 5 | ADOPTO |
| EMP027 | Producción | 20 | 89 | Completado | 4 | ADOPTO |
| EMP028 | Producción | 20 | 90 | Completado | 3 | ADOPTO |
| EMP029 | Producción | 20 | 91 | Completado | 2 | ADOPTO |
| EMP030 | Producción | 20 | 92 | Completado | 2 | ADOPTO |
| EMP031 | Producción | 20 | 93 | Completado | 5 | ADOPTO |
| EMP032 | Producción | 20 | 94 | Completado | 4 | ADOPTO |
| EMP033 | Producción | 20 | 95 | Completado | 3 | ADOPTO |
| EMP034 | Producción | 20 | 96 | Completado | 2 | ADOPTO |
| EMP035 | Producción | 20 | 97 | Completado | 2 | ADOPTO |
| EMP036 | Producción | 20 | 98 | Completado | 5 | ADOPTO |
| EMP037 | Producción | 20 | 99 | Completado | 4 | ADOPTO |
| EMP038 | Producción | 20 | 100 | Completado | 3 | ADOPTO |
| EMP039 | Producción | 20 | 81 | Completado | 2 | ADOPTO |
| EMP040 | Producción | 20 | 82 | Completado | 2 | ADOPTO |
| EMP041 | Producción | 20 | 87 | Completado | 5 | ADOPTO |
| EMP042 | Producción | 20 | 88 | Completado | 4 | ADOPTO |
| EMP043 | Producción | 20 | 89 | Completado | 3 | ADOPTO |
| EMP044 | Producción | 20 | 90 | Completado | 2 | ADOPTO |
| EMP045 | Producción | 20 | 91 | Completado | 6 | ADOPTO |
| EMP046 | Producción | 20 | 92 | Completado | 5 | ADOPTO |
| EMP047 | Producción | 20 | 93 | Completado | 4 | ADOPTO |
| EMP048 | Producción | 20 | 94 | Completado | 3 | ADOPTO |
| EMP049 | Producción | 20 | 95 | Completado | 2 | ADOPTO |
| EMP050 | Producción | 20 | 96 | Completado | 6 | ADOPTO |
| EMP051 | Producción | 20 | 97 | Completado | 5 | ADOPTO |
| EMP052 | Producción | 20 | 98 | Completado | 4 | ADOPTO |
| EMP053 | Producción | 20 | 99 | Completado | 3 | ADOPTO |
| EMP054 | Producción | 20 | 82 | Completado | 2 | ADOPTO |
| EMP055 | Producción | 20 | 83 | Completado | 5 | ADOPTO |
| EMP056 | Producción | 20 | 84 | Completado | 5 | ADOPTO |
| EMP057 | Producción | 20 | 85 | Completado | 3 | ADOPTO |
| EMP058 | Producción | 20 | 86 | Completado | 3 | ADOPTO |
| EMP059 | Producción | 20 | 87 | Completado | 2 | ADOPTO |
| EMP060 | Producción | 20 | 88 | Completado | 6 | ADOPTO |
| EMP061 | Producción | 20 | 89 | Completado | 5 | ADOPTO |
| EMP062 | Producción | 20 | 90 | Completado | 4 | ADOPTO |
| EMP063 | Producción | 20 | 91 | Completado | 3 | ADOPTO |
| EMP064 | Producción | 20 | 92 | Completado | 2 | ADOPTO |
| EMP065 | Producción | 20 | 93 | Completado | 6 | ADOPTO |
| EMP066 | Producción | 20 | 94 | Completado | 5 | ADOPTO |
| EMP067 | Producción | 20 | 95 | Completado | 4 | ADOPTO |
| EMP068 | Producción | 20 | 96 | Completado | 3 | ADOPTO |
| EMP069 | Producción | 20 | 97 | Completado | 2 | ADOPTO |
| EMP070 | Producción | 20 | 98 | Completado | 6 | ADOPTO |
| EMP071 | Producción | 20 | 99 | Completado | 5 | ADOPTO |
| EMP072 | Producción | 20 | 82 | Completado | 4 | ADOPTO |
| EMP073 | Producción | 20 | 83 | Completado | 3 | ADOPTO |
| EMP074 | Producción | 20 | 84 | Completado | 2 | ADOPTO |
| EMP075 | Producción | 20 | 85 | Completado | 6 | ADOPTO |
| EMP076 | Producción | 20 | 86 | Completado | 5 | ADOPTO |
| EMP077 | Producción | 20 | 87 | Completado | 4 | ADOPTO |
| EMP078 | Producción | 20 | 88 | Completado | 3 | ADOPTO |
| EMP079 | Producción | 20 | 89 | Completado | 2 | ADOPTO |
| EMP080 | Producción | 20 | 90 | Completado | 6 | ADOPTO |
