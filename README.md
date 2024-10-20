# git-custom-commands
1. checkout the files to some folder (~/bin)
2. Add the path to the folder to .zshrc (export PATH=$PATH:$HOME/bin)
3. newbrach requires jira cli:
    - ```
      brew tap ankitpokhrel/jira-cli
      brew install jira-cli
      ```
    - [Create API token](https://id.atlassian.com/manage-profile/security/api-tokens)

    - Place the token under .zshrc: `export JIRA_API_TOKEN="xxx"`
