---
title: Automaton
layout: page
collection: gh-repos
permalink: /automaton/
---
##### THIS IS A MODIFIED, WORK IN PROGRESS, ACTION BASED ON: 
##### https://github.com/dmnemec/copy_file_to_another_repo_action by https://github.com/dmnemec

##### This action is designed to be used with github pages and jekyll
<!--more-->

### Features
##### - Copy README.md from repository A into repository B, directory C
##### - Rename copied README.md to any arbitrary name (will always be a markdown file) (default = repository name)
##### - Respect already present filed named README.md (reneaming happens before copying)


### Variables
#### USER DATA FOR COMMIT MSG
#####  user_name:
    description: 'GitHub username for the commit'
    required: true
    default: 'Automaton'
    
#####  user_email:
    description: 'Email for the git commit'
    required: true
    default: '<>'
    
#### TARGET INFO
#####  target_repo:
    description: 'Destination repository'
    required: true
    
#####  target_folder:
    description: 'Directory to push the file to'
    required: false
    default: 'automaton'
    
#####  target_branch:
    description: 'Branch to push file to'
    required: false
    default: 'main'
    
#####  target_file_name:
    description: 'Name of the destination file'
    required: false
    
#### FRONT MATTER INFO
#####  front_matter_permalink:
    description: 'Front matter permalink'
    required: false
    default: ''
    
#####  front_matter_layout:
    description: 'Front matter layout'
    required: false
    default: 'page'
    
#####  front_matter_title:
    description: 'Front matter title'
    required: false
    default: '' 
    
#### COMMIT MESSAGE
#####  commit_message:
    description: 'A custom message for the commmit'
    required: false


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
      uses: Emaleth/Automaton@master
      env:
        API_TOKEN_GITHUB: '${{ secrets.AUTOMATON_TOKEN }}'
      with:
        target_repo: 'GithubUsername/My_Awesome_Page.github.io'
        user_email: 'my@email.me'
        user_name: 'GithubUsername'
        target_file_name: 'My_Awesome_Project_Page'
        front_matter_permalink: /about/
        front_matter_layout: page
        front_matter_title: About Me
```

