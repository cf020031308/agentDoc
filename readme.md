# AGENTDOC 1                 2019-04-28                  1.5

## NAME

agentDoc - An agent which makes documents easy to be accessed, modified and searched.

## SYNOPSIS

agentDoc [.=]  
agentDoc [*PATTERN*]  
agentDoc [+-] [*DOCNAME*]  
agentDoc [*SOURCE* | *DOCNAME*] [*DESTINATION* | *DOCNAME*]

## COMMANDS

    agentDoc
        edit the default doc
    agentDoc .
        list all docs
    agentDoc + docname
        create a doc to edit
    agentDoc - docname
        delete a doc
    agentDoc pattern
        search a doc to edit
    agentDoc URL/filepath1/docname1 filepath2/docname2
        append a page/file/doc to an internal doc or an external file
    agentDoc URL/filepath1/docname1 dirpath
        export a page/file/doc to a directory
    agentDoc = [comment]
        sync with git
    agentDoc -h
        help

### About Default Doc

agentDoc guesses the filename if not provided.

When the managed folder is synced with Github Wiki, the default filename is 'home'.  
When the managed folder is a git repository, the default filename is 'readme'.

### About Search

When searching, `agentDoc` looks at the filenames and contents to pick the only file with its name or content exactly or partially matching the pattern, then opens it for editing.

In every search phase if the result contains multiple files, `agentDoc` prints them and quit immediately.

## INSTALLATION

`curl "https://raw.githubusercontent.com/cf020031308/agentDoc/master/agentDoc" -o /usr/local/bin/agentDoc`  
`chmod 755 /usr/local/bin/agentDoc`

Put or link agentDoc as a copy into the folder where you hope to manage documents. Then name the copy as the extension of the managed documents, such as `md` or `txt`. It can also be hidden by being named as `.md`, `.txt`, etc.

And It's recommended to link the copy into `$path` such as `/usr/local/bin/agentDoc` to make it convenient to use.

### Installation Examples

`ln -sf agentDoc /Documents/cheatsheet/.md`  
`ln -sf /Document/cheatsheet/md /usr/local/bin/cheat`  
  Manage cheatsheet in markdown format with command `cheat`

`cp agentDoc /Documents/myproject.wiki.git/md`  
`ln -sf /Document/myproject.wiki.git/md /usr/local/bin/wk`  
  Manage documents of github wiki in markdown format with command `wk`

`ln -sf agentDoc ~/.vim/snippets/snippets`  
`ln -sf ~/.vim/snippets/snippets /usr/local/bin/snippets`  
  Manage vim-snippets with command `snippets`

### Usecases

With different extensions and aliases agentDoc becomes:

1. Shortcut
2. Todo app
3. Cheatsheet
4. Snippet manager
5. Wiki, blog, diary, ...
6. ...

## SPECIALITIES

`agentDoc` leverages the power of Github <https://github.com> and markdown <https://guides.github.com/features/mastering-markdown/>.

1. Properly fix referenced URLs when getting a remote markdown file
2. Automatically manage images referenced in a local markdown file
    1. When editing, you can reference an image relative to your working directory (PWD);
    2. When appending, images referenced in the source file will be copied to the destination folder, and links converted as well.
    3. When syncing, images in the managed folder which are not referenced will be removed before pushing.
3. Friendly with Github
    1. URLs of raw. When getting a remote file from Github or Github Wiki, `agentDoc` guesses the URL of the raw file according to the given URL.
    2. Issue links. When getting a remote file from Github, GFM Issue links will be converted to normal links.

## EXIT STATUS

The `agentDoc` utility exits 0 on success, and >0 if an error occurs.

## SEE ALSO

git(1), curl(1)

## AUTHOR

Written first in May, 2018 by Roy <https://github.com/cf020031308/agentDoc>  
Distributed under the terms of the BSD license.
