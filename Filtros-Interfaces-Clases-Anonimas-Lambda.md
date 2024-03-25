# Filtros:
Creamos una clase llamada Filtro1:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/6ae1ed70-f110-48a5-9571-fbbc05504345)

Luego implementamos el método correspondiente `doFilter` para poder arreglar el error:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/bd821a18-bf5f-4f04-a330-043912c78895)

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/10b6731a-6b44-4548-b8f2-d884f18e8046)

Como doFilter no cuenta con HttpServletRequest, debemos castear al momento de validar la sesion:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/7264e8eb-0460-4008-8c06-ec9ec4c5fd28)

Ahora ya podemos proceder a armar nuestra validación:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/e9800bda-ed3b-4740-b932-dd338d001d5b)


Filter Chain hace que pasemos a la siguiente validación si es que hubiese una:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/24432822-ede9-49e1-8487-01b0a9625252)

Y ya una vez pasando las validaciones, tener que mandarlo al servlet correspondiente:

Agregamos @WebFilter(...) en nuestra clase Filtro1. Cabe resaltar que HttpSession igual se usara en los Servlets, ya sea para obtener o definir atributos:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/368180ea-f6cd-4b9c-9532-c4ef565bffd4)

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/472ada37-77fe-45a2-b1e2-57f70e4b0ce1)

Si tenemos varios filtros, como clases Filtro1.java, Filtro2.java, ... , el orden de los filtros en ejecutarse sera por orden alfabético

---------------------------------------------------------------

# Interfaces: 
Por ejemplo, todos deben pagar ciertas cosas, pero cada uno, cada persona lo puede pagar de diferente forma, via banca movil, web o de manera presencial.
Creo un metodo de pago como interfaz

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/4da28f64-b183-4a61-8408-a095b4e068d2)

En sus metodos no es necesario escribir `public void`, basta con `void`, ya que en una interfaz todos los métodos son abstractos y públicos, no les puede poner ni privado, ni protectec, ni default

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/de10d1f5-2ad7-4e5b-973a-8da87648286e)

Para que cada estudiante pague de forma distinta agregamos la funcion recibeMetodoPago: 

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/bfd91d5c-58dd-4126-8553-53ae3b1481e9)

Ahora solucionaremos este error, el cual ocurre ya que no es posible instanciar una interfaz

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/f6dab267-07ce-4f7b-af46-b4c3b4caf162)

Creamos una clase Intermedia y al ponerle implements, estamos diciendo que claseIntermedia es un método de pago, entonces, llamamos a la funcion recibeMetodoPago del estudiante, la cual esta definida como que recibirá un método de pago:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/b4d28a9e-769b-4e64-9d7d-647421df5055)

---------------------------------------------

# Clases Anónimas:
Son clases que se crean y se usan una única vez.
Ponemos como clase abstracta a Persona:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/842610d5-8df8-4721-8d25-4bcda962a82f)

Creamos una instancia anonima(A pesar de Persona ser abstracta, una instancia de una clase anónima que herede de esta(extends), si puede ser creada):

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/74f574ac-6873-48fb-8ade-be7a765c8d57)

De la misma manera y con el mismo concepto es que se puede crear una clase anonima de las interfaces, como lo es MetodoDePago:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/574e513b-4400-4f8b-9e01-6360253a4599)

Para resumir codigo(tipo JS):

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/9a2ec87b-e78b-43ab-999f-c20be77e6fd4)

E incluso se puede reducir mas el codigo, colocando de frente lo que hará el método, esto es gracias a que es una clase de tipo LAMBDA, que tiene un solo método: 

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/583ec819-d002-4ef9-9ec2-f1175bf613b4)


## OJO: 
Cuando la interfaz tiene un solo método(una sola función) se le llama interfaz funcional o `LAMBDA` 

Tambien podemos añadir parametros a la método de la interfaz:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/c4092361-5db3-4984-a93a-03bf56363a45)

O añadir mas sout:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/b71b1272-67e8-4640-b190-adf05bea8066)

------------------------------
Agregamos una nueva interfaz, reccordar que en LAMBDA el return es implicito si no usamos llaves{}:

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/56aa76dd-6e1c-4876-8a8d-744d7f8ee1ef)


![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/073c95ec-ae23-49d8-b4ba-8131b6569324)

![image](https://github.com/Pierohc/Filtros-Interfaces-Clases-Anonimas-Lambda/assets/133154904/560e14b2-7dc9-4e08-9091-3e686d46ef50)












