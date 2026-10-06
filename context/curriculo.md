# Currículo — Mentor-Especialista v6

## Descoberta (passo 0)

- **Aluno:** profissional de mais de 30 anos. Já usa ChatGPT ou Claude no dia a dia e acabou de instalar o Claude Code. Quer que a IA o **ensine** de verdade, e não só entregue respostas.
- **Profissões-alvo dos exemplos:** **professora / instrutora** (monta o mentor de um autor de referência da área dela para preparar aulas) e **consultor de vendas / pequeno empresário** (monta o mentor de um especialista de negócios que acompanha há anos).
- **Tecnologia:** chat de IA, YouTube, um pouco de terminal (copia e cola comando). **Perfil técnico**: terminal permitido, todo termo definido com `.gterm` na aula.
- **Sai fazendo:** um mentor próprio funcionando (fontes, wiki, regras com citação, 3 testes) e reconhecer quando a IA "disse que funciona" sem ter rodado.
- **Tempo:** uns 15 minutos por aula.

## Fio condutor

O **piloto real** do mentor do Nei (repo público `inematds/mentor-nei`, kit `inematds/mentor-especialista` v1.3). Números reais: 22 fontes (14 lives + 8 guias), cerca de 189 mil palavras; 13 lives coletadas pela legenda em 1,6 min; uma live sem legenda transcrita localmente em 7,7 min; wiki com 76 páginas e cerca de 1.300 links; 10 regras ativas com 40 citações; placar final 5/5, nota 8. Detalhes e casos: `~/projetos/mentor-especialista-curso/PLANO-CURSO.md`, `~/projetos/mentor-nei/PILOTO-DIARIO.md`, `~/projetos/mentor-nei/testes/aceitacao/RESULTADOS.md`, `~/projetos/mentor-nei/regras.md`, `~/projetos/mentor-nei/wiki/hot.md`.

**Nunca** citar fontes externas de referência. O kit é uma solução da comunidade INEMA. Só números reais.

## Aulas (promessa · tipo da prática · gancho)

### Módulo 1 · Por que um mentor
1. **A IA que parece certa sem estar.** Promessa: você reconhece os 4 maus hábitos da IA quando ensina (explica demais, parece certa sem estar, supõe sem avisar, fala no genérico) numa resposta real. Prática: análise (comparar duas respostas). Gancho: o caso em que a própria sessão disse "o validador passa" e o validador de fora reprovou.
2. **Copiar o método, não a pessoa.** Promessa: você escreve em uma frase o domínio estreito do seu mentor e o que fica de fora. Prática: tarefa (preencher o domínio em 1 frase + 3 itens fora). Gancho: domínio bom × ruim; o escopo do mentor do Nei.
3. **Criar a pasta do seu mentor.** Promessa: você roda `novo-mentor.py` e confere que nasceram o agente, as 6 skills e o portão. Prática: tarefa no terminal (copiar e colar 2 comandos e conferir 3 arquivos). Gancho: o que cada pasta guarda (raw, wiki, regras, .claude).

### Módulo 2 · Montar o acervo
4. **Juntar as fontes sem pagar API.** Promessa: você lista 10 fontes do seu especialista e sabe qual coletor usa para cada uma. Prática: tarefa (tabela de fontes no ESCOPO.md). Gancho: legenda antes de transcrição: 13 lives em 1,6 min; exportação manual em vez de API paga.
5. **Coletar e conferir: manifesto, falhas e metas.** Promessa: você roda um coletor e lê o `stats.py` dizendo o que falta. Prática: tarefa no terminal (coletar 1 arquivo, rodar stats). Gancho: os 2 bugs reais do piloto (paralelo sem trava; transcrição chamada `transcript.txt`) e como o kit corrigiu.
6. **Da pilha de texto à wiki.** Promessa: você explica por que o acervo cru não serve como memória e pede a wiki ao Claude Code. Prática: prompt (`/<slug>-compilar` + `validar_links.py`). Gancho: raw intocável (o hash denuncia); fase 2 do piloto: 5 subagentes, 3,3 min, 73 páginas.
7. **A página "hot" e o teste do "é a pessoa?".** Promessa: você julga se a wiki reflete o especialista ou a IA genérica. Prática: análise (marcar 3 páginas boas e 3 ruins). Gancho: o hot do Nei (verificar antes de afirmar, 17 fontes; menor custo, 16; medir, 14); ida e volta de links.

### Módulo 3 · Regras e mentor
8. **Regra é o que a pessoa faz.** Promessa: você distingue uma regra de conduta de uma frase de efeito. Prática: análise (classificar 6 frases). Gancho: as regras do Nei (R1 conferir antes de dizer pronto… R10 handoff não é permissão).
9. **Citação conferida por script.** Promessa: você roda o validador de citações e vê ele reprovar uma frase inventada. Prática: tarefa no terminal (teste negativo numa cópia). Gancho: ativa × banco × inferência; o erro do operador no piloto (git checkout apagou regras não salvas) e a lição "salve antes de testar".
10. **O passo a passo do mentor.** Promessa: você reconhece as 6 partes de uma resposta do mentor numa lição real. Prática: análise (achar Pronto, Previsão, Saída real, Versão quebrada, Relatório numa resposta). Gancho: a lição real do hook TODO.md, com a versão ingênua que entra em loop infinito.
11. **O portão: rodar antes de dizer que funciona.** Promessa: você provoca o portão e entende o aviso "Stop hook error occurred". Prática: prompt (pedir para criar um arquivo e não rodar). Gancho: o portão provado no piloto; o que não conta como "rodar" (listar, abrir o arquivo, git commit).

### Módulo 4 · Provar e manter
12. **Os 3 testes do piloto.** Promessa: você roda o teste 1 (ensinar construindo) no seu mentor e confere pelo validador. Prática: prompt (`/<slug>-ensina` + validador). Gancho: o placar do piloto e o teste 2 que falhou.
13. **Instrução não basta: o portão de previsão.** Promessa: você explica por que pedir "preveja antes" não funcionou e o que funcionou. Prática: análise (ler as 4 rodadas e apontar a virada). Gancho: rodadas 2 e 3 falham, rodada 4 passa com o portão de previsão do kit 1.3 → 5/5.
14. **Ensinar coisa nova e atualizar o kit.** Promessa: você ingere um link novo e atualiza o mentor para a versão nova do kit sem perder nada. Prática: tarefa no terminal (`/<slug>-ingere` + `novo-mentor.py --atualizar`). Gancho: o guia novo que criou as regras R9 e R10; o conselho de mentores.
