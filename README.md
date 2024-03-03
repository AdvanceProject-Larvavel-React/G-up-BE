# Hello G-UP

## Convension

** Ticket code is the code generated autumatically by Jira (or some task management tools, or even self-naming)
- Branch naming: 
  - Categories: 
    - prod (PRODUCTION)
    - stg (STAGING)
    - dev (DEVELOPMENT)
    - Others:
      - feature: used for developing/updating a new feature
      - fix: used for fixing bug
      - chore: used for documents (not code)
    - **format: [tag]/[ticket code]-#[child ticket code]**
    - example: 
      - feature/GUP-1 (US)
      - feature/GUP-1-#GUP-2
      - fix/GUP-1-#GUP-3
  - Pushing:
    - Create a pull request
    - Reviewer -> Accepted the PR
    - Merge PR
    - Notify to all members -> update the latest code from branch 'dev'
  - Commit:
    - **format: [tags]([ticket code]): short description**
    - example: 
      - feature(GUP-1): show featured products
      - fix(GUP-1): fix layout
    
# Fix conflict
** Notice: Always pull the latest code from the branch DEV when someone merged PR

## Method 1: rebase

- git pull origin [branch name] --rebase
- Choose the suitable code
- git rebase --continue (Maybe multiple times -> Return step 2)
- git push origin [branch name] -f

## Method 2: reset

** Both of --soft (reset commit history and keep the changes) and --hard (delete all changes and can not restore) are acceptable

- Copy the commit hash that you want to back the code
- git reset --soft/--hard [commit hash]
- git stash 
- git pull origin [branch name]
- git stash apply
- git commit -m "something"
- git push origin [branch name] -f
  
# Research some advanced git commands
- git cherry-pick
- git revert
- git stash
- git fetch
- git tag