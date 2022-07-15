# ✈️ Sistema de geolocalización en tiempo real bus aeropuerto de la Región de Murcia.

## Contexto
La consejeria de Fomento de la Comunidad Autónoma de la Región de Murcia habilitó el día 15 de junio de 2022 una linea de autobús que comunica las dos principales ciudades de la región (Murcia y Cartagena) con al Aeropuerto Internacional.

Además, como novedad se ha habilitado un sistema de geolocalización del autobus para saber cuanto le quedaŕa para llegar.

El servicio es operado por Interbus y de momento está confirmada su continuidad hasta el 16 de Septiembre de 2022.

En la misma web de Interbus se podía consultar la posición en tiempo real, aunque el visionado de la misma no es muy comodo, al menos a mi parecer.

De ahi mi motivación de crear mi propia versión con algunas mejoras.

## Funcionamiento
La pagina web se refresca cada 5 segundos con la ubicación del autobus, además si lo desea se puede mostrar la estela del recorrido que va haciendo el autobus.

![Funcionamiento](./docs/images/estela.gif)



## ¿Como lo he hecho?
Se trata de una webapp desarrollada en Nuxt.js y Vue, utilizando OpenStreetMap (Leaflet) para los mapas.

La app consulta frecuentemente a una API donde se puede consumir las coordenadas del bus en tiempo real. Esta API pertenece a la empresa Interbus.

## Creditos
- [Web oficial de las lineas del Aeropuerto (Interbus)](https://www.interbusmurcia.es/servicio-aeropuerto/)

## License
MIT License

Copyright (c) [2022] [Enrique Rodirguez Lopez]

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


