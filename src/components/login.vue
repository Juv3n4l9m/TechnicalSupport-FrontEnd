<template>
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login and Registtration form in HTML and CSS codehal</title>
    <link rel="stylesheet" href="style.css">
    <link href='https://cdn.boxicons.com/fonts/basic/boxicons.min.css' rel='stylesheet'>
</head>
<body>
    <div class="wrapper">
        <span class="bg-animate"></span>
        <span class="bg-animate2"></span>

        <div class="form-box login">
            <h2 class="animation" style="--i:0; --j:21;">Login</h2>
            <form action="#">
                <div class="input-box animation" style="--i:1; --j:22;">
                    <input type="text" required>
                    <label>Username</label>
                    <i class='bx  bxs-user'  ></i> 
                </div>
                <div class="input-box animation" style="--i:2;  --j:23;">
                    <input type="password" required>
                    <label>Password</label>
                    <i class='bx  bxs-lock'  ></i> 
                </div>
                <button type="submit" class="btn animation" style="--i:3; --j:24;">Login</button>
                <div class="logreg-link animation" style="--i:4;  --j:25;">
                    <p>Don't have an account <a href="#" class="register-link">Sign Up</a></p>
                </div>                
            </form>
        </div>
        <div class="info-text login">
            <h2 class="animation" style="--i:0;  --j:20;">Bienvenido!</h2>
            <p class="animation" style="--i:1;  --j:21;">Ingrese sus credenciales para usar todas las funciones del sitio.</p>
        </div>

        <div class="form-box register">
            <h2 class="animation" style="--i:17; --j:0;">Sign Up</h2>
            <form action="#">
                <div class="input-box animation" style="--i:18; --j:1;">
                    <input type="text" required>
                    <label>Username</label>
                    <i class='bx  bxs-user'  ></i> 
                </div>
                <div class="input-box animation" style="--i:19; --j:2;">
                    <input type="text" required>
                    <label>Email</label>
                    <i class='bxr  bxs-envelope'  ></i> 
                </div>
                <div class="input-box animation" style="--i:20; --j:3;">
                    <input type="password" required>
                    <label>Password</label>
                    <i class='bx  bxs-lock'  ></i> 
                </div>
                <button type="submit" class="btn animation" style="--i:21; --j:4;">Sign Up</button>
                <div class="logreg-link animation" style="--i:22; --j:5;">
                    <p>Already have an account? <a href="#" class="login-link">Login</a></p>
                </div>                
            </form>
        </div>
        <div class="info-text register">
            <h2 class="animation" style="--i:17; --j:0;">Hola</h2>
            <p class="animation" style="--i:18; --j:1;">Registrese con sus datos personales para usar todas las funciones del sitio.</p>
        </div>
    </div>
</body>
</template>

<script>
    const wrapper = document.querySelector('.wrapper');
    const registerLink = document.querySelector('.register-link');
    const loginLink = document.querySelector('.login-link');
    if(wrapper){
        registerLink.onclick = () =>{
            wrapper.classList.add('active');
        }
    }else{
        console.error('xxxxxxxx');
    }
    if(wrapper){
        loginLink.onclick = () =>{
            wrapper.classList.remove('active');
        }
    }
    else{
        console.error('yyyyyyyy');
    }
</script>

