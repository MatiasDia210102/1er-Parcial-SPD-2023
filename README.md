# 1er-Parcial-SPD-2023

# SPD-Dojo-2
## Integrantes
- Mateo Ciotti
- Matias Díaz
- Franco Beltrán

## Proyecto

<img src="https://github.com/MatiasDia210102/1er-Parcial-SPD-2023/blob/42f527afa33eb8bfd08b1c8172cfdda163ede0b7/Imagenes/1er%20Parcial%20SPD%202023.png?raw=true" width="800"/>

## Descrpcion
AL presionar los botones el montacargas pasara por cada piso o frenara, encendiendo su respectivo led y marcandolo en el display

## Defines Y Funciones

~~~/*C++ code
  Matias Diaz DIV J TT
  Dojo 2
*/

#define LEDROJO 10 
#define LEDVERDE 9
#define B 8
#define A 7
#define F 6
#define G 5
#define E 4
#define D 3
#define C 2

#define BOTONPARA A0
#define BOTOBAJA A1
#define BOTONSUBE A2

void validar_estado_led(int led, char* mensaje);
void encender_apagar_led(int led, int led2);
void encender_digitos(int estado0, int estado1, int estado2, int estado3, int estado4, int estado5, int estado6);

void encender_display(int digito);
void imprimir_mensaje(char* mensaje, int contador);

void validar_estado_montacargas(char* mensaje, int contador, int led_high, int led_low);
int recorrer_pisos(char* mensaje, char* condicion, int contador, int numero, int led_high, int led_low);

void ejecutar_programa(int estado_boton);
int sumar_o_restar(char* condicion, int contador, int numero);

int contador = 0;
int estado_boton = 0;
int paro;

## Principal
void setup()
{
  for(int i = 2; i <= 10; i++){
    pinMode(i, OUTPUT);
  }
  pinMode(BOTONPARA, INPUT);
  pinMode(BOTOBAJA, INPUT_PULLUP);
  pinMode(BOTONSUBE, INPUT_PULLUP);
  Serial.begin(9600);
}

void loop()
{
  if(digitalRead(BOTONPARA) == HIGH){
    estado_boton = !estado_boton;
    delay(300);
  } 
  ejecutar_programa(estado_boton);
}


~~~

## Links
-[ThinkerCad](https://www.tinkercad.com/things/7rjLmqkCjsa-ejercicio-trenes/editel?sharecode=rhnHZ1HSNi45kLiAJaHVGWsPdo9eRsRYTNV-S7J5mjs)
