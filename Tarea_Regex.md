## 1. Genere una expresión regular que sea capaz de detectar las placas de un vehículo particular guatemalteco.

    No_placa <- c('P123ABC','P324CVB','PAV001EFT','P742TVG','P238BG', 'U012YTX','LPR2310VTP','PQR564RYP', 'P387VPN','P893QRM')

    str_extract(No_placa, '^[P]{1}[0-9]{3}(?![AEIOUÑ])[A-Z]{3}$')

    ##  [1] NA        "P324CVB" NA        "P742TVG" NA        NA        NA       
    ##  [8] NA        "P387VPN" "P893QRM"

## 2. Genere una expresión regular que valide si un archivo es de tipo .pdf o jpg. Ejemplo1.pdf, prueba2.PDF, respuestas\_del\_examen.jpg, amor.JPG

    documento <- c('doc1.JPG', 'doc2.PDF', 'doc3.jpg', 'doc4.pdf')
    str_extract(documento,'[.](JPG|PDF|jpg|pdf)$')

    ## [1] ".JPG" ".PDF" ".jpg" ".pdf"

\#\#3. Genere una expresión regular para validar contraseñas de correo.
Una contraseña de correo debe contener por lo menos 8 caracteres, una
letra mayúscula y un carácter especial.

    Password <- c('cLave.123','snap.23','Ufm.2019','Facebook009','Instagram_1')
    str_extract(Password, '^(?=.*[A-Z])(?=.*[a-z])(?=.*[&%@!$*.-_?])[A-Za-z\\d&%@!$*.-_?]{8,}$')

    ## [1] "cLave.123"   NA            "Ufm.2019"    "Facebook009" "Instagram_1"

## 4. Cree una expresión regular para validar un numero de carnet de la Universidad Galileo, por ejemplo 19002324 donde los primeros dos dígitos representan el año en el que el alumno se inscribió los cuales pueden variar desde el 01 (año 2001) hasta el 30 (año 2030). Los siguientes dos dígitos son cero (00) los cuales van por default y los últimos cuatro dígitos son un número que va desde el 1110 hasta el 8970. Para dar su respuesta utilice la notación de expresiones regulares.

    no_carnet<-c(19002324,2002324, 30001990,33221567,14002340)
    str_extract(no_carnet,'^[0-30]\\d{2}[00][1110-8970]{4}')

    ## [1] "19002324" NA         "30001990" NA         "14002340"

\#\#5. Cree una expresión regular que encuentre todas las palabras de la
primera línea, pero ninguna de la segunda. \#\#a. pit, spot, spate, slap
two, respite \#\#b. pt,Pot,peat,part

    palabras_clave <-   c('pit', 'spot', 'spate', 'slap two', 'respite','pt','Pot','peat','part')
    str_extract(palabras_clave,'.*p.t.*')

    ## [1] "pit"      "spot"     "spate"    "slap two" "respite"  NA         NA        
    ## [8] NA         NA

\#\#6. Cree una expresión regular para obtener los números telefónicos
de Guatemala. Estos pueden contener al inicio +502 o 502, pueden estar
separados por un espacio en blanco o un guión o juntos. Notar que los
números telefónicos pueden empezar únicamente con 4,5,6 o 2.

    numeros <-  c('+50254821151', '4210-7640', '52018150', '2434 6854', '11234569', '50211234578')

    str_extract(numeros,'^[+]?[5][0][2][-|\\s]?[4,5,2,6]{1}[1-9]{3}[-|\\s]?[1-9]{4}')

    ## [1] "+50254821151" NA             NA             NA             NA            
    ## [6] NA

#### 7. Genere una expresión regular que sea capaz de obtener correos de la UFM.

    mail <- c('luisamayoa@ufm.edu', 'luis.javiersamayoa@gmail.com', 'pedrogarcia@ufm.edu', 'parkerjuana@ufm.edu', 'carlos.22@yahoo.com')
    str_extract(mail, '.*@[ufm]+.(edu)$')

    ## [1] "luisamayoa@ufm.edu"  NA                    "pedrogarcia@ufm.edu"
    ## [4] "parkerjuana@ufm.edu" NA

\#\#8. En el mundo distópico de Eurasia, Big Brother le asigna un
identificador único a cada ciudadano. Genere una expresión regular que
valide las identificaciones. Composición del id: \#\#\#a. El id inicia
con 0 a 3 letras minúsculas (puede tener 0 letras minúsculas hasta tres
letras minúsculas) \#\#\#b. Luego es seguido por una cadena de dígitos
que puede ser de 2 a 9 dígitos respectivamente. \#\#\#c. Inmediatamente
después de la cadena de dígitos, se encuentra por lo menos tres letras
mayúsculas. \#\#\#d. Ej: abc012333ABCDEEEE

    id <- c('abc012333ABCDEEEE', 'Rt6789gggh', 'cfg34567JKL', 'utjgn45TTT')
    str_extract(id,'^[a-z]{0,3}[0-9]{2,9}[A-Z]{2,}$')

    ## [1] "abc012333ABCDEEEE" NA                  "cfg34567JKL"      
    ## [4] NA
