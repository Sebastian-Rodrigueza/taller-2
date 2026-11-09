# Anexo: prompts a la IA generativa

Estos son los mensajes que el equipo le escribió a Claude Code durante el trabajo, en orden cronológico y tal como se enviaron (con sus errores de tipeo). Solo se cambiaron las rutas locales por `[ruta local]` y se quitó una frase sobre la configuración de GitHub. Las imágenes pegadas se indican entre corchetes.

El resumen de uso, modelos y porcentajes está en la sección 7 de `Taller2.ipynb`.

## Revisión inicial y secciones 1–3

**1. 2026-11-04 00:05**

> quiero que despliegues un conjunto de subagentes que usen el ultimo modelo de Sonnet o haiku (dependiendo la complejidad de la tarea) para llevar a cabo tareas que tu mismo vas a definir a partir de los requerimientos en el enunciado del taller2. Quiero que cada punto sea revisado y me des un porcentaje de completitud y sugerencias para mejorarlo o completarlo. Quiero que cada agente use superpowers para completar su tarea y como parte de su contexto sea un scientifico de datos senior. Tu vas ser el agente orquestador que se va a encargar de validar y entregar los resultados de cada subagente de manera ordenada.
> cada reporte se va a escribir bajo una carpeta escondida llamada .claude, esta, sobra decirlo, no va a ser subida al repositorio remoto. Todos los reportes y herramientas que va a ser usadas solo por claude, van a estar dentro de esta carpeta. 
> Tambien quiero que utilices el feedback que los profesores junto con los enunciados en mi ultimo taller y en mi parcial para identificar exactamente de que manera se califica y como obtener el mejor puntaje:
> parcial:
> [ruta local]/examen-1
> feedback:
>
>
> <pasted_content id="1375">
> Comentario general
> El trabajo es muy completo y coherente: la limpieza se propaga a todo el análisis, el EDA anticipa decisiones posteriores y el modelo de log10(precio) (R² = 0.72) está bien interpretado. Se convirtieron los coeficientes a cambios porcentuales (−10% por año) y se utilizó el ratio precio observado/esperado para comparar cada carro contra sus comparables. La revisión crítica del top 15, donde se detectó que el Chevrolet City Express es una van mal segmentada, muestra muy buen criterio analítico.
>
> La mayor oportunidad de mejora está en `car_rating`. Se encontró que los "overpriced" son los más baratos incluso controlando edad, segmento y marca, lo que sugiere que la etiqueta no mide el precio frente a comparables. Sin embargo, se utilizó como filtro (great/good) y como predictor del modelo, lo que contamina el precio esperado. Antes de aceptar una etiqueta del marketplace, conviene validarla contra el residuo del modelo sin incluirla. Además, el modelo omite el kilometraje sin justificarlo; es una variable que debe incorporarse o cuya exclusión debe justificarse con evidencia. También faltó explorar la transmisión y el combustible.
>
> El ranking por descuento frente a comparables con filtros de riesgo es un buen método; podría reforzarse incorporando el kilometraje y los dueños al criterio de priorización, no solo como columnas informativas. Es importante cuidar el lenguaje causal: una prueba de Kruskal-Wallis o una regresión con datos observacionales muestran asociaciones. Frases como "body_type produce diferencias en sale_price" o "cada año reduce el precio" deben formularse como asociaciones. En las pruebas de hipótesis, también debe recordarse que, con n grande, Shapiro casi siempre rechaza, por lo que conviene complementar con QQ-plots y discutir la independencia.
> </pasted_content id="1375">
>
>
> taller 1 : [ruta local]/t_contratos_publicos
> feedback: 
>
>
> <pasted_content id="1375">
> Comentario general
> Nota: 3,5/5 (70/100). En la estrategia de análisis (14 de 15), usó cuatro fases con subtítulos y listas en vez de uno o dos párrafos (−1). En el desarrollo del análisis (26 de 40), cuenta el pago en cero como presupuesto no ejecutado, cuando en SECOP puede ser solo falta de registro (−4); su "desviación general" suma señales que solo existen en contratos finalizados, pero la calcula también sobre los abiertos, así que los grupos con muchos contratos en ejecución parecen desviarse menos (−4); cita pruebas de solidez (remuestreo por entidad, Hedges, residuos, repetición sin el 1 % más caro) que no están en el código (−4), y el mapa de calor y las barras de destino solo tienen lecturas generales, sin cifras (−2). En el informe y las recomendaciones (15 de 25), su criterio principal es un puntaje que suma las propias desviaciones, que solo se conocen después de firmar, así que no sirve para elegir desde la firma (−8), y cifras como "~30 %" de desviación en mínima cuantía y "~5.000–8.000" contratos de seguimiento no salen del código o no coinciden con él (−2). Por instrucciones de entrega, trabajó solo y no en pareja (−5).
> </pasted_content id="1375">

**2. 2026-11-04 00:32**

> de nuevo, quiero que despliegues un conjunto de subagentes que usen el ultimo modelo de Sonnet o haiku (dependiendo la complejidad de la tarea) para llevar a cabo cada tarea que tu mismo vas a definir a partir de los requerimientos. Tu vas ser el agente orquestador que se va a encargar de validar y entregar los resultados de cada subagente de manera ordenada.
> 1. de donde sacas que la asimetria de age es 0.996? queremos que se impriman todas las requeridas. no entiendi bien de donde sacas el 0,283, solo veo el 0,28 en la matriz
> 2, 3, completemos esto 
> esto sera el primer commit, luego continuaremos con el punto 4

**3. 2026-11-04 00:46**

> y la grafica de la asimetria sale de los datos limpios? o crudos? el reporte final de la seccion deberia ser de una descripcion de los datos crudos o de los datos ya limpios?

**4. 2026-11-04 01:12**

