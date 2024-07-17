# Diagrama de Classes

```mermaid
classDiagram
    class Usuario {
      Long id
      String nome
      String email
      String senha
      void cadastrar()
      void autenticar()
    }

    class Questao {
      Long id
      String enunciado
      String respostaCorreta
      String explicacao
      String areaDeEstudo
      String categoria
      String subcategoria
      String areaDeConhecimento
      String topicoOuAssunto
      String[] tags
      String fonte
      void adicionarQuestao()
      void editarQuestao()
      void removerQuestao()
    }

    class Alternativa {
      Long id
      String texto
      Boolean correta
      void adicionarAlternativa()
      void editarAlternativa()
      void removerAlternativa()
    }

    class Resultado {
      Long id
      Usuario usuario
      Questao questao
      Alternativa alternativa
      Boolean acertou
      Long tempoParaResponder
      void calcularPontuacao()
    }

    Usuario "1" -- "0..*" Resultado : realiza
    Questao "1" -- "0..*" Alternativa : tem
    Questao "1" -- "0..*" Resultado : é
    Resultado "1" -- "1" Alternativa : seleciona
