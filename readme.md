# AGENTDOC 1                 2018-06-12                  1.2

## NAME

agentDoc - Document manager majored in cheatsheet and github wiki

## SYNOPSIS

agentDoc [.=]  
agentDoc [*PATTERN*]  
agentDoc [+-] [*DOCNAME*]  
agentDoc [*SOURCE* | *DOCNAME*] [*DESTINATION* | *DOCNAME*]

## EXAMPLES

`ln -sf agentDoc /Documents/cheatsheet/.md`  
`ln -sf /Document/cheatsheet/md /usr/local/bin/cheat`  
  Manage cheatsheet in markdown format with command `cheat`

`cp agentDoc /Documents/myproject.wiki.git/md`  
`ln -sf /Document/myproject.wiki.git/md /usr/local/bin/wk`  
  Manage documents of github wiki in markdown format with command `wk`

`ln -sf agentDoc ~/.vim/snippets/snippets`  
`ln -sf ~/.vim/snippets/snippets /usr/local/bin/snippets`  
  Manage vim-snippets with command `snippets`

## DESCRIPTION

Put or link agentDoc into the folder where to manage documents and name it to the suffix of the documents, such as md or txt.

You can also hide your agentDoc by naming it as a hidden file, such as .md or .txt. It's the same.

It's recommended to link it into $path such as /usr/local/bin/agentDoc.

Then the following commands are available:

    edit the default doc    : agentDoc
    list all docs           : agentDoc .
    create a doc to edit    : agentDoc + docname
    delete a doc            : agentDoc - docname
    search a doc to edit    : agentDoc pattern
    append a web to a doc   : agentDoc URL docname
    append a file to a doc  : agentDoc path docname
    move a doc to external  : agentDoc docname directory
    append a doc to another : agentDoc docname1 docname2
    sync with git           : agentDoc =
    help                    : agentDoc -h

### Usecases

With different suffices and commands agentDoc becomes:

1. Shortcut
2. Todo app
3. Cheatsheet
4. Snippet manager
5. Wiki, blog, diary, ...
6. ...

### Image migrating in markdown

When editing documents in markdown, paths of the pictures should be relevant to pwd, not to the managed folder.  
After editing, agentDoc will migrate pictures into the managed folders.

When migrating a doc to another directory out of the managed folder, agentDoc migrates related pictures to it, too.

## EXIT STATUS

The agentDoc utility exits 0 on success, and >0 if an error occurs.

## SEE ALSO

vim(1), git(1), curl(1)

## AUTHOR

Written in May, 2018 by Roy <https://github.com/cf020031308/agentDoc>  
Distributed under the terms of the BSD license.
