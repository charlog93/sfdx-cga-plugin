# sfdx-cga-plugin

Plugin Claude Code pour Salesforce — MCP server complet.

## Features

- **Report Builder** : rapports interactifs avec graphiques (bar, line, pie, etc.)
- **Kanban** : pipeline d'opportunités drag & drop
- **Debug Logs** : analyse des logs Apex avec timeline et governor limits
- **Document Preview** : visualisation de PDFs et images attachés aux records
- **Identity Card** : carte d'identité visuelle pour les contacts
- **SOQL / SOSL** : requêtes directes sur l'org
- **Apex** : exécution anonyme, tests, analyse de code
- **Metadata** : describe, dependencies, deploy, retrieve
- **CRUD** : create, update, delete de records

## Installation

### Via Claude Code Plugin

```bash
/plugin marketplace add charlog93/sfdx-cga-plugin
/plugin install sfdx-cga-plugin@charlog93-sfdx-cga-plugin
```

### Via npm (manuel)

```bash
npx sfdx-cga-plugin --stdio
```

## Prérequis

- **Salesforce CLI** (`sf`) installé et authentifié sur au moins une org
- **Node.js** >= 18

## Configuration

Le plugin détecte automatiquement votre org Salesforce par ordre de priorité :

1. `SF_ACCESS_TOKEN` + `SF_INSTANCE_URL` (variables d'environnement)
2. `SF_TARGET_ORG` (alias explicite)
3. Default org du projet SFDX courant
4. Default org global (`sf config set target-org <alias>`)
5. Première org connectée trouvée

Pour spécifier une org dans le `.mcp.json` :

```json
{
  "mcpServers": {
    "sfdx-cga": {
      "command": "npx",
      "args": ["-y", "sfdx-cga-plugin", "--stdio"],
      "env": {
        "SF_TARGET_ORG": "mon-alias-org"
      }
    }
  }
}
```

## License

MIT
