## LAB # 21 · Cueva con monedas y caso ZK de verificación de edad

**Modalidad:** hice la actividad con dos personas que conozco. Para no incluir sus nombres, las identifiqué como «Persona 2» y «Persona 3»; yo aparezco como «Yo». Los papeles fueron SÍ, SÍ y NO, respectivamente, y registré las tiradas de una moneda real.

### Parte A · Mi tabla de rondas

**Foto de mi tabla de rondas hecha a mano:** [ver tabla](evidence/tablabuena.jpeg).

**Foto de mi resumen de participantes y resultados:** [ver resumen](evidence/tabla.jpeg).

**Foto de mi ficha del caso 1 hecha a mano:** [ver siete respuestas](evidence/7preguntas.jpeg).

Transcribí el detalle de las rondas que observé. «P» significa que se usó la puerta para salir por el camino pedido. «—» señala que, tras el fallo de Persona 3 en la ronda 7, no cuento las anotaciones posteriores como retos superados.

| Participante | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |
|---|---|---|---|---|---|---|---|---|---|---|
| Yo (SÍ) | ✓ | ✓ | ✓ | ✓ P | ✓ | ✓ P | ✓ P | ✓ | ✓ | ✓ |
| Persona 2 (SÍ) | ✓ P | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| Persona 3 (NO) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✗ | — | — | — |

| Participante | Papel | Resultado observado | Probabilidad de que alguien con NO alcance esa ronda |
|---|---|---|---|
| Yo | SÍ | 10/10; usé la puerta cuando el camino inicial no coincidió con la moneda en las rondas 4, 6 y 7 | No aplica a quien conoce la palabra |
| Persona 2 | SÍ | 10/10; usó la puerta ante una discrepancia en la ronda 1 | No aplica a quien conoce la palabra |
| Persona 3 | NO | Falló en la ronda 7 | Llegar a la ronda 7: 1/64; fallar exactamente allí: 1/128 |

La probabilidad **teórica** para un probador sin la palabra es 1/2ⁿ después de n retos independientes: ronda 1 = 1/2, 2 = 1/4, 3 = 1/8, 4 = 1/16, 5 = 1/32 y 10 = 1/1024 ≈ 0.098 %. En mi registro, Persona 3 pasó seis rondas y falló en la séptima; la probabilidad de llegar a ese reto es 1/64 y la de seguir ese patrón exacto de seis aciertos y un fallo es 1/128.

En mi hoja también marqué cuándo el camino inicial de quienes tenían SÍ no coincidió con la moneda. Eso no fue un fallo de la prueba: ambos conocíamos la palabra, usamos la puerta y salimos por el lado pedido en las diez rondas. El verificador no aprende la palabra y una foto de la tabla sola no convencería a otro trío, porque los retos podrían haberse acordado antes.

### Parte B · Mi ficha del caso 1

El profesor me asignó la verificación de edad de la UE. Respondí las siete preguntas del Apéndice A para ese único caso. Las afirmaciones sobre funcionamiento se basan en fuentes; los puntos de confianza son mi análisis.

#### Verificación de edad de la UE

| # | Pregunta | Mi respuesta |
|---|---|---|
| 1 | ¿Qué se prueba? | Que tengo una atestación válida y vigente que afirma que soy mayor de 18. |
| 2 | ¿Qué permanece secreto? | Mi nombre, fecha de nacimiento e identidad concreta. |
| 3 | ¿Quién prueba y quién verifica? | La persona con la atestación genera la prueba; el sitio que restringe por edad la verifica. |
| 4 | ¿Qué ve el verificador? | La afirmación de mayoría de edad y una prueba válida; no debería recibir los datos personales de la atestación. |
| 5 | ¿Interactiva? ¿SNARK/STARK? ¿Configuración confiable? | Prueba no interactiva; la [especificación de la UE](https://ageverification.dev/av-doc-technical-specification/docs/annexes/annex-B/annex-B-zkp/) describe el esquema ECDSA Anonymous Credentials basado en zkSNARK y dice que **no requiere configuración confiable**. |
| 6 | ¿Qué confianza queda? | Debo confiar en el emisor de la edad, en la corrección del circuito y en la app que genera la prueba; una fecha falsa emitida correctamente seguiría produciendo una prueba válida. |
| 7 | Fuente de §9 | [Anexo ZKP de la solución europea de verificación de edad](https://ageverification.dev/av-doc-technical-specification/docs/annexes/annex-B/annex-B-zkp/). |

### Mi reflexión de tres líneas

1. En la cueva, «Yo» y «Persona 2» completaron 10/10 usando la puerta; Persona 3 llegó por azar a la ronda 7 y falló, así que repetir retos aumentó mi confianza sin revelar la palabra.
2. En la verificación de edad de la UE, una atestación con edad falsa o un circuito que omita revisar su firma podría producir una prueba aceptada; por eso todavía confío en el emisor y en el diseño del circuito.
3. En Pactrail, propondría probar que los requisitos de liberación se cumplieron sin guardar sus documentos completos, siempre que el contrato y quien emite la evidencia sean confiables.
