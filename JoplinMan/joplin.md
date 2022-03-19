% JOPLIN(1) joplin-cli 2.6.2
% joplinapp.org
% Mar 2022

# NAME

**joplin** - Note taking application

# SYNOPSIS

**joplin**\
**joplin** COMMAND [options]\
**joplin** COMMAND SUBCOMMAND [options]

# DESCRIPTION

Joplin is a free, open source note taking and to-do application, which can handle a large number of notes organised into notebooks. The notes are searchable, can be copied, tagged and modified with your own text editor.

Notes exported from Evernote via .enex files can be imported into Joplin, including the formatted content (which is converted to Markdown), resources (images, attachments, etc.) and complete metadata (geolocation, updated time, created time, etc.). Plain Markdown files can also be imported.

The notes can be synchronised with various targets including the file system (for example with a network directory), Nextcloud, Dropbox, OneDrive or WebDAV. When synchronising the notes, notebooks, tags and other metadata are saved to plain text files which can be easily inspected, backed up and moved around.

# COMMANDS

**attach** *note* *file*

: Attaches the given file to the note.

**batch** *file-path*

: Runs the commands contained in the text file. There should be one command per line.

**cat** *note* **[-options]**

: Displays the given note

    *Options*
    
      **-v**, **--verbose** Displays the complete information about note.
  
**config** **{name}** **{value}** **[-options]**

