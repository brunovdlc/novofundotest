<html>
  <head>
 
    <title>pg</title>

<!-- Alinhamento e formatacao letras + Data -->
    <link href="https://fonts.googleapis.com/css2?family=Shadows+Into+Light&amp;display=swap" rel="stylesheet">
<!-- Particulas interativas +- estrelas -->
    <script src="https://cdn.jsdelivr.net/npm/particles.js@2.0.0/particles.min.js"></script>

<!-- Style geral -->
    <style>
    
      body {
      background:url(https://i.imgur.com/qYuHVmd.png) #000010;
      background-size:cover;
      color:#fff;
      font-size: 16px;
      }
      #particles-js{ position:fixed; left: 0%; 
      top: 0%; width: 100%; height: 100%; .js-count-particles{-webkit-user-select: none; margin-top: 5px; margin-left: 5px; } #stats{ border-radius: 3px 3px 0 0; overflow: hidden; } .count-particles{ border-radius: 0 0 3px 3px; }}  
      svg {
      position: relative;
      top: 0px; left: 0px;
      }
      .text-copy {
      font: 60px Righteous; 
      fill: none;
      stroke: white;
      stroke-dasharray: 20% 90%;
      stroke-width: 2px;
      stroke-dashoffset: 20%;
      animation: stroke-offset 15.5s infinite linear;
      }
      .text-copy:nth-child(1){
      stroke: #fff600;
      animation-delay: -1;
      }
      .text-copy:nth-child(2){
      stroke: #ff0000;
      animation-delay: -2s;
      }
      .text-copy:nth-child(3){
      stroke: #00ff12;
      animation-delay: -3s;
      }
      .text-copy:nth-child(4){
      stroke: #0048ff;
      animation-delay: -4s;
      }
      .text-copy:nth-child(5){
      stroke: #ffffff;
      animation-delay: -5s;
      }
      @keyframes stroke-offset{
      100% {stroke-dashoffset: -35%;}
      }
      .bchat { 
      position: absolute; 
      left: 50%; 
      top: 38%; 
      margin-top: 71px; 
      transform: translate(-50%, -50%); 
      width: 52vw; 
      height: 96vh; 
      padding: 20px; 
      text-align: center; 
      background-color: rgba(0, 0, 0, 0.5); 
      } 
      .wrap{
      width: 60%;
      max-width: 1000px;
      /*margin:auto;*/
      }
      .widget{
      width: 40%;
      margin: 6.5em;
      /*margin:32px;*/
      }
      .widget p{
      display: inline-block;
      line-height: .1em;
      }
      .fecha{
      position: relative;
      top: 50px; left: 1115px;
      font-family: Shadows Into Light, Arial;
      text-align: center;
      font-size: 0.9em;
      margin-bottom: 0rem;
      /*margin-bottom: 5px;*/
      background: rgba(0,0,0,0.5);
      padding: -54px;
      height: 0px;
      width: 150px;
      }
      .reloj{
      position: relative;
      top: 0px; left: 1100px;
      font-family: Shadows Into Light, Arial;
      width:50%;
      height: 64px;
      padding: 1px;
      font-size: 2.0em;
      text-align: center;
      background: rgba(0,0,0,0);
      }
      .reloj .caja-segundos {
      display: inline-block;
      }
      .reloj .segundos,
      .reloj .ampm  {
      position: relative;
      top: 13px;
      font-size: 1.3rem;
      display: block;
      } 
    </style>
  </head>


  <body>
<!-- Particulas interativas +- estrelas -->
    <div id="particles-js">
      <canvas class="particles-js-canvas-el" width="400" height="822" style="width: 100%; height: 100%;"></canvas>
    </div> 

<!-- Data + Hora-->
    <div class="wrap">
      <div class="widget">
        <div class="fecha">
          <p id="diaSemana" class="diaSemana"></p>
          <p id="dia" class="dia"></p>
          <p></p>
          <p id="mes" class="mes"></p>
          <p></p>
          <p id="year" class="year"></p>
          <p></p>
          <p id="year" class="year"></p>
        </div>
        <div class="reloj">
          <p id="horas" class="horas"></p>
          <p>🅼</p>
          <p id="minutos" class="minutos"></p>
          <p>🅸</p>
          <p id="minutos" class="minutos"></p>
          <p>🆇</p>
          <div class="caja-segundos">
            <p id="ampm" class="ampm"></p>
            <p id="segundos" class="segundos"></p>
          </div>
        </div>
      </div>
    </div>
    <div class="">
    </div>

<!-- Logo -->
<style>audio::-webkit-media-controls-timeline { display:none;}</style>
<audio autoplay controls="controls" src="http://stream2.painel-stm.com:10016/;"></audio>
<!-- Horario + Data -->
	
    <script>
      (function(){
        
      	var actualizarHora = function(){
      
      		var fecha = new Date(),
      			horas = fecha.getHours(),
      			ampm,
      			minutos = fecha.getMinutes(),
      			segundos = fecha.getSeconds(),
      			diaSemana = fecha.getDay(),
      			dia = fecha.getDate(),
      			mes = fecha.getMonth(),
      			year = fecha.getFullYear();
      
      		var pHoras = document.getElementById('horas'),
      			pAMPM = document.getElementById('ampm'),
      			pMinutos = document.getElementById('minutos'),
      			pSegundos = document.getElementById('segundos'),
      			pDiaSemana = document.getElementById('diaSemana'),
      			pDia = document.getElementById('dia'),
      			pMes = document.getElementById('mes'),
      			pYear = document.getElementById('year');
      
      		
      
      		var semana = ['Domingo', 'Segunda', 'Terça', 'Quarta', 'Quinta', 'Sexta', 'Sabado'];
      		pDiaSemana.textContent = semana[diaSemana];
      
      
      		pDia.textContent = dia;
      
      		var meses = ['Janeiro', 'Fevereiro', 'Março', 'Abril', 'Maio', 'Junho', 'Julho', 'Agosto', 'Setembro', 'Outobro', 'Novembro', 'Desembro'];
      		pMes.textContent = meses[mes];
      		pYear.textContent = year;
      
      		if (horas >= 12) {
      			horas = horas - 12;
      			ampm = 'PM';
      		} else {
      			ampm = 'AM';
      		}
      
      		if (horas === 0 ){
      			horas = 12;
      		}
      
      		pHoras.textContent = horas;
      		pAMPM.textContent = ampm;
      
      		if (minutos < 10){ minutos = "0" + minutos; }
      		if (segundos < 10){ segundos = "0" + segundos; }
      
      		pMinutos.textContent = minutos;
      		pSegundos.textContent = segundos;
      	};
      
      	
        
          particlesJS("particles-js", {"particles":{"number":{"value":35,"density":{"enable":false,"value_area":800}},"color":{"value":"#ffffff"},"shape":{"type":"star","stroke":{"width":0,"color":"#000000"},"polygon":{"nb_sides":5},"image":{"src":"https://i.imgur.com/unEnzRH.png","width":100,"height":100}},"opacity":{"value":0.5,"random":false,"anim":{"enable":false,"speed":1,"opacity_min":0.1,"sync":false}},"size":{"value":4,"random":true,"anim":{"enable":false,"speed":40,"size_min":0.1,"sync":false}},"line_linked":{"enable":false,"distance":150,"color":"#ffffff","opacity":0.4,"width":1},"move":{"enable":true,"speed":3,"direction":"top-left","random":false,"straight":false,"out_mode":"out","bounce":false,"attract":{"enable":true,"rotateX":2164.606282168456,"rotateY":481.0236182596568}}},"interactivity":{"detect_on":"canvas","events":{"onhover":{"enable":false,"mode":"grab"},"onclick":{"enable":true,"mode":"repulse"},"resize":true},"modes":{"grab":{"distance":200,"line_linked":{"opacity":1}},"bubble":{"distance":400,"size":40,"duration":2,"opacity":8,"speed":3},"repulse":{"distance":200,"duration":0.4},"push":{"particles_nb":4},"remove":{"particles_nb":2}}},"retina_detect":true});var count_particles, stats, update; stats = new Stats; stats.setMode(0); stats.domElement.style.position = 'absolute'; stats.domElement.style.left = '0px'; stats.domElement.style.top = '0px'; document.body.appendChild(stats.domElement); count_particles = document.querySelector('.js-count-particles'); update = function() { stats.begin(); stats.end(); if (window.pJSDom[0].pJS.particles && window.pJSDom[0].pJS.particles.array) { count_particles.innerText = window.pJSDom[0].pJS.particles.array.length; } requestAnimationFrame(update); }; requestAnimationFrame(update);
        
      }());
      
    </script>
  </body>
</html>
