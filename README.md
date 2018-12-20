![Calf Logo](./logo.png)

# calf-cli
一个轻量、简单的calf项目构建工具.

# 安装 (Installation)
```
git clone https://github.com/eventao/calf-cli.git

cd calf-cli && npm install

npm link
```

# 使用 (Usage)
Open your terminal and type `calf` or `calf -h` , you'll see the help infomation below:
```
  Usage: calf <command>


  Commands:

    add|a      Add a new template
    list|l     List all the templates
    init|i     Generate a new project
    delete|d   Delete a template

  Options:

    -h, --help     output usage information
    -V, --version  output the version number
```

# 命令 (Commands)
### add | a
This command would help you to add a new template to the `templates.json`, which will be used by Calf to generate projects.
```
$ calf add
```
```
 /*  your template's name */
Template name: my-tpl

 /* your template's git https link, note that it ends with .git */
Git https link:  https://gitxxx/somebody/my-tpl.git 

 /* your template's branch */
Branch: master 
```
Once confirm you'll see the message like below:
```
The last template list is:

{ tpl:
   { 'my-tpl-name':
      { url: 'https://gitxxx/somebody/my-tpl.git',
        branch: 'master' } } }
```
Now you've added a new template to Calf successfully.

### list | l
It shows you the templates list.
```
$ calf list

{ tpl:
   { 'my-tpl-name':
      { url: 'https://gitxxx/somebody/my-tpl.git',
        branch: 'master' } } }
```

### init | i
After adding new templates, you could use this command to generate your own project by choosing template.
```
$ calf init

/* enter a template name which was added by yourself */
Template name: my-tpl-name

/* your project name */
Project name: my-new-project
```
After enter correct template name and confirm, you'll see the message below:
```
Start generating...

 √ Generation completed!

 cd my-new-project && npm install
```
It's easy, right?

### delete | d
To delete a template, you could use this command:
```
$ calf delete
```
and type the template name you want to delete:
```
Template name: my-tpl-name
```
if the name exist, you will see:
```
Template deleted!
The last template list is:

{ tpl:
   { 'my-tpl-name': undefined } }
```
once a template is `undefined`, it means you've deleted it successfully.

# Template
The most important part of Calf is `template`. All templates' infomation were list in the `templates.json`.
A template means a project sample, which has a simple or complex file structure.

You can create your own templates repository, and push your templates in different branches. All you need to do then is to add the templates into Calf's `templates.json`.

# License
MIT.










