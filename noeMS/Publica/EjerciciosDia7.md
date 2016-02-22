2 - ¿Que fecha será dentro de 30 días?
```
    var ahora = new Date();
    console.log("Hoy es " + ahora.toLocaleString());
    ahora.setDate(ahora.getDate() + 30);
    console.log("En 30 días será " + ahora.toLocaleString());
```

3 - ¿Cuantas horas han pasado desde que emepezó este curso? y... ¿en días?
```
    var startCourse = new Date(Date.UTC(2016, 0, 27))
    console.info ("La fecha en la que empezó el curso es " + startCourse.toLocaleString());
    var today = new Date();
    console.info ("La fecha de hoy es " + today.toLocaleString());
    var time = today-startCourse
    var hours = Math.floor(time/(3600*1000))
    console.info ( "Han pasado " +  Math.floor(time/(3600*1000)) + " horas desde que empezamos las clases")
    console.info ( "O lo que es lo mismo " + Math.floor(hours/24) + " dias")
```

4 - ¿Cuantos milisengundos quean para terminar el curso? y... ¿en horas o días?
```
    var today = new Date();
    console.info ("La fecha de hoy es " + today.toLocaleString());
    var endCourse = new Date(Date.UTC(2016, 2, 16));
    var time = endCourse-today;
    console.info("Quedan " + time + " ms para que acabe el curso");
    var hours = Math.floor(time/(3600*1000));
    console.info ( "Lo que en horas son " +  Math.floor(time/(3600*1000)) + " horas y  " + Math.floor(hours/24) + " dias");
```

5 - ¿Que fecha será dentro de un año y 10 horas más?
```


```
6 - Imprimer por consola la fecha completa (formato texto) en koreano, japones.
```
    var today = new Date();
    console.info("La fecha en koreano es " + today.toLocaleString('ko-KO'));
    console.info("La fecha en japones es " + today.toLocaleString('ja-JA'));
```