: Gets or sets a config value. If **{value}** is not provided, it will show the value of **{name}**. If neither **{name}** nor **{value}** is provided, it will list the current configuration.

    *Options*

      **-v**, **--verbose**    

      Also displays unset and hidden config variables.

      **--export**             

      Writes all settings to STDOUT as JSON including secure variables.

      **--import**

      Reads in JSON formatting settings from STDIN.

      **--import-file** *file*

      Reads in settings from *file*. *file* must contain valid JSON.
  
      *Possible keys/values*:

      **sync.target**

      Synchronisation target.\
      The target to synchronise to. Each sync target may have additional parameters which are named as `sync.NUM.NAME` (all documented below).\
      Type: Enum.\
      Possible values: 0 ((None)), 2 (File system), 3 (OneDrive), 5 (Nextcloud), 6 (WebDAV), 7 (Dropbox), 8 (S3 (Beta)), 9 (Joplin Server (Beta)), 10 (Joplin Cloud).\
      Default: 0

      **sync.2.path**

      Directory to synchronise with (absolute path).\
      Attention: If you change this location, make sure you copy all your content to it before syncing, otherwise all files will be removed! See the FAQ for more details: https://joplinapp.org/faq/\
      Type: string.

      **sync.5.path**

      Nextcloud WebDAV URL.\
      Attention: If you change this location, make sure you copy all your content to it before syncing, otherwise all files will be removed! See the FAQ for more details: https://joplinapp.org/faq/\
      Type: string.

      **sync.5.username**

      Nextcloud username.
      Type: string.

      **sync.6.path**

      WebDAV URL.\
      Attention: If you change this location, make sure you copy all your content to it before syncing, otherwise all files will be removed! See the FAQ for more details: https://joplinapp.org/faq/\
      Type: string.

      **sync.6.username**

      WebDAV username.\
      Type: string.

      **sync.6.password**

      WebDAV password.\
      Type: string.

      **sync.8.path**

      AWS S3 bucket.\
      Attention: If you change this location, make sure you copy all your content to it before syncing, otherwise all files will be removed! See the FAQ for more details: https://joplinapp.org/faq/\
      Type: string.

      **sync.8.url**

      AWS S3 URL.\
      Type: string.\
      Default: "https://s3.amazonaws.com/"

      **sync.8.region**

      AWS region.\
      Type: string.

      **sync.8.username**

      AWS access key.\
      Type: string.

      **sync.8.password**

      AWS secret key.\
      Type: string.

      **sync.8.forcePathStyle**

      Force path style.\
      Type: bool.\
      Default: false

      **sync.9.path**

      Joplin Server URL.\
      Attention: If you change this location, make sure you copy all your content to it before syncing, otherwise all files will be removed! See the FAQ for more details: https://joplinapp.org/faq/\
      Type: string.

      **sync.9.username**
      
      Joplin Server email.\
      Type: string.

      **sync.9.password**

      Joplin Server password.\
      Type: string.

      **sync.10.username**

      Joplin Cloud email.\
      Type: string.

      **sync.10.password**

      Joplin Cloud password.\
      Type: string.

      **sync.maxConcurrentConnections**

      Max concurrent connections.\
      Type: int.\
      Default: 5

      **locale**   

      Language.\
      Please see localisation section on https://joplinapp.org/help/#localisation for info on translation completion progress\
      Type: Enum.\
      Possible values: ar (Arabic), eu (Basque), bs_BA (Bosnian), bg_BG (Bulgarian), ca (Catalan), hr_HR (Croatian), cs_CZ (Czech), da_DK (Dansk), de_DE (Deutsch), et_EE (Eesti Keel), en_GB (English (UK)), en_US (English (US)), es_ES (Español), eo (Esperanto), fi_FI (Finnish), fr_FR (Français), gl_ES (Galician), id_ID (Indonesian), it_IT (Italiano), nl_BE (Nederlands), nl_NL (Nederlands), nb_NO (Norwegian), fa (Persian), pl_PL (Polski), pt_PT (Português), pt_BR (Português (Brasil)), ro (Română), sl_SI (Slovenian), sv (Svenska), th_TH (Thai), vi (Tiếng Việt), tr_TR (Türkçe), el_GR (Ελληνικά), ru_RU (Русский), sr_RS (српски језик), zh_CN (中文 (简体)), zh_TW (中文 (繁體)), ja_JP (日本語), ko (한국말).\
       Default: "en_GB"

       **dateFormat**

       Date format.\
       Type: Enum.\
       Possible values: DD/MM/YYYY (30/01/2017), DD/MM/YY (30/01/17), MM/DD/YYYY (01/30/2017), MM/DD/YY (01/30/17), YYYY-MM-DD (2017-01-30), DD.MM.YYYY (30.01.2017), YYYY.MM.DD (2017.01.30), YYMMDD (170130), YYYY/MM/DD (2017/01/30). Default: "DD/MM/YYYY"

       **timeFormat**

       Time format.\
       Type: Enum.\
       Possible values: HH:mm (20:30), h:mm A (8:30 PM).\
       Default: "HH:mm"

       **uncompletedTodosOnTop**

       Uncompleted to-dos on top.\
       Type: bool.\
       Default: true

       **showCompletedTodos**

       Show compelted to-dos.\
       Type: bool.\
       Default: true

       **notes.sortOrder.field**

       Sort notes by.\
       Type: Enum.\
       Possible values: user_updated_time (Updated date), user_created_time (Created date), title (Title), order (Custom order).\
       Default: "user_updated_time"

       **notes.sortOrder.reverse**

       Reverse sort order.\
       Type: bool.\
       Default: true

       **folders.sortOrder.field**

       Sort notebooks by.\
       Type: Enum.\
       Possible values: title (Title), last_note_user_updated_time (Updated date).\
       Default: "title"

       **folders.sortOrder.reverse**

       Reverse sort order.\
       Type: bool.\
       Default: false

       **trackLocation**

       Save geo-location with notes.\
       Type: bool.\
       Default: true

       **sync.interval**

       Synchronisation interval.\
       Type: Enum.\
       Possible values: 0 (Disabled), 300 (5 minutes), 600 (10 minutes), 1800 (30 minutes), 3600 (1 hour), 43200 (12 hours), 86400 (24 hours).\
       Default: 300

       **editor**

       Text editor command.\
       The editor command (may include arguments) that will be used to open a note. If none is provided it will try to auto-detect the default editor.\
       Type: string.

       **net.customCertificates**

       Custom TLS certificates.\
       Comma-separated list of paths to directories to load the certificates from, or path to individual cert files. For example: /my/cert_dir, /other/custom.pem. Note that if you make changes to the TLS settings, you must save your changes before clicking on "Check synchronisation configuration".\
       Type: string.

       **net.ignoreTlsErrors**

       Ignore TLS certificate errors.\
       Type: bool.\
       Default: false

       **sync.wipeOutFailSafe**

       Fail-safe.\
       Fail-safe: Do not wipe out local data when sync target is empty (often the result of a misconfiguration or bug)\
       Type: bool.\
       Default: true

       **revisionService.enabled**

       Enable note history.\
       Type: bool.
       Default: true

       **revisionService.ttlDays**

       Keep note history for.\
       Type: int.\
       Default: 90

       **layout.folderList.factor**

       Notebook list growth factor.\
       The factor property sets how the item will grow or shrink to fit the available space in its container with respect to the other items. Thus an item with a factor of 2 will take twice as much space as an item with a factor of 1.Restart app to see changes.\
       Type: int.\
       Default: 1

       **layout.noteList.factor**

       Note list growth factor.\
       The factor property sets how the item will grow or shrink to fit the available space in its container with respect to the other items. Thus an item with a factor of 2 will take twice as much space as an item with a factor of 1.Restart app to see changes.\
       Type: int.\
       Default: 1

       **layout.note.factor**

       Note area list growth factor.\
       The factor property sets how the item will grow or shrink to fit the available space in its container with respect to the other items. Thus an item with a factor of 2 will take twice as much space as an item with a factor of 1.Restart app to see changes.\
       Type: int.\
       Default: 2

