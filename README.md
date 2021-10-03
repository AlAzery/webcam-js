# webcam-js

<p>buat structur html nya seperti ini </p>

````html
   <h1>webcam js</h1>
        <div>
        <video autoplay="true" id="video-webcam" style="width:100%;">
        Browsermu tidak mendukung, kentang ya
        </video>
        </div>
````

<h3> buat file javascript nya pasteka kode ini</h3>

````javascript
    
    var video = document.querySelector("#video-webcam"); 
            navigator.getUserMedia = navigator.getUserMedia || navigator.webkitGetUserMedia || navigator.mozGetUserMedia || navigator.msGetUserMedia || navigator.oGetUserMedia; 
            if (navigator.getUserMedia) { 
                navigator.getUserMedia({
                    video: true }, 
                    handleVideo, videoError);
                    }
                    function handleVideo(stream) { 
                        video.srcObject = stream;
                        } 
                        function videoError(e) {
                            alert("Izinkan menggunakan kamera anda ")
                            };
    
````

<h1> Mengambil foto dengan javascript</h1>

````html
     <button onclick="ambilFoto()">Ambil Gambar</button>
````

<p>tambahkan function javascript button ambilFoto()</p>

````javascript
    
    function ambilFoto(){ 
                // buat elemen img/jpg 
                var img = document.createElement('img');
                var context;
                // buat ukuranvideo 
                var width = video.offsetWidth , height = video.offsetHeight;
                // buat elemen canvas 
                canvas = document.createElement('canvas'); canvas.width = width; canvas.height = height; 
                // ambil gambar dari video dan masukan
                // ke dalam canvas 
                context = canvas.getContext('2d'); context.drawImage(video, 0, 0, width, height); 
                // render hasil dari canvas ke elemen img 
                img.src = canvas.toDataURL('image/png'); document.body.appendChild(img); 
                
            }

````

##dan selamat anda telah membuat 1 kamera sederhana dengan javascript