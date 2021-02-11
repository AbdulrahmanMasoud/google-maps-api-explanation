# Google Map Api
عشان تستخدم جوجل ماب لازم يبقا معاك سيكرت كي وده بتجيبه من `جوجل ماب اي بي اي`
وهو حاليا مش مجاني ف ممكن تبحث وتشوف ازاي تجيب كي تجرب بيه او تشتري من جوجل ماب
<a href="https://console.cloud.google.com/apis/credentials">من هنا</a>

ندخل بقا علي ازاي نظهر الخريطه اصلا في المتصفح عندنا 

اول حاجه هعملها هعمل صفحه `اتش تي ام ال`  عاديه خالص وهضيف فيها في الاخر خالص 

``` <script src="https://maps.googleapis.com/maps/api/js?key=API_KEY&callback=initMap" async></script> ```

هتلاحظ ان فيه حاجه اسمها

``API_KEY``

ده بقا انت هتضيف مكانه `الكي` اللي انت جيبته من جوجل 

و هتلاحظ حاجه كمان اسمها
``` javascrip
 callback=initMap 
 ```
 انا هعمل فانكشن بالاسم ده عشان الاسكريبت يستخدمها ف خليك فاكرها

##### تمام اوي كده انا ظبط الصفحه بتاعتي ابدأ بقا اعرف ازاي اعرض الخريطه عندي ف الصفحه

اولا هحتاك ان انا اعمل ديف واديله اي دي اسمه ماب 

``` html
<div id="map"></div>
```
و ادي للديف ارتفاع عشان يظهر
``` css
#map { height: 70%;}
```
تمام جدا ابدأ بقا احط كود الجافاسكريبت اللي هجيبه من جوجل عشان يعرضلي الخريطه عندي

``` javascript
function initMap() {
          map = new google.maps.Map(document.getElementById("map"), { /
            center: { lat: 29.943453969087464, lng: 31.326295631528204 },
            zoom: 8,  
          });
        }
```
هنا انا عمل داله جديده بنفس اسم الكول باك اللي موجود في الاسكريبت اللي استدعيته ف الاول خالص

طيب تمام جيت بقا بعد ما عملت الداله ضيفت فيها اوبجكت جديد خاص بخرائط جوجل

``` js
new google.maps.Map(//المكان اللي هتعرض فيه الخريطه , settings)
```

وده بياخد حاجتين المكان اللي هعرض فيه الخريطه و الاعدادات بتاعه الخريطه

طيب احنا عرفنا المكان اللي هنضيف فيه الخريطه اللي هو 

``<div id='map'></div>``

طيب تعالا نشوف بقا الاعدادات

``` js
center: { lat: 29.943453969087464, lng: 31.326295631528204 },
```
ده انا بحددله المكان اللي الخريطه هتفتح عليه طيب بحدده ازاي عن` طريق خطوط الطول` و `خطوط العرض` 

طيب و 

```js
zoom:8
```
دي انا بحددله الخريطه هتبقا عامله زوم بنسبه كام

طيب تمام جدا لحد كده كده عرفنا ازاي نعرض الخريطه عندنا في الاخر هيظهر عندنا نفس الصفحه دي

``` html css js

<!DOCTYPE html>
<html>
<head>
    <title>Google Map Apis</title>
    <style> #map {height: 70%;}</style>
</head>
<body>

    <div id="map"></div>

    <script>
        function initMap() {
          map = new google.maps.Map(document.getElementById("map"), {
            center: { lat: 29.943453969087464, lng: 31.326295631528204 },
            zoom: 8, 
          });
        }
      </script>
     
<script src="https://maps.googleapis.com/maps/api/js?key=AIzaSyD_37gmGg4dOwESmxBtmdCPpYTlHomYneU&callback=initMap&libraries=&v=weekly" async></script>
</body>
</html>
```
-----------------

## ندخل بقا علي ازاي نحط ماركر علي الخريطه زي ده
<br><br>
<img src="https://cdn0.iconfinder.com/data/icons/small-n-flat/24/678111-map-marker-512.png" width="70px">

اول حاجه هنعرف اوبجكت جديد تبع خرائط جوجل اسمه
``` js
new google.maps.Marker({//بياخد الاعدادات بتاعته})
```
اول حاجه بياخدها 

``` js
 position: { lat: 29.943453969087464, lng: 31.326295631528204 }
```
وده الماكن اللي هيقا فيه الماركر بناء علي خطوط الطول و خطوط العرض

تاني حاجه 

``` js
map = map 
```
 دي اللي انا معرفها في الاوبجكت بتاع اللي بيظهر الخريطه ودي لازم تحطها عشان تعرفه انت هتحط الماركر علي اي خريطه

ثالث حاجه ممكن تضيفها 

``` js
title : "This Title"
```
وده بيظهر اول اما انت تروح علي الماركر بالموس

رابع حاجه ممكن تضيفها

``` js
icon: "http://simpleicon.com/wp-content/uploads/map-marker-5.png"
```
وده انت تقدر تغير شكل الماركر لاي صوره انت عايزها زي دي مثلا

خامس حاجه ممكن تضيفها

``` js
draggable: true,
```
ودي عشان تقدر تحرك الماركر بتاعك علي اي مكان في الخريطه

وطبعا فيه حاجات تانيه كتييره انت ممكن تبقا تلقي نظره هنا

<a href="https://developers.google.com/maps/documentation/javascript/examples/marker-labels">Google Map Markers</a>

المثال في الاخر هيبقا بالشكل ده

``` html css js
<!DOCTYPE html>
<html lang="en">
<head>
    <title>Google Map Apis</title>
    <style>#map {height: 70%;}</style>
</head>
<body>
    <div id="map"></div>
    <script>
        function initMap() {
          map = new google.maps.Map(document.getElementById("map"), {
            center: { lat: 29.943453969087464, lng: 31.326295631528204 },
            zoom: 8, 
          });

          new google.maps.Marker({
          position: { lat: 29.943453969087464, lng: 31.326295631528204 }, 
          map, 
          title: "Hello World!",
        });
        }
      </script>

    <script
      src="https://maps.googleapis.com/maps/api/js?key=AIzaSyD_37gmGg4dOwESmxBtmdCPpYTlHomYneU&callback=initMap&libraries=&v=weekly"
      async
    ></script>
</body>
</html>

```

----------------
## تمام لحد كده تعالا بقا نعرف ازاي نظهر اي بيانات لما اضغط علي الماركر
زي كده

<img src="https://duncan99.files.wordpress.com/2011/10/google-maps-api-v3-lesson-1_1317734507450.png" width="500px">

Coming Soon ......