**cp** *note* *notebook*

: Duplicates the notes matching *note* to *notebook*. If no notebook is specified then the note is duplicated in the current notebook.

**done** *note*

: Marks a to-do as done.

**e2ee** **{command}** **[-option]**

: Manages E2EE configuration. Commands are `enable`, `disable`, `decrypt`, `status`, `decrypt-file`, and `target-status`.

    *Options*

      **-p**, **--password** *password* Use this password as master password (For security reasons, it is not recommended to use this option).

      **-v**, **--verbose** More verbose output for the `target-status` command

      **-o**, **--output** *directory* Output directory

      **--retry-failed-items** Applies to the `decrypt` command - retries decrypting items that previously could not be decrypted.

**edit** *note*

: Edit note.

**export** *path* **[-option]**

: Exports Joplin data to the given path. By default, it will export the complete database including notebooks, notes, tags and resources.

    *Options*

      **--format** *format* Destination format: jex (Joplin Export File), raw (Joplin Export Directory), md (Markdown), md_frontmatter (Markdown + Front Matter)

      **--note** *note* Exports only the given note.

      **--notebook** *notebook* Exports only the given notebook

**geoloc** *note*

: Displays a geolocation URL for the note.

**help** **{command}**

: Displays usage information.

**import** *path* *notebook* **[-option]**

: Imports data into Joplin.

    *Options*

      **--format** *format* Source format: auto, jex, md, md_frontmatter, raw, enex, enex

      **-f**, **--force** Do not ask for confirmation.

      **-output-format** *output-format* Output format: md, html

**ls** *note-pattern*

