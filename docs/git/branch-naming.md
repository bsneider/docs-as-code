# Branch Naming

- [Branch Naming](#branch-naming)
  - [Working on a ticket](#working-on-a-ticket)

## Working on a ticket

1. Create a feature branch
   1. Prerequisite: create a ticket in the ticketing system if one does not already exist
   - The branch should be of the format:
     - JIRA
       - `feature/<jira-ticket>_<short_description>`
       - Eg: feature/ProjectID-78_arch-checklist
     - Gitlab
       - e.g. `feature/35_arch-checklist` 
     - GitHub Issues / Projects
       - `feature/<IssueNumber>_<short_description>`
       - Eg: feature/#35_arch-checklist
     - If the branch is named as such we have a script that will append Jira ticket / issue number to all your commit messages.
     - Note there must be an "_" underscore and not a hyphen between the Jira-ticket and the short description of the ticket

    Steps:

    1. open "Git BASH" if windows or just terminal if mac
    2. Run each line individually

        - `git config --global init.templatedir '~/.git-templates'`
        - `mkdir -p ~/.git-templates/hooks`
        - `cd ~/.git-templates/hooks`
        - `nano prepare-commit-msg`

    3. paste:

        ```bash
        #!/bin/bash
        # This way you can customize which branches should be skipped when
        # prepending commit message.
        if [ -z "$BRANCHES_TO_SKIP" ]; then
          BRANCHES_TO_SKIP=(master develop staging test)
        fi

        BRANCH_NAME=$(git symbolic-ref --short HEAD)
        BRANCH_NAME="${BRANCH_NAME##*/}"
        BRANCH_EXCLUDED=$(printf "%s\n" "${BRANCHES_TO_SKIP[@]}" | grep -c "^$BRANCH_NAME$")
        BRANCH_IN_COMMIT=$(grep -c "\[$BRANCH_NAME\]" $1)

        # Trim it down to get the parts we're interested in
        TRIMMED=$(echo $BRANCH_NAME | sed -E 's/(^[a-z]+\/)?([A-Z]{1,4}[-]{1}[0-9]{1,4}).*/\2/')

        # If it isn't excluded, preprend the trimmed branch identifier to the given message
        if [ -n "$BRANCH_NAME" ] &&  ! [[ $BRANCH_EXCLUDED -eq 1 ]] && ! [[ $BRANCH_IN_COMMIT -ge 1 ]]; then
          sed -i.bak -e "1s/^/[$TRIMMED] /" $1
        fi
        ```

    4. Save and exit
    5. MacOS and Linux only

        ```bash
        chmod +x  ~/.git-templates/hooks/prepare-commit-msg
        ```

    6. Run

        ```bash
        git config --global core.hooksPath ~/.git-templates/hooks/
        ```

    Sources:
     1. [PreCommitHookSource](https://gist.github.com/achromik/67c6e1a2d53b211ad2fa574ef25ad965#file-prepare-commit-msg-L2)

__Note:__

1. You might get errors when merging that first line in the template should be `#!bin/sh`. In these scenarios, open the prepare-commit-msg using the step 2. Change line 1 to `#!bin/sh`
