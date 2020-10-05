<template>
  <div>
    <span class="leta">❯</span>
    <span class="command">./run.sh</span>
  </div>

  <h1 class="rainbow">
    {{ title }}
  </h1>

  <p>
    💻
    <span class="text-red-500">
      TerminaLA
    </span> es un curso para aprender, mejorar y optimizar tus habilidades con la linea de comandos y con UNIX.
  </p>

  <p>
    💪 Archivos, directorios, usuarios, ssh, paquetes, scripts y muchas herramientas que te van a ayudar a mejorar tu flujo de trabajo
  </p>

  <p>
    📅 Lunes 12 de Octubre (horario a confirmar)
  </p>


  <p>
    📺
    <a class="rainbow" href="https://twitch.tv/ianaya89">
    https://twitch.tv/ianaya89</a>
  </p>

  <span class="leta">❯</span>
  <span class="blinking">|</span>
</template>

<script>
import { ref } from 'vue'
import figlet from 'figlet'
import standard from 'figlet/importable-fonts/Standard.js'

figlet.parseFont('Standard', standard);

export default {
  name: 'App',

  setup () {
    const title = ref('Terminal')

    figlet.text('TerminaLA', { font: 'Standard' }, function(err, data) {
     if (err) {
       return
     }

      console.log(data)
      title.value = data.replace(/ /g, ' ')
    });

    return { title }
  }
}
</script>

<style>
  body {
    height: 100vh;
    background: #011627;
    color: #D6DEEB;
    padding: 1rem;
    margin: 0;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    text-align: left;
    font-family: 'Fira Code', monospace;
  }

  .leta {
    color: #C792EA;
    font-weight: bold;
    font-size: 1.5rem;
  }

  p {
    font-size: 1.5rem;
  }

  .command {
    color: #22DA6E;
    font-weight: 500;
    margin-left: 1rem;
    font-size: 1.5rem;
  }

  .rainbow {
    background: linear-gradient(45deg,#FF0000,#FF7F00,#FFFF00,#00FF00,#0000FF,#4B0082,#8B00FF);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-size:100%;
  }

  h1 {
    white-space: pre;

    font-family: monospace;
  }

  .blinking {
    font-size: 1.5rem;
    font-weight: bold;
    animation: 1s blink step-end infinite;
  }

  @keyframes blink {
    from, to {
      color: transparent;
    }
    50% {
      color: #D6DEEB;
    }
  }

</style>