: Displays the notes in the current notebook. Use `ls /` to display the list of notebooks.

    *Options*

      **-n**, **--limit** *num* Displays only the first top *num* notes.

      **-s**, **--sort** *field* Sorts the item by *field* (e.g. title, updated_time, created_time).

      **-r**, **--reverse** Reverses the sorting order

      **-t**, **--type** *type* Displays only the items of the specific type(s). Can be `n` for notes, `t` for to-dos, or `nt` for notes and to-dos (e.g. `-tt` would display only the to-dos while `-tnt` would display notes and to-dos.

      **-f**, **--format** *format* Either "text" or "json"

      **-l**, **--long** Use long list format. Format is ID, NOTE_COUNT (for notebook), DATE, TODO_CHECKED (for to-dos), TITLE

**mkbook** *new-notebook*

: Creates a new notebook.

**mknote** *new-note*

: Creates a new note.

**mktodo** *new-todo*

: Creates a new to-do.

**mv** *note* *notebook*

: Move the notes matching *note* to *notebook*.

**ren** *item* *name*

: Renames the given *item* (note or notebook) to *name*

**rmbook** *notebook* **[-option]**

: Deletes the given notebook

    *Options*

      **-f**, **--force** Deletes the notebook without asking for confirmation

**rmnote** *note-pattern*

: Deletes the notes matching *note-pattern*.

    *Options*

      **-f**, **--force** Deletes the notes without asking for confirmation

**server** **{command}**

: Start, stop or check the API server. To specifify on which port it should run, set the api.port config variable. Commands are (start|stop|status). This is an experimental feature - use at your own risks! It is recommended that the server runs off its own separate profile so that no two CLI instances access that profile at the same time. Use --profile to specify the profile path.

**set** *note* **{name}** *value*

: Sets the property *name* of the given *note* to the given *value*. Possible properties are:

    parent_id (text), title (text), body (text), created_time (int), updated_time (int), is_conflict (int), latitude (numeric), longitude (numeric), altitude (numeric), author (text), source_url (text), is_todo (int), todo_due (int), todo_completed (int), source (text), source_application (text), application_data (text), order (numeric), user_created_time (int), user_updated_time (int), encryption_cipher_text (text), encryption_applied (int), markup_language (int), is_shared (int), share_id (text), conflict_original_id (text), master_key_id (text)

**status**

: Displays summary about the notes and notebooks.

**sync** **[-option]**

: Synchronises with remote storage.

    *Options*

    **--target** *target* Sync to the provided target (defaults to sync.target config value)

    **--upgrade** Upgrade the sync target to the latest version.

    **--use-lock** *value* Disable local locks that prevent multiple clients from synchronising at the same time (Default = 1)

**tag** **{tag-command}** *tag* *note* **[-option]**

: **{tag-command}** can be "add", "remove", "list", or "notetags" to assign or remove *tag* from *note*, to list notes associated with *tag*, or to list tags associated with *note*. The command `tag list` can be used to list all the tags (use -l for long option)

    *Options*

    **-l**, **--long** Use long list format. Format is ID, NOTE_COUNT (for notebook), DATE, TODO_CHECKED (for to-dos), TITLE

**todo** **{todo-command** *note-pattern*

: **{todo-command}** can either be "toggle" or "clear". Use "toggle" to toggle the given to-do between completed and uncompleted state (if the target is a regular note it will be converted to a to-do). Use "clear" to convert the to-do back to a regular note.

**undone** *note*

: Marks a to-do as non-completed.

**use** *notebook*

: Switches to *notebook* - all further operations will happen within this notebook.

**version**

: Displays version information

# EXAMPLES

## COMMAND-LINE MODE

Used from within the Joplin terminal application by typing **:**.

**mknote** "Wednesday's meeting"

: Creates a new note with the title "Wednesday's meeting"

**mktodo** "Buy bread"

: Create a new to-do

**mv** $n "Personal"

: Move the currently selected note ($n) to the notebook with title "Personal"

**ren** $b "Something"

: Rename the currently selected notebook ($b) to "Something"

**attach** $n /home/laurent/pictures/Vacation12.jpg

: Attach a local file to the currently selected note ($n)

**config** editor "subl -w"

: Change the current editor to Sublime Text

## SHELL MODE

**joplin mkbook** "My notebook"
**joplin use** "My notebook"
**joplin mknote** "My note"

: Create a new note "My note" in the notebook "My notebook"

**joplin ls -l**

: View the newly created note
    fe889 07/23/3027 27:57 My Note

**joplin set** fe889 title "New title"

: Gives the title "New title" to the note

# FILES

**~/.config/joplin**

: Local data, settings and configuration

**~/.joplin-bin**

: Application binary (also has a symlink from ~./joplin-bin/bin/joplin to /usr/bin/joplin)

# ISSUES

For additional help visit https://joplinapp.org/help

For support please visit the forum at https://discourse.joplinapp.org/

For bugs and issues please report at https://github.com/laurent22/joplin/issues

# COPYRIGHT

Copyright © 2016-2022 Laurent Cozic

License MIT
