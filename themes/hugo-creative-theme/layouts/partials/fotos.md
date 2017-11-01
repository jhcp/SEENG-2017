<style>

.trs {-webkit-transition:all ease-out 0.5s;
    -moz-transition:all ease-out 0.5s;
    -o-transition:all ease-out 0.5s;
    -ms-transition:all ease-out 0.5s;
    transition:all ease-out 0.5s;}  
#slider {position: relative; z-index: 1;}
#slider a { position: absolute; top: 0; left: 0; opacity: 0;filter:alpha(opacity=0);}
.ativo {opacity: 1!important; filter:alpha(opacity=100)!important;}

/*controladores*/

.next, .prev {background: #56CD95; cursor: pointer; opacity: 0;filter:alpha(opacity=0); position: absolute; bottom: 40%; width: 43px; height: 43px; z-index: 5;}

.next {right: 10px;}
.next:before,.next:after {left: 21px;}
.next:before {
    -webkit-transform: rotate(-42deg);
    top: 5px;
}
.next:after {
    -webkit-transform: rotate(-132deg);
    top: 19px;
}
.next:before,.next:after,.prev:before,.prev:after {content: "";
    height: 20px;
    background: #fff;
    width: 1px;
    position: absolute;
}
.prev {left: 10px;}
.prev:before,.prev:after {left: 18px;}
.prev:before {
    -webkit-transform: rotate(42deg);
    top: 5px;
}
.prev:after {
    -webkit-transform: rotate(132deg);
    top: 19px;
}

figure:hover span {opacity: 0.76;filter:alpha(opacity=76);}
figure {
    max-width: 937px;
    height: 554px;
    position: relative;
    overflow: hidden;
//    margin: 50px auto;
}

figcaption {padding-left: 20px;color: #fff; font-family: "Kaushan Script","Lato","arial"; font-size: 18px; background: #56CD95; width: 100%; position: absolute; bottom: 0; left: 0; line-height: 55px; height: 55px; z-index: 5}

</style>

<section id="registration" class="no-padding">
<div class="container">
    <div class="row">
        <div class="col-lg-12 text-center">
            <h2 class="section-heading">Obrigado!</h2>
            <hr class="primary">
        </div>
    </div>
</div>

<div class="container-fluid">
    <div class="row">
      <div class="col-lg-8 col-lg-offset-2 text-center">
<figure>
   <span class="trs next"></span>
   <span class="trs prev"></span>

   <div id="slider">
      <a href="img/fotos/1.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/1.jpg" alt="Foi um prazer tê-lo conosco! Já estamos lhe esperando de volta em 2018..." /></a>
      <a href="img/fotos/2.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/2.jpg" alt="Auditório cheio para a abertura!" /></a>
      <a href="img/fotos/3.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/3.jpg" alt="A abertura da III SEENG" /></a>
      <a href="img/fotos/4.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/4.jpg" alt="Primeira palestra" /></a>
      <a href="img/fotos/6.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/6.jpg" alt="Outra palestra" /></a>
      <a href="img/fotos/7.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/7.jpg" alt="Mais palestra" /></a>
      <a href="img/fotos/8.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/8.jpg" alt="Mais uma..." /></a>
      <a href="img/fotos/9.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/9.jpg" alt="Foram 15 palestras e 9 minicursos ao todo" /></a>
      <a href="img/fotos/10.jpg" class="trs"><img width="100%" src="img/fotos/thumbs/10.jpg" alt="Encerramento da III SEENG, com o Coral da UFRPE" /></a>
      <a href="#" class="trs"><img width="100%" src="img/fotos/thumbs/11.jpg" alt="Os monitores! (foram 40...)" /></a>
   </div>

   <figcaption></figcaption>
</figure>

<a href="img/fotos/fotos.zip">baixar as fotos</a><br /><br />
<script type="text/javascript">
function setaImagem(){
    var settings = {
        primeiraImg: function(){
            elemento = document.querySelector("#slider a:first-child");
            elemento.classList.add("ativo");
            this.legenda(elemento);
        },

        slide: function(){
            elemento = document.querySelector(".ativo");

            if(elemento.nextElementSibling){
                elemento.nextElementSibling.classList.add("ativo");
                settings.legenda(elemento.nextElementSibling);
                elemento.classList.remove("ativo");
            }else{
                elemento.classList.remove("ativo");
                settings.primeiraImg();
            }

        },

        proximo: function(){
            clearInterval(intervalo);
            elemento = document.querySelector(".ativo");

            if(elemento.nextElementSibling){
                elemento.nextElementSibling.classList.add("ativo");
                settings.legenda(elemento.nextElementSibling);
                elemento.classList.remove("ativo");
            }else{
                elemento.classList.remove("ativo");
                settings.primeiraImg();
            }
            intervalo = setInterval(settings.slide,4000);
        },

        anterior: function(){
            clearInterval(intervalo);
            elemento = document.querySelector(".ativo");

            if(elemento.previousElementSibling){
                elemento.previousElementSibling.classList.add("ativo");
                settings.legenda(elemento.previousElementSibling);
                elemento.classList.remove("ativo");
            }else{
                elemento.classList.remove("ativo");                     
                elemento = document.querySelector("#slider a:last-child");
                elemento.classList.add("ativo");
                this.legenda(elemento);
            }
            intervalo = setInterval(settings.slide,4000);
        },

        legenda: function(obj){
            var legenda = obj.querySelector("img").getAttribute("alt");
            var link = obj.getAttribute("href");
            obj.onclick="window.location = '" + link + "'";
            document.querySelector("figcaption").innerHTML = legenda;
        }

    }

    //chama o slide
    settings.primeiraImg();

    //chama a legenda
    settings.legenda(elemento);

    //chama o slide à um determinado tempo
    var intervalo = setInterval(settings.slide,4000);
    document.querySelector(".next").addEventListener("click",settings.proximo,false);
    document.querySelector(".prev").addEventListener("click",settings.anterior,false);
}

window.addEventListener("load",setaImagem,false);
</script>





  </div>
  </div>
</div>

</section>