> crea la rama cuando termine el punto 3

## Umbral de negocio, desbalance y redacción (secciones 3 y 4)

**5. 2026-11-04 20:41**

> tienes todo lo que necesitas para continuar con el 4? usando la misma metodologia de diseno y desarrollo?

**6. 2026-11-04 21:06**

> adelantar el cálculo de ganancia ahora y usar ese umbral desde el 4.

**7. 2026-11-04 21:22**

> como vamos?

**8. 2026-11-04 21:25**

> parece que tenemos agentes sin uso pero activos?

**9. 2026-11-06 20:34**

> me pregunto que estamos haciendo para el desbalance de churn (variable objetivo) en cada modelo

**10. 2026-11-06 20:39**

> pero sin pesos desbalanceados como parametro y buscando optimizar AUC no se incurre en el mismo error que incrementando precision con clases desbalanceadas? si el modelo simplemente escoge a la mayoria como no churn va a aumentar la metrica.

**11. 2026-11-06 20:57**

> si

**12. 2026-11-07 00:33**

> no entiendo muy bien los del umbral de 0.5 vs 0.25

**13. 2026-11-07 00:58**

> me gustaria que la seccion 3.6 y 3.7 fueran mas concisas en su explicacion .

**14. 2026-11-07 01:15**

> explicame esta formula Ganancia anual = VP · `P_EXITO` · `INGRESO` · `HORIZONTE` − contactados · `COSTO_CONTACTO`

**15. 2026-11-07 01:33**

> porque estamos diciendo en algunos lugares que la ganancia es de  291.1 y en otros de 304?

**16. 2026-11-07 01:35**

> quisiera que las explicaciones del punto 4 fueran mas concisas.

**17. 2026-11-07 01:38**

> me gusta esto para el 3 
> - Etiquetas. En 3.7 cada cifra ya dice si es de validación o de prueba. En las secciones 5 y 6 propongo citar solo la de prueba, 304,0 M, y dejar la de validación únicamente donde se explica cómo se eligió el umbral.
> - Un intervalo de confianza. Con un bootstrap de la ganancia en prueba quedaría algo como "304,0 M, intervalo de X a Y". Se vería que 291 y 304 caen dentro del mismo rango, y también la diferencia entre los umbrales 0,20 y 0,25. Ya lo tenía pendiente para la sección 5.

## Sección 4: técnicas de interpretabilidad de la clase

**18. 2026-11-07 01:56**

> para este punto 4 me gustaria que se utilizaran tecnicas de interpretacion que aprendimos en la clase. [ruta local]/CDA-Interpretabilidad.pdf si estan dentro de la clase, mantenerlas, si no, validar si se puede cambiar por una que haya sido viso en clase, si no, mantenerla.

**19. 2026-11-07 01:59**

> instalar en el entorno de conda data-science-applied.

**20. 2026-11-07 02:01**

> perferimos instalar en el entorno de conda data-science-applied que hacer la implementacion nosotros para cualquier libreria

**21. 2026-11-07 02:04**

> no, prefiero que todo quede instalado con pip

**22. 2026-11-07 02:08**

> hecho

## Sección 5: avance y verificación de fuentes

**23. 2026-11-07 03:01**

> has commit y pasamos al 5

**24. 2026-11-07 03:10**

> debemos revisar que cada una de las fuentes sea real

## Revisión de riesgos

**25. 2026-11-07 13:56**

> requiero un repaso de validacion para identificar riesgos comunes. crea un subagente por etapa. [imagen pegada]

**26. 2026-11-07 15:00**

> 1. no entiendo, explica con mas detallee
> 2. no entiendo, explica con mas detalle
> 3. no entiendo, explica con mas detalle
> 4. Corregir
> 5. Corregir asegurandose de que los intervalos son correctamente calculados y mencionados
> 6. que alternativas/sugerencias hay para estos casos?
> 7. que alternativas/sugerencias hay para estos casos?

**27. 2026-11-07 15:56**

> 1. esto es una foto de cuando el cliente ya abandono o no. El active_member es si la persona ha hecho transacciones ultimamente, si abandono o no. y el numbero de productos creo que es un patron que vale la pena notar de que cuando un miembro tiene 4 productos, probablemente va a desertar (no sabemos porque) pero el numero de clientes con 4 productos es muy bajo. Prefiero mantener ambas variables en todo el analisis.  
> 2. me gusta la tabla que quieres agregar, junto con explicaciones concisas. y la propuesta de hacer un modelo sin gender podria ser algo que hariamos en una siguiente, futura iteracion.
> 3. me preocupa que la solucion a repercuta en las referencias a la regresion logistica en todo el resto del notebook. si hacermos la solucion a debemos correr un validador que se asegure que estos resultados son los que se citan en el resto del notebook. 
> 6. me gusta la opcion a para el saldo mezclado con pais, pero si la hacemos, debemos correr un validador que se asegure que estos resultados son los que se citan en el resto del notebook. para las pruebas estadisticas me gusta la opcion C.
> 7. dejemos esto para el final del proyecto, si queda tiempo.

## Explicación de las técnicas de las secciones 4 y 5

**28. 2026-11-07 16:22**

> explicame cada una de las tecnicas de la seccion 5. no entendi muy bien la explicacion del profesor.

**29. 2026-11-07 16:25**

> explicame cada una de las tecnicas de la seccion 4. no entendi muy bien la explicacion del profesor.

## Secciones 6 y 7

**30. 2026-11-07 17:16**

> okay, ahora queremos las secciones 6 y 7. ...
> quiero que despliegues subagentes con tareas bien descritas y delimitadas por ti para hacer el punto 6 y el 7. Queremos utilizar un lenguaje conciso y natural; facil de leer. Trabaja sobre la rama acual (4-5)
