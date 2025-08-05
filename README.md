<h1>Hello World, I'm Leeh, be very welcome</h1>

<div id="typing-text" style="font-size: 1.2rem; color: #ccc; height: 30px; margin-top: 10px;"></div>

<script>
  const frases = [
    "Front-End Developer 💻",
    "Estudando Fullstack 🚀",
    "Apaixonada por código ❤️",
    "Sempre aprendendo 📚"
  ];

  const typingSpeed = 100; // velocidade de digitação (ms por letra)
  const erasingSpeed = 50; // velocidade de apagar
  const delayBetweenFrases = 2000; // tempo antes de apagar (ms)

  let fraseIndex = 0;
  let charIndex = 0;
  const typingTextElement = document.getElementById('typing-text');

  function digitar() {
    if (charIndex < frases[fraseIndex].length) {
      typingTextElement.textContent += frases[fraseIndex].charAt(charIndex);
      charIndex++;
      setTimeout(digitar, typingSpeed);
    } else {
      setTimeout(apagar, delayBetweenFrases);
    }
  }

  function apagar() {
    if (charIndex > 0) {
      typingTextElement.textContent = frases[fraseIndex].substring(0, charIndex - 1);
      charIndex--;
      setTimeout(apagar, erasingSpeed);
    } else {
      fraseIndex = (fraseIndex + 1) % frases.length;
      setTimeout(digitar, typingSpeed);
    }
  }

  digitar();
</script>
