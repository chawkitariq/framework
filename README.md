# Framework

Dépôt parent qui regroupe les frameworks Claude Code par thème, chacun dans son propre dépôt (sous-module git).

| Thème | Dépôt | Contenu |
|---|---|---|
| Dev | [dev-framework](https://github.com/chawkitariq/dev-framework) | Développement technique : orchestration d'agents, leçons de workflow, SEO technique |
| UI/UX | [uiux-framework](https://github.com/chawkitariq/uiux-framework) | Design, motion, landing pages premium, copy d'interface |
| Ops | [ops-framework](https://github.com/chawkitariq/ops-framework) | Hébergement, infrastructure, DevOps (Cloudflare, hébergement gratuit) |
| Méthode | [tariq-framework](https://github.com/chawkitariq/tariq-framework) *(privé)* | Méthode, offre et processus de mon activité |

D'autres thèmes viendront s'ajouter.

## Cloner

```bash
git clone --recurse-submodules https://github.com/chawkitariq/framework.git
# déjà cloné :
git submodule update --init --recursive
# mettre à jour tous les thèmes :
git submodule update --remote --merge
```

`tariq-framework` est privé : sans accès, son sous-module échoue, les autres se clonent normalement.

## Installer les skills et agents

Chaque thème suit le format Claude Code : `skills/<nom>/SKILL.md` et `agents/<nom>.md`. Pour les installer globalement :

```bash
for t in dev-framework uiux-framework ops-framework; do
  cp -r "$t"/skills/* ~/.claude/skills/ 2>/dev/null
  cp "$t"/agents/*.md ~/.claude/agents/ 2>/dev/null
done
```

(`tariq-framework` range ses skills et agents dans `.claude/` : ils s'utilisent en ouvrant ce dépôt dans Claude Code.)
