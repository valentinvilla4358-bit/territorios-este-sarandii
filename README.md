# territorios-este-sarandii

const TOTAL_TERRITORIOS = 52;

const grid = document.getElementById("grilla");
const visor = document.getElementById("visor");
const imagen = document.getElementById("imagenTerritorio");

const volver = document.getElementById("volver");
const anterior = document.getElementById("anterior");
const siguiente = document.getElementById("siguiente");

const buscador = document.getElementById("busqueda");

let territorioActual = 1;

function nombreArchivo(numero){

    return `territorios/${String(numero).padStart(2,"0")}.jpg`;

}

function abrirTerritorio(numero){

    territorioActual = numero;

    imagen.src = nombreArchivo(numero);

    imagen.alt = `Territorio ${numero}`;

    visor.classList.remove("hidden");

}

function cerrarTerritorio(){

    visor.classList.add("hidden");

}

function crearBotones(){

    for(let i=1;i<=TOTAL_TERRITORIOS;i++){

        const boton=document.createElement("button");

        boton.className="territorio";

        boton.textContent=i;

        boton.onclick=()=>abrirTerritorio(i);

        grid.appendChild(boton);

    }

}

crearBotones();