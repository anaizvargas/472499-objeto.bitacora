# Objeto de estudio
El objeto de estudio elegido es el comportamiento de la  actividad de un conejo doméstico en su entorno. Se aborda desde la perspectiva observacional, con el enfoque en cómo el conejo interactúa con el espacio que habita y cómo responde a ciertos estímulos.

## Interés personal
El interés por este objeto de estudio surge desde la observación cotidiana de un animal adaptado a un hábitat no natural, de la relación de éste con su entorno. Se busca explorar cómo ciertos factores del entorno influyen en su actividad física, entendiendo su comportamiento como una forma de interacción con el espacio.

## Cualidades 
Se consideran como cualidades relevantes:
nivel de actividad del animal
variación del movimiento
respuesta a estímulos del entorno
Estas cualidades permiten traducir el comportamiento en datos, facilitando su análisis y visualización.

## Cualidad medida para esta entrega
Para esta entrega se midió específicamente el  , entendido como la intensidad del movimiento del conejo en intervalos de tiempo determinados.
La medición se realizó mediante el uso del acelerómetro de un dispositivo móvil, registrando variaciones en el movimiento del entorno cercano al animal. Posteriormente, estos valores fueron normalizados en una escala de 0 a 100 para su organización en la base de datos.

## Metodología y recolección de datos
Para facilitar la proximidad del animal al dispositivo de medición y generar variaciones en la actividad, se utilizó un estímulo alimenticio (plátano), permitiendo inducir comportamientos observables en el entorno inmediato del sensor.
Los datos fueron registrados mediante la aplicación Sensor Logger, específicamente utilizando el sensor de acelerómetro. El dispositivo fue ubicado en una superficie cercana al animal, manteniéndose fijo durante el proceso de registro para asegurar la consistencia de las mediciones.

## Consideraciones para la visualización
La visualización de los datos busca representar las variaciones en la actividad, explorando cómo el movimiento puede traducirse en elementos visuales como forma o intensidad. Se consideran decisiones compositivas como el uso de variaciones en densidad, en coherencia con los cambios registrados.
De este modo, la visualización no solo representa los datos, sino que permite observar patrones de comportamiento y generar una nueva lectura del fenómeno registrado.


# codigo processing 
 
// Visualización de actividad de un conejo
// Datos obtenidos desde Sensor Logger (acelerómetro)
// Normalizados a escala 0–100

int[] actividad = {2, 3, 2, 2, 1, 2, 2, 2, 1, 5};
int index = 0;

void setup() {
  size(800, 400);
  background(0, 0, 150); // azul
  frameRate(2);
}

void draw() {
  background(0, 0, 150, 40); // azul con transparencia (rastro)

  int valor = actividad[index];

  // tamaño según actividad
  float tam = map(valor, 0, 100, 20, 300);

  float x = random(width);
  float y = random(height);

  // color blanco
  fill(255);
  
  // borde negro
  stroke(0);
  strokeWeight(2);

  ellipse(x, y, tam, tam);

  index++;
  if (index >= actividad.length) {
    index = 0;
  }
}

