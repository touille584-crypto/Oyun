<!DOCTYPE html>
<html lang="tr">
<head>
<meta charset="UTF-8">
<title>Furry Elma Toplama</title>
<style>
body{
    margin:0;
    background:#87CEEB;
    overflow:hidden;
    font-family:Arial;
}
#oyun{
    width:100vw;
    height:100vh;
    position:relative;
}
#oyuncu{
    width:60px;
    height:60px;
    background:orange;
    border-radius:50%;
    position:absolute;
    bottom:20px;
    left:50%;
    transform:translateX(-50%);
    text-align:center;
    line-height:60px;
    font-size:30px;
}
.elma{
    width:40px;
    height:40px;
    background:red;
    border-radius:50%;
    position:absolute;
}
#puan{
    position:absolute;
    top:10px;
    left:10px;
    font-size:24px;
    color:white;
}
</style>
</head>
<body>

<div id="oyun">
<div id="puan">Puan: 0</div>
<div id="oyuncu">🦊</div>
</div>

<script>
const oyuncu=document.getElementById("oyuncu");
const oyun=document.getElementById("oyun");
const puanYazi=document.getElementById("puan");

let x=window.innerWidth/2-30;
let puan=0;

document.addEventListener("keydown",e=>{
    if(e.key==="ArrowLeft") x-=20;
    if(e.key==="ArrowRight") x+=20;

    if(x<0)x=0;
    if(x>window.innerWidth-60)x=window.innerWidth-60;

    oyuncu.style.left=x+"px";
});

function elmaOlustur(){
    let elma=document.createElement("div");
    elma.className="elma";
    elma.style.left=Math.random()*(window.innerWidth-40)+"px";
    elma.style.top="-40px";
    oyun.appendChild(elma);

    let y=-40;

    let dus=setInterval(()=>{
        y+=5;
        elma.style.top=y+"px";

        let ex=elma.offsetLeft;
        let ey=elma.offsetTop;
        let ox=oyuncu.offsetLeft;
        let oy=oyuncu.offsetTop;

        if(
            ex<ox+60 &&
            ex+40>ox &&
            ey<oy+60 &&
            ey+40>oy
        ){
            puan++;
            puanYazi.textContent="Puan: "+puan;
            clearInterval(dus);
            elma.remove();
        }

        if(y>window.innerHeight){
            clearInterval(dus);
            elma.remove();
        }

    },20);
}

setInterval(elmaOlustur,1000);
</script>

</body>
</html>
