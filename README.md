let umidadeSolo = 30; // Começa seco
let reservatorioAgua = 100;
let sistemaLigado = false;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(220);
  
  // Interface de monitoramento
  textAlign(LEFT);
  textSize(16);
  text("🌱 Umidade do Solo: " + umidadeSolo + "%", 20, 50);
  text("💧 Reservatório: " + reservatorioAgua + "%", 20, 80);
  
  // Lógica do Equilíbrio Sustentável (Tema Agrinho)
  // O sistema só irriga se a umidade for baixa, economizando água
  if (umidadeSolo < 40 && reservatorioAgua > 0) {
    sistemaLigado = true;
    umidadeSolo += 0.2;
    reservatorioAgua -= 0.1;
  } else {
    sistemaLigado = false;
    umidadeSolo -= 0.05; // Solo seca naturalmente
  }

  exibirStatus();
}

function exibirStatus() {
  fill(sistemaLigado ? "blue" : "red");
  rect(20, 110, 150, 30);
  fill(255);
  text(sistemaLigado ? "IRRIGANDO..." : "SISTEMA EM ESPERA", 30, 130);
  
  fill(0);
  textSize(12);
  text("Objetivo: Manter umidade acima de 40% com o mínimo de água.", 20, 180);
}
