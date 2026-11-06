# Programação II · exercícios em C

Acervo acadêmico de exercícios de Programação II da UFES, com enunciados, interfaces, casos de entrada e saída e resoluções em C. A organização acompanha a progressão da disciplina: revisão, recursão, modularização, ponteiros, memória dinâmica, Tipos Abstratos de Dados (TADs) e arquivos binários.

Este repositório é um fork de [prog-II-ufes/exercicios-gerais](https://github.com/prog-II-ufes/exercicios-gerais). Ele preserva o material da disciplina e inclui resoluções em diretórios como `Respostas/Gabriel`. Os enunciados, interfaces e gabaritos fornecidos não devem ser confundidos com as resoluções do estudante; a presença de um exercício também não significa que sua implementação esteja completa.

## Navegação por assunto

| Pasta | Conteúdo | Aulas no cronograma original |
| --- | --- | --- |
| [01_revisao](01_revisao/) | Revisão de Programação I | 01 |
| [02_recursao](02_recursao/) | Funções recursivas | 03 |
| [03_bibliotecas](03_bibliotecas/) | Separação de arquivos, modularização e bibliotecas estáticas/dinâmicas | 04–06 |
| [04_TAD_simples](04_TAD_simples/) | TADs sem alocação dinâmica | 07–08 |
| [05_ponteiros](05_ponteiros/) | Ponteiros, passagem de parâmetros e ponteiros para funções | 09–12 |
| [06_alocacao_dinamica](06_alocacao_dinamica/) | Memória dinâmica e TADs dinâmicos | 13–17 |
| [07_TAD_opaco](07_TAD_opaco/) | Encapsulamento com TADs opacos | 18 |
| [08_TAD_generico](08_TAD_generico/) | TADs genéricos | 19–22 |
| [09_arquivo_binario](09_arquivo_binario/) | Arquivos binários combinados com os conceitos anteriores | 23–24 |

A sequência foi concebida para acompanhar o avanço das aulas, com dificuldade crescente. O material original foi construído progressivamente por professores e monitores.

## Por onde começar

- [Inversão recursiva de palavras](02_recursao/rec_01/prog.c): exemplo curto para acompanhar chamadas recursivas; [enunciado](02_recursao/rec_01/rec_01.pdf).
- [Área e volume de uma esfera](03_bibliotecas/bibli_01/Respostas/Gabriel/): separação entre programa principal, implementação e [interface pública](03_bibliotecas/bibli_01/Includes/esfera_utils.h); [enunciado](03_bibliotecas/bibli_01/bibli_01.pdf).
- [Pontos e círculos](07_TAD_opaco/TAD_opac_00/Respostas/Gabriel/): exercício de TAD opaco com criação, consulta e liberação de objetos.
- [TADs genéricos](08_TAD_generico/): continuação da sequência para estudar interfaces e armazenamento genérico.

## Como ler a estrutura de um exercício

As pastas variam conforme o tema. Quando presentes:

| Caminho | Papel |
| --- | --- |
| PDF | Especificação do exercício e regras de correção |
| `Includes/` | Headers com as interfaces fornecidas |
| `Respostas/` | Código das resoluções, frequentemente em `Respostas/Gabriel/` |
| `Casos/` | Entradas e saídas esperadas fornecidas para o exercício |
| `Gabarito-obj/` | Objetos e executáveis de referência da disciplina |
| `Resultados/`, `Resultado.csv`, `log.txt` | Registros de execuções anteriores dos scripts de correção |

Há também fontes diretamente na pasta de alguns exercícios, além de executáveis e artefatos históricos. Consulte o PDF e os headers antes de compilar cada resolução; não há um único programa para todo o repositório.

## Compilar e executar exemplos

Requisitos para os exemplos abaixo: terminal com GCC e biblioteca matemática do sistema. Execute a partir da raiz do repositório em Linux ou WSL. Os executáveis serão gravados em `/tmp`.

### Recursão

```bash
gcc -std=c11 -Wall -Wextra 02_recursao/rec_01/prog.c -o /tmp/prog2-recursao
printf 'ufes dados\n' | /tmp/prog2-recursao
```

A saída inverte cada palavra: `sefu sodad` (com espaço ao final).

### Modularização e biblioteca matemática

```bash
gcc -std=c11 -Wall -Wextra \
  -I03_bibliotecas/bibli_01/Includes \
  03_bibliotecas/bibli_01/Respostas/Gabriel/main.c \
  03_bibliotecas/bibli_01/Respostas/Gabriel/esfera_utils.c \
  -lm -o /tmp/prog2-esfera
/tmp/prog2-esfera < 03_bibliotecas/bibli_01/Casos/1/entrada.txt
```

Para o raio `3.8` do caso fornecido, a saída é:

```text
Area: 181.37
Volume: 229.73
```

Esse resultado usa o valor de `PI` definido no header do exercício. A saída esperada está em [Casos/1/saida/saida.txt](03_bibliotecas/bibli_01/Casos/1/saida/saida.txt).

## Correção automática da disciplina

A partir do módulo de bibliotecas, o material prevê scripts para compilar, comparar entradas e saídas, verificar vazamentos de memória e avaliar a adequação às interfaces de TAD. Cada especificação determina como usar a correção.

O projeto original do script está em [prog-II-ufes/script-de-correcao](https://github.com/prog-II-ufes/script-de-correcao). Há cópias de `correcao.sh` em módulos e exercícios deste acervo. Elas usam ferramentas como Bash, GCC e Valgrind e podem recriar pastas de resultados. Leia o script e o enunciado e execute-o em uma cópia de trabalho, a partir da pasta do exercício correspondente.

Os registros já versionados são históricos. A execução dos dois exemplos acima não verifica todos os exercícios nem substitui as verificações de memória e interface do corretor.

## Contexto e créditos

- Material-base, enunciados, interfaces e gabaritos: professores e monitores de [Programação II da UFES](https://github.com/prog-II-ufes).
- Resoluções identificadas como `Gabriel`: organizadas neste fork de [Gabriel de Albuquerque](https://github.com/gabrieldealbuquerque); outros arquivos mantêm seus créditos e comentários de origem.
- Linguagem principal: **C**; scripts auxiliares em **Shell/Bash**.

Dúvidas sobre enunciados e sugestões para o material original podem ser encaminhadas aos professores e monitores da disciplina. Este acervo registra atividades de estudo e suas versões históricas.
