# morfossintaxe

Quando o formulario é enviado, é chamada a funcao enviar, e apartir dela são chamadas outras 4 função:

Função 1 (array): transforma a string do formularia em uma array de string, sendo cada indice uma palavra
  A função recebe uma string é usando chatAt() com um loop; se o caracter for um espaço (" ") então para para o proximo indice do array, se não o caracter é adicionado ao indice atual. E ao mesmo tempo todas as letras são passadas para lowercCase para evitar erros.


Função 2 (plural): recebe o array  de palavras e verificar se alguma palavra terminar com "am" e salvar esse indice pois pode ser um verbo na 3ª pessoa do plural
        se o caracter length-2 e length-1 for (ultima e penultima letras da palavra), respectivamente 'a' e 'm' salva o indice dessa palavra em uma variavel
        Se essa variavel for preenchinda então:
            Se esse indice for o 0 (primeira palavra da frase) então (provavelmente) é um sujeito indeterminado.
            Se não o sujeito é (provavelmente) composto.
        Se não for preenchida então é simples (ou oculto).
  
Função 3(verbal): tem um loop que passa por todas as palavras comparando cada uma delas a uma array de verbos de ligação
        se alguma dessas palavras for um verbo de ligação o predicado é (provavelmente) nominal
        se não é (provavelmente) predicado verbal

Função 4 (inexistente):tem um loop que passa por todas as palavras comparando cada uma delas a uma array de verbos comuns em frase com sujeito inexistente (como: chove, há, faz, neva)
          se alguma das palavras for igual a algum dos verbos da lista o sujeito é (provavelmente) inexistente