<style>
    *{
        margin: 0;/*margen: 0*/
        padding: 0;/*relleno: 0*/
        box-sizing: border-box;/*caja(cuadro)-dimencionamiento: border-cuadro*/
        /*font-family:'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;*/
        /*font-family:Arial, Helvetica, sans-serif;*/
        font-family:sans-serif;
    }
    body{
        display: flex; /*pantalla: flexible*/
        justify-content: center; /*justificacion-contenido*/
        align-items: center; /*aliniar-elementos: centro*/
        min-height: 100vh; /*minima-altura: 100*/
        background: #081b29;/*fondo:*/
    }
    .wrapper{
        position: relative;
        width: 750px;
        height: 450px;
        background: transparent; /*fondo:*/
        border: 2px solid #0ef;
        box-shadow: 0 0 25px #0ef; /*caja-sombra: 0 0 25px #0ef */
        overflow: hidden; /*desbordamiento: ocultar*/
    }
    .wrapper .form-box{
        position: absolute;
        top: 0; /*parte superio (arriba):*/
        width: 50%;
        height: 100%;
        /*background: red; /*fondo: */
        display: flex; /*pantalla: flexible*/
        flex-direction: column; /*flexionar-direccion: columna*/
        justify-content: center; /*justificacion-contenido: centro*/
    }
    .wrapper .form-box.login{
        left: 0; /*izquierda: 0 */
        padding: 0 60px 0 40px; /*relleno: 0 40px*/
        /*display: none; /*mostrar(pantalla): ninguna*/
    }
    .wrapper .form-box.login .animation{
        transform: translateX(0); /*transformar: traducirY(0)*/
        opacity: 1; /*opacidad: */
        filter: blur(0); /*filtrar: */
        transition: .7s ease; /*transicion: */
        transition-delay: calc(.1s * var(--j));/*transmicion-demora: calculo()*/
    }
    .wrapper.active .form-box.login .animation{
        transform: translateX(-120%);
        opacity: 0; /*opacidad: */
        filter: blur(10px); /*filtrar: */
        transition-delay: calc(.1s * var(--i));/*transmicion-demora: calculo()*/
    }
    .wrapper .form-box.register{
        right: 0; /*derecha: 0*/
        padding: 0 40px 0 60px; /*relleno: 0 40px*/
        /*display: none;*/
        pointer-events: none;
    }
    .wrapper.active .form-box.register{
        pointer-events: auto;
    }
    .wrapper .form-box.register .animation{
        transform: translateX(120%);
        opacity: 0;
        filter: blur(10px); /*filtro: desenfocar(difuminar)(10px)*/
        transition: .7s ease;
        transition-delay: calc(.1s * var(--j));/*transmicion-demora: calculo()*/
    }
    .wrapper.active .form-box.register .animation{
        transform: translateX(0);
        opacity: 1;
        filter: blur(0); /*filtro: desenfocar(difuminar)(10px)*/
        transition-delay: calc(.1s * var(--i));/*transmicion-demora: calculo()*/
    }
    .form-box h2{
        font-size: 32px; /*fuete-tamaño: 32px*/
        color: #fff;
        text-align: center; /*texto-aliniacion: centro*/
    }
    .wrapper .input-box{
        position: relative; /*posicion: relativa*/
        width: 100%;
        height: 50px;
        /*background: seagreen;*/
        margin: 25px 0;
    }
    .input-box input{
        width: 100%;
        height: 100%;
        background: transparent; /*fondo: transparente*/
        border: none;
        outline: none;/*fuera linea: ninguna*/
        border-bottom: 2px solid #fff; /*border-inferior(abajo): 2px solida #fff*/
        transition: .5s;
        padding-right: 23px; /*relleno-derecho: 23px*/
        font-size: 16px;
        color: #fff;
        font-weight: 500;
        transition: .5s;
    }
    .input-box input:focus,
    .input-box input:valid{
        border-bottom-color: #0ef; /*borde-inferior(abajo): */
    }
    .input-box label{
        position: absolute; /*posicion: absoluta*/
        top: 50%; /*parte superio (arriba):*/
        left: 0; /*izquierda: */
        transform: translateY(-50%);/*transformar: traducir Y*/
        font-size: 16px;
        color: #fff;
        pointer-events: none; /*puntero-eventos: ninguna*/
        transition: .5s;
    }
    /*****/
    .input-box input:focus ~ label,
    .input-box input:valid ~ label{
        top: -5px;
        color: #0ef;
    }
    /****/
    .input-box i{
        position: absolute;
        top: 50%; /*parte superio (arriba):*/
        right: 0; /*derecha*/
        transform: translateY(-50%);
        font-size: 18px;
        color: #fff;
        transition: .5s; /*transicion: .5segundos*/
    }
    /****/
    .input-box input:focus ~ i,
    .input-box input:valid ~ i{
        color: #0ef;
    }
    /****/
    .btn{
        position: relative;
        width: 100%; /*ancho: 100%*/
        height: 45px; /*altura: 45px*/
        background: transparent; /*fondo: transparente*/
        border: 2px solid #0ef;
        outline: none; /*fuera linea: ninguna*/
        border-radius: 40px; /*borde-radio: 40px*/
        cursor: pointer; /*cursor: puntero*/
        font-size: 16px;
        color: #fff;
        font-weight: 600; /*fuente-peso: 600*/
        z-index: 1;
        overflow: hidden; /*desbordamiento: ocultar*/
    }
    .btn::before{
        content: '';
        position: absolute;
        top: -100%; /*parte superio (arriba): -100%*/
        left: 0; /*izquierda: 0% */
        width: 100%;
        height: 300%;
        background: linear-gradient(#081b29, #0ef, #081b29, #0ef);
        z-index: -1; /*z-indice: -1*/
        transition: .5s;
    }

    .btn:hover::before{
        top: 0;
    }
    .form-box .logreg-link{
        font-size: 14.5px;
        color: #fff;
        text-align: center;
        margin: 20px 0 10px;
    }
    .logreg-link p a{
        color: #0ef;
        text-decoration: none;
        font-weight: 600; /*fuente-peso: 600*/
    }
    .logreg-link p a:hover{ /*hover => cernerse(flotar)*/
        text-decoration: underline;/*texto-decoracion: subrayar*/
    }
    /*********************************************************************/
    .wrapper .info-text{
        position: absolute;
        top: 0;
        width: 55%;
        height: 100%;
        /*background: red;*/
        display: flex; /*pantalla: flexible*/
        flex-direction: column; /*flexible-direccion: columna*/
        justify-content: center; /*justificacion-contenido: centro*/
    }
    .wrapper .info-text.login{
        right: 0; /*derecha: 0*/
        text-align: right;
        padding: 0 40px 60px 150px; /*relleno: */
        /*display: none;*/
    }

    .wrapper .info-text.login .animation{
        transform: translateX(0); /*transformar: traducirY(0)*/
        opacity: 1; /*opacidad: */
        filter: blur(0); /*filtrar: */
        transition: .7s ease; /*transicion: */
        transition-delay: calc(.1s * var(--j));/*transmicion-demora: calculo()*/
    }
    .wrapper.active .info-text.login .animation{
        transform: translateX(120%);
        opacity: 0; /*opacidad: */
        filter: blur(10px); /*filtrar: */
        transition-delay: calc(.1s * var(--i));/*transmicion-demora: calculo()*/
    } 

    .wrapper .info-text.register{
        left: 0; /*izquierda: 0*/
        text-align: left;
        padding: 0 150px 60px 40px; /*relleno: */
        /*display: none;*/
        pointer-events: none;
    }
    .wrapper.active .info-text.register{
        pointer-events: auto;
    }
    .wrapper .info-text.register .animation{
        transform: translateX(-120%);
        opacity: 0;
        filter: blur(10px);
        transition: .7s ease;
        transition-delay: calc(.1s * var(--j));/*transmicion-demora: calculo()*/

    }
    .wrapper.active .info-text.register .animation{
        transform: translateX(0);
        opacity: 1;
        filter: blur(0);
        transition-delay: calc(.1s * var(--i));/*transmicion-demora: calculo()*/
    }
    .info-text h2{
        font-size: 36px;
        color: #fff;
        line-height: 1.3; /*linea-altura: */
        text-transform: uppercase;
    }
    .info-text p{
        font-size: 16px;
        color: #fff;
    }
    .wrapper .bg-animate{
        position: absolute;
        top: -4px; /*parte superio (arriba): -100%*/
        right: 0; /*derecha: 0*/
        width: 850px; /*ancho: 850px*/
        height: 600px; /*altura: 600px*/
        background: linear-gradient(45deg, #081b29, #0ef); /*fondo: linea-gradiante()*/
        border-bottom: 3px solid #0ef; /*border-inferior(abajo): 3px solida #0ef*/
        transform: rotate(10deg) skewY(40deg);/*transformacion: rotar() sesgar*/
        /*transform: rotate(0) skewY(0);/*transformacion: rotar() sesgar*/
        transform-origin: bottom right; /*transformacion-original: inferior(abajo) derecho*/
        transition: 1.5s ease; /*transicion: 1.5s facilitar*/
        transition-delay: 1.6s; /*transicion-retraso(demora): */
    }
    .wrapper.active .bg-animate{
        transform: rotate(0) skewY(0);/*transformacion: rotar() sesgar*/
        transition-delay: .5s;/*transmicion-demora: .5s*/

    }
    .wrapper .bg-animate2{
        position: absolute;
        top: 100%; /*parte superio (arriba): 100%*/
        left: 250px; /*izquierda: 250px*/
        width: 850px; /*ancho: 850px*/
        height: 700px; /*altura: 700px*/
        background: #081b29; /*fondo: #081b29*/
        border-top: 3px solid #0ef; /*border-superio(arriba): 3px solida #0ef*/
        /*transform: rotate(-11deg) skewY(-41deg);/*transformacion: rotar() sesgar*/
        transform: rotate(0) skewY(0);/*transformacion: rotar() sesgar*/
        transform-origin: bottom left; /*transformacion-original: inferior(abajo) izquierdo*/
        transition: 1.5s ease; /*transicion: 1.5s facilitar*/
        transition-delay: .5s; /*transicion-retraso(demora): */
    }
    .wrapper.active .bg-animate2{
        transform: rotate(-11deg) skewY(-41deg);/*transformacion: rotar() sesgar*/
        transition-delay: 1.2s; /*transicion-retraso(demora): */
    }
</style>