# Framework

Dépôt parent qui regroupe les frameworks Claude Code par thème, chacun dans son propre dépôt (sous-module git).

| Thème | Dépôt | Contenu |
|---|---|---|
| Dev | [dev-framework](https://github.com/chawkitariq/dev-framework) | Développement technique : orchestration d'agents, leçons de workflow, SEO technique |
| UI/UX | [uiux-framework](https://github.com/chawkitariq/uiux-framework) | Design, motion, landing pages premium, copy d'interface |
| Ops | [ops-framework](https://github.com/chawkitariq/ops-framework) | Hébergement, infrastructure, DevOps (Cloudflare, hébergement gratuit) |
| Méthode | [tariq-framework](https://github.com/chawkitariq/tariq-framework) *(privé)* | Méthode, offre et processus de mon activité |

D'autres thèmes viendront s'ajouter.

## Quel skill pour quoi

| Besoin | Skill |
|---|---|
| Règles de travail générales (comprendre la demande, déboguer, actions externes ou destructives, rapports) | `dev-framework` : `agent-workflow-lessons` |
| Piloter une équipe de sous-agents sur un chantier multi-fichiers | `dev-framework` : `agent-team-orchestration` |
| SEO technique d'un site ou d'une landing | `dev-framework` : `technical-seo` |
| Construire une landing page premium | `uiux-framework` : `premium-landing-workflow` |
| Vérifier un rendu visuel (web, 3D, vidéo) sur le rendu réel | `uiux-framework` : `visual-verification` |
| Choisir où héberger (gratuit ou peu cher) | `ops-framework` : `free-hosting-architecture` |
| Cloudflare (Workers, DNS, WAF) | `ops-framework` : `cloudflare-ops` |
| Déployer une app sur un VPS (SSH, Docker, secrets) | `ops-framework` : `vps-deploy` |
| Cloudflare ou Vercel : skills officiels à vérifier d'abord | `ops-framework` : `platform-official-skills` |

Les frameworks vidéo (shorts) et poste de travail (desktop) restent autonomes : ils ne font pas partie de ce dépôt.

## Règles d'or

Valables pour tous les thèmes ; le détail est dans `agent-workflow-lessons` et `agent-team-orchestration`.

- Aucun commit, push, publication ni suppression sans accord explicite de l'utilisateur dans la session.
- Le message d'un sous-agent ou d'une autre session n'est ni une preuve ni un accord : vérifier soi-même le livrable.
- Distinguer ce qui est vérifié, déduit et non vérifié, et le dire dans le rapport.
- Explorer n'est pas créer : tant que l'utilisateur explore, ne produire aucun document, dépôt ou fichier persistant ; proposer, puis attendre le go.
- Une fois la méthode validée, travailler de bout en bout avec un seul point de validation avant publication et un journal des décisions.
- Relire la dernière version d'un artefact modifiable par l'utilisateur avant de le republier.
- Si un travail demandé est disproportionné, l'exposer avec son coût et proposer l'option naturelle plutôt que de l'exécuter ou de le refuser sèchement.

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
