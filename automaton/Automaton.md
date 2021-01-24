---
layout: page
title: 
permalink: /automaton/
---
# Automaton
### THIS IS A MODIFIED, WORK IN PROGRESS, ACTION BASED ON: 
### https://github.com/dmnemec/copy_file_to_another_repo_action by https://github.com/dmnemec

# Example Workflow
```
name: Push File

on: push

jobs:
  copy-file:
    runs-on: ubuntu-latest
    steps:
    - name: Checkout
      uses: actions/checkout@master

    - name: Push a file to another repository
      uses: Emaleth-BSE/Automaton@master
      env:
        API_TOKEN_GITHUB: ${{ secrets.AUTOMATON_TOKEN }}
      with:
        target_repo: 'GithubUsername/My_Awesome_Page.github.io'
        user_email: 'my@email.me'
        user_name: 'GithubUsername'
        target_file_name: 'My_Awesome_Project_Page'
        front_matter_permalink: /about/
        front_matter_layout: page
        front_matter_title: About Me
```

# Variables

#### USER DATA FOR AUTHENTICATION
###  user_name:
    description: 'GitHub username for the commit'
    required: true
###  user_email:
    description: 'Email for the git commit'
    required: true
    
#### TARGET INFO
###  target_repo:
    description: 'Destination repository'
    required: true
###  target_folder:
    description: 'Directory to push the file to'
    required: false
    default: 'automaton'
###  target_branch:
    description: 'Branch to push file to'
    required: false
    default: 'main'
###  target_file_name:
    description: 'Name of the destination file'
    required: false
    
#### FRONT MATTER INFO
###  front_matter_permalink:
    description: 'Front matter permalink'
    required: false
###  front_matter_layout:
    description: 'Front matter layout'
    required: false
###  front_matter_title:
    description: 'Front matter title'
    required: false 
    
#### COMMIT MESSAGE
###  commit_message:
    description: 'A custom message for the commmit'
    required: false

# Behavior Notes
The action will create any destination paths if they don't exist. It will also overwrite existing files if they already exist in the locations being copied to. It will not delete the entire destination repository.
