
  <h3 align="center">Vue.js Basic Notes For Me</h3>

  <p align="center">
    My notes about Vue.js
  </p>


## Notes


* {{ title }} değişkenler double curly braces arasında yazılır // string interpolation -> {{}}
* data : {
   title : "Merhaba Samet",
   description : "Açıklama"
   }, değişkenler data içerisinde tutulur
*  methods : {
       changeTitle : function(event){
       this.description = event.target.value; 
   }
   }  methodlar methods içerisinde tutulur
* <p>{{ hello() }}</p> curly braces içerisinde method çağırımı yapılabilir returnlenen değer basılır.
* Method içerisinde datalara erişim sağlamak için this keywordü kullanılır.
* V-bind ile attribute üzerine data aktarılabiliriz (method üzerinden de yapılabilir) örnek : v-bind:href="link" yada v-bind:href="linkGetir()" 
* Datalar çeşitli methodlar ile değiştirilirken bir datanın değişmemesi için ilgili elemente v-once keywordü yazılır  örnek   <p v-once>{{ title }}</p>
* Bir html kodu getirilmek istenirse v-html komutu kullanılır örneğin   <p v-html="blogLink"></p>  data ---> blogLink : "<a href='https://www.facebook.com'>Link</a>"
* Event dinlemek için v-on keywordü kullanılır. örnek  <button v-on:click="showAlert">Alert Göster</button>  eğer işlem tek satırlık ise js kodu yazılabilir örnek  <button v-on:click="değişken++">değişkeni arttır</button>
* Methodlara event objesi gönderilir bu obje attribute özelliklerini taşır. örneğin   <p v-on:mousemove="updateCoords">Koordinatlar :{{x}},{{y}}</p> event.clientX 
* Event objesine veri göndermek için method çağırılırken içeriye değişken yazılır örnek   <p v-on:mousemove="updateCoords(2,$event)">Koordinatlar :{{x}},{{y}}</p> hem veri hem event bu şekilde gönderilebilir.
* Eventler stop keywordu ile engellenebilir v-on:mousemove.stop
* Klavye eventleri örnekteki şekilde dinlenebilir  v-on:keyup.enter="showAlert2" v-on:keyup.enter.space="showAlert2"
* v-model keywordü ile event dinlemekden datalar birbirine bağlanabilir
  <input type="text" v-model="name">
  <p>{{ name}} </p>
  <h3>{{name}} </h3>  bu şekilde hiç method yazmadan name değiştikçe modele kaydedilir.
* Computed ile method arasındaki en büyük fark computed içerisindeki kodu analiz eder. Eğer değişiklik varsa DOM u günceller.
* Computed senkron çalışır
* Watch asenkron çalışır
* Watch bir datayı gözlemlemek için kullanılır. İçerisinde function yazılabilir. 
Örnek
watch : {
    counter : function(value){
        vm = this;
        setTimeout(function(){
          vm.counter= 0;
        },1500)
    }
   }
* V-on yerine @ v-bind yerine : kullanılır.
* V-if de if else ve else var v-show da yok.
* Elementin pasif olaram DOM üzerinde kalmasını istiyorsak v-show kullanmalıyız.
* Template elementi vue js ile gelir ve render edilmez
* V-bind:key (:key) kullanarak v-for kullanırsak vue js elementin sıra numarasını değil elementin kendisini tutuyor bu yüzden eklenti yapıldığı zaman elementin yerini değiştiriyor. Ram için daha performanslı