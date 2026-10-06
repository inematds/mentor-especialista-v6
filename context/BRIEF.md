# Brief para autores de aula — Mentor-Especialista v6

## Leia antes (nesta ordem)
1. `~/.claude/skills/formato-curso-v6/SKILL.md`
2. `~/.claude/skills/formato-curso-v6/references/CONTEUDO-INICIANTE.md` (inclui §2b, o perfil técnico)
3. `~/.claude/skills/formato-curso-v6/references/V6-DESIGN.md` (visuais com markup pronto)
4. `~/.claude/skills/formato-curso-v6/references/CHECKLIST-V6.md` (a rubrica que o script mede)
5. **Aula-modelo aprovada (10/10):** `~/.claude/skills/formato-curso-v6/examples/aula-1-oswork.html`. Copie a estrutura e o tom. Molde vazio: `~/.claude/skills/formato-curso-v6/assets/aula-template.html`.
6. **Currículo deste curso:** `~/projetos/mentor-especialista-v6/context/curriculo.md` (aluno, profissões, promessa, tipo e gancho de cada aula)
7. **Glossário/perfil:** `~/projetos/mentor-especialista-v6/curso.json` (`perfil: tecnico` + `termos`: todo termo da lista que aparecer na aula precisa de `.gterm` na própria aula)

## Conteúdo de origem (fatos e números reais; não invente)
- Plano detalhado e casos reais: `~/projetos/mentor-especialista-curso/PLANO-CURSO.md`
- Kit: `~/projetos/mentor-especialista/` (README.md, docs/PLANO.md, docs/PILOTO.md, docs/ADAPTAR.md, CHANGELOG.md, novo-mentor.py, template/)
- Piloto: `~/projetos/mentor-nei/` (PILOTO-DIARIO.md, testes/aceitacao/RESULTADOS.md, testes/respostas/*.md, regras.md, wiki/hot.md, ESCOPO.md, exemplos/hook-todo-stop/)
- Se precisar de um detalhe já explicado com profundidade, o curso v2 está em `~/projetos/mentor-especialista-curso/curso/` (só como referência de fatos; NÃO copie o estilo, o v6 é outro formato).
- **Proibido:** citar fontes externas de referência. O kit é solução da comunidade INEMA. Só números que estão no material.

## Profissões dos exemplos (`p[data-ex]`)
Alterne entre **professora** (Marta) e **consultor de vendas** (Rui), os dois personagens das cenas. O exemplo deve ser concreto: qual especialista ela/ele escolheu (invente um especialista **fictício** da área, nunca uma pessoa real além do Nei), qual fonte, o que o mentor respondeu.

## Cena da aula
`figure.cena` aponta para `assets/img/aula-N.webp` (já sendo gerada; descrição em `/tmp/claude-1000/-home-nmaldaner-projetos-wifi/4dbcc26c-5b01-4a95-b2c8-b43ada10b268/scratchpad/cenas-v6.sh`). Escreva o `alt` descrevendo essa cena.

## Verificação (numa cópia isolada; NUNCA monte no repositório real)
```bash
S=/tmp/claude-1000/-home-nmaldaner-projetos-wifi/4dbcc26c-5b01-4a95-b2c8-b43ada10b268/scratchpad/v6-aulas-<SUAS-AULAS>
rm -rf $S && cp -r ~/projetos/mentor-especialista-v6 $S && rm -rf $S/.git $S/aulas/*
# coloque SÓ as suas aulas em $S/aulas/ e deixe em curso.json → "modulos" apenas um módulo com elas
python3 ~/.claude/skills/formato-curso-v6/scripts/montar-curso.py $S
node ~/.claude/skills/formato-curso-v6/scripts/auditar-curso.cjs $S/curso.html
node ~/.claude/skills/formato-curso-v6/scripts/testar-motor.cjs $S/curso.html
```
Itere até **toda aula ≥9/10, sem falha nos critérios 7, 8 e 10**, e o motor sem erro. Depois faça o **leitor simulado** (`references/TESTE-HUMANO.md` §1) em cada aula e corrija qualquer "travei".

## Entrega
Copie de volta SOMENTE `aulas/aula-N.html` das suas aulas para `~/projetos/mentor-especialista-v6/aulas/`. Não mexa em curso.json, assets, landing, nem nas aulas dos outros. Sem commit. Sem API paga.
Relate: nota do auditor por aula, o que corrigiu, resultado do leitor simulado e dúvidas de conteúdo.
