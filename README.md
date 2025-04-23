material del curso de webflux udemy pragma: https://www.udemy.com/certificate/UC-454143b4-5f8b-4720-b793-0886b0dc5ce5/

Seccion 5: API RESTFUL usando RestController https://github.com/saigon32/spring-boot-webflux-apirest

listar productos: curl --location 'http://localhost:8080/api/productos'
listar un producto: curl --location 'http://localhost:8080/api/productos/<id>'
crear: curl --location 'http://localhost:8080/api/productos' \
--header 'Content-Type: application/json' \
--data '{
    "nombre": "TV Samsung LED 55",
    "precio": 1000,
    "categoria": {
        "id": "6809545a0afcda0343de8f94",
        "nombre": "Electronico"
    }
}'

crear validando campos:
curl --location 'http://localhost:8080/api/productos' \
--header 'Content-Type: application/json' \
--data '{
  "nombre" : "impresora HP",
   "precio" : "1000",
   "categoria": {
      "id": "680963ef0f9f272875b912d7",
      "nombre": "Computacion"
   }  
}'

upload: curl --location 'http://localhost:8080/api/productos/upload/680961f06beeae165e58f092' \
--form 'file=@"/C:/Users/andres.jurado_pragma/Desktop/pngtree-led-tv-television-screen-vector-png-image_6673700.png"'

upload v2:
curl --location 'http://localhost:8080/api/productos/v2' \
--form 'file=@"/C:/Users/andres.jurado_pragma/Desktop/pngtree-led-tv-television-screen-vector-png-image_6673700.png"' \
--form 'nombre="televisor bonito"' \
--form 'precio="1000"' \
--form 'categoria.id="680961f06beeae165e58f08e"' \
--form 'categoria.nombre="Electronico"'

actualizar:
curl --location --request PUT 'http://localhost:8080/api/productos/680957290f87e262e13a4907' \
--header 'Content-Type: application/json' \
--data ' {
        "nombre": "Asus Camara HD Digital",
        "precio": 3000,
        "categoria": {
            "id": "680957290f87e262e13a4904",
            "nombre": "Computacion"
        }
}'

eliminar:
curl --location --request DELETE 'http://localhost:8080/api/productos/68095cbd5a490408e874158f' \
--header 'Content-Type: application/json' \
--data ' {
        "nombre": "Asus Camara HD Digital",
        "precio": 3000,
        "categoria": {
            "id": "680957290f87e262e13a4904",
            "nombre": "Computacion"
        }
}'
