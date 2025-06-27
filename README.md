<!DOCTYPE html>
<html lang="pt-BR">
<cabeça>
  <meta charset="UTF-8">
  <title>Tradutor de Alfabeto Secreto</title>
  <estilo>
    corpo {
      família de fontes: Arial, sem serifa;
      fundo: #f9f9f9;
      preenchimento: 20px;
    }
    h1, h2 {
      cor: #333;
    }
    área de texto {
      largura: 100%;
      altura: 100px;
      tamanho da fonte: 16px;
      margem inferior: 10px;
    }
    botão {
      preenchimento: 10px 20px;
      tamanho da fonte: 16px;
      margem direita: 10px;
    }
    .disse {
      margem superior: 10px;
      preenchimento: 10px;
      fundo: #fff;
      borda: 1px sólido #ccc;
      altura mínima: 60px;
      tamanho da fonte: 18px;
      espaço em branco: pré-encapsulamento;
    }
    .copiar {
      cor de fundo: #4CAF50;
      cor: branco;
      borda: nenhuma;
      cursor: ponteiro;
    }
  </estilo>
</cabeçalho>
<corpo>

  <h1>Tradutor de Alfabeto Secreto</h1>

  <h2>Texto comum → Código secreto</h2>
  <textarea id="textoNormal" placeholder="Ex: Ana e Juan"></textarea>
  <br>
  <button onclick="traduzir()">Traduzir</button>
  <button class="copiar" onclick="copiar('saidaTraducao')">📋 Copiar</button>
  <div id="saidaTraducao" class="saida"></div>

  <h2>Código secreto → Texto comum</h2>
  <textarea id="textoCodigo" placeholder="Ex: ∩ᒷ: ᔑ ∩∩ᒷᒷ"></textarea>
  <br>
  <button onclick="destraduzir()">Destraduzir</button>
  <button class="copiar" onclick="copiar('saidaReverso')">📋 Copiar</button>
  <div id="saidaReverso" class="saida"></div>

  <script>
    const alfabetoSecreto = {
      "a": "ᒷ", "b": "ᓭ", "c": "<", "d": "ᑑ", "e": ":",
      "f": "ᓵ", "g": "ᓷ", "h": "ᔑᔑ", "i": "‖", "j": "ᒣ",
      "k": "ᒣᒣ", "l": "ᒲ", "m": "‖‖", "n": "∩", "o": "O",
      "p": "ᑊ", "q": "ᓹ", "r": "ᓮ", "s": "ᔑ", "t": "‖ᔑ",
      "u": "∩∩", "v": "ᓭᓭ", "w": "ᒷᒷ", "x": "★", "y": "¥", "z": "ᔑ∷",
      " ": " "
    };

    // Cria dicionário reverso
    const alfabetoReverso = {};
    for (deixe a letra do alfabeto secreto) {
      alfabetoReverso[alfabetoSecreto[letra]] = letra;
    }

    função traduzir() {
      const texto = document.getElementById("textoNormal").value.toLowerCase();
      deixe resultado = "";
      para (deixe char do texto) {
        resultado += alfabetoSecreto[char] || caractere;
      }
      document.getElementById("saidaTraducao").innerText = resultado;
    }

    função destraduzir() {
      deixe texto = document.getElementById("textoCodigo").value;
      const símbolos = Object.keys(alfabetoReverso).sort((a, b) => b.length - a.length);
      for (seja símbolo de símbolos) {
        texto = texto.split(simbolo).join(alfabetoReverso[simbolo]);
      }
      document.getElementById("saidaReverso").innerText = texto;
    }

    função copiar(id) {
      const texto = document.getElementById(id).innerText;
      navigator.clipboard.writeText(texto).then(() => {
        alert("Texto copiado com sucesso!");
      }).catch(erro => {
        alert("Erro ao copiar: " + err);
      });
    }
  </script>

</corpo>
</html># tradutor-alfabeto
tradutor-alfabeto
