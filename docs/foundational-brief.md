# Foundational Brief — ARQUITECTURA AI

**Author:** Juan (operator) — `jlvelasquez-nomba`
**Date:** 2026-05-26
**Source:** Original document delivered as PDF, transcribed here verbatim.
**Status:** Canonical. This is the document that triggered creation of claude-ops.

---

> "Si quiero talar un árbol en 4 horas pasaré las primeras 3 afilando el hacha."
> — Abraham Lincoln

Con esta premisa en mente, apremia valorar una manera de darle la vuelta a cómo la IA entiende el montaje y ensamblaje de proyectos de código online. Desde drafting y planning, hasta inception. Pensar que en el gold rush la gran mayoría de los que se forró no fue por minar oro, sino por dar herramientas como picos, palas, vestimenta, viviendas y comida a los que intentaron ir a forrarse con el oro. Tuvieron una visión transversal de la tendencia y supieron ver las cosas por donde no las ve el resto.

> "Any sufficiently advanced technology is indistinguishable from magic."
> — Arthur C. Clarke

## Problemas importantes de la IA al entender la arquitectura de proyectos digitales

(Desde un simple componente de Framer hasta un proyecto full stack para millones de usuarios.)

### 1. El planning es pobre

Ve las cosas muy a lo pequeño tomando en cuenta solo lo feature-wise, pero sin entender el gran esquema del proyecto solicitado funcional para el final user, haciendo que no entienda cómo conectar y hacer que las conexiones funcionen entre estos features. No hay un sistema de metas y de milestones que hagan que el proyecto vaya de 0 a 101% estando recorded.

### 2. Le falta entender cómo funcionan las apps full-stack como endpoints de referencia

No entiende bien la arquitectura, la lógica, funcionalidades y conexiones de cómo las grandes apps y repos de código funcionan para poder deliver al usuario la mejor experiencia en cuanto a X producto. El error que comete está en coger el repo y usarlo sin entender el todo por sus partes y viceversa. En cada caso particular, debería de coger 2-3 modelos de apps de referencia y usarlos en cuanto a crear componentes y aplicaciones totalmente funcionales.

Ejemplo: para SupraCRM, serviría coger ejemplos de Huly.io y Salesforce y triangular qué tienen en común, qué hace que funcione cada una de estas aplicaciones, por qué funcionan, qué hacen para que sean estables en future versions.

Que pueda entender que si quiero montar algo como un CRM, cojo stacks y ejemplos de los top MVPs a nivel de git stars, funcionalidad, reviews online, valuation (pero viendo la letra pequeña, evitando mismatching de inversores equívocos), phases del proyecto, etc.

### 3. Le falta tener una estructuración overall de cómo empezar y acabar proyectos

Repite malos patrones de trabajo humanos: toma decisiones muy precipitadas, da por hecho muchísimas cosas, entiende mal el contexto de su trabajo y acaba haciendo cosas a medias, sacrificando funcionalidad real por respuestas mediocres, UX/UI que le toma demasiado tiempo y acaba siendo malísimo, intentando ser un shotgun donde intenta atacar toda la app del tirón y montarla ya, en vez de empezar por el paso 1, la capa 1: el planning que lo hace funcional, escalable y viable. Luego iría el backend, etc.

### 4. Se enfoca demasiado en tener un mockup que en que sea funcional

Importa más que funcionen APIs, repos, procesos, comunicación entre lenguajes de código, conexiones entre nodos y líneas y demás, que en que se vea bonito. Luego ya nos encargaremos de una estética completa y totalmente preciosa. Pero lo mismo, intentando tener todo montado del tirón, ya sacrifica muchísimas cosas. Ejemplo: si le pido que me monte un SaaS de booking, lo monta todo a nivel de UX/UI que te deja presionar botones, pero luego no funciona, se rompe, los spacings y los paddings no respetan nada. Ni backend, ni middlend ni frontend se casan y se conectan hasta el vigésimo tercer intento y por ende, acabamos en tierra de nadie: ni hay un mockup chulo, ni hay un modelo funcional. Acabamos gastando tokens, dinero y tiempo. Pasemos de modelo funcional a darle una estética chula.

**A.** Que tú te centres en preguntarte: ¿qué hace que este componente/feature/proyecto funcione? ¿Por qué? ¿Cómo? ¿Cómo empezamos en un scale 1:1 a millions si fuera el caso? Siguiendo el grand scheme del proyecto ya mencionado. Pregúntame estas cosas a un nivel que yo te pueda responder fácilmente. Esto es para ti. Pero también hay que hacer preguntas al usuario no técnico para que pueda explicarte el proyecto de la mejor manera posible y entender como un equipo para que funciona cada cosa.

### 5. Demasiado tiempo en iteraciones estúpidas

No hay una manera real de obtener un debugging rápido de gilipolleces/tonterías que nos permitan ahorrar tiempo y evitar cometer más errores en código que ya está bien. Buscar maneras de encapsular el approach para evitar que toque cosas que no tienen sentido. A su vez, cuando haga un general scope o aperture el modelo/proyecto para revisarlo pueda debuggear entendiendo qué es lógico y qué no.

### 6. Aprender de pro devs

Intentemos entender y buscar cómo funcionan los pro developers en las grandes tecnológicas: Mag7 companies, OpenAI, Anthropic, Tesla/SpaceX/xAI y muchos de los developers como Linus Torvalds, Vitalik Buterin, Steve Wozniak entre otros que hicieron grandes aportaciones al mundo del desarrollo y programación. Busquemos la manera de entender su trabajo y trabajar al nivel de ellos.

### 7. Equilibrio realista-optimista

Por último intentemos conseguir un intermedio casable entre "trabajemos sobre lo que hay" y "the sky is the limit". Pensemos en una manera realístico-optimista, de cara a que trabajamos de la mejor manera sobre lo que hay y pensamos en soluciones creativas a los problemas.

---

> Adelante, feel free to improve y añadir más cosas. Piensa que debe ser holístico. Para los patrones, workflows, work-structures, architectures de pro devs, valdría la pena dedicarle un buen overview e insight para conseguir que sea funcional en todos los proyectos.

## Rule #0 (added during processing of this brief)

**Nunca, nunca inventar sources.** Tanto para montar códigos y proyectos como para references de los pro devs. Si no está escrito por ellos en sus socials, su substack, página web, GitHub, repo, Wikipedia o "x" tipo de wiki, no es suyo. E intentar tener una red buena, ni muy grande pero ni tan chica, de estos developers.

This becomes `protocols/no-fabrication.md` (Rule #0). Overrides all other protocols.
