---
layout: page
title: "Explore Apache Zeppelin UI"
description: "If you are new to Apache Zeppelin, this document will guide you about the basic components of Zeppelin one by one."
group: quickstart
---
<!--
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->
{% include JB/setup %}

# Explore Apache Zeppelin UI (Classic UI)

<div id="toc"></div>

## How to Enable and Switch to the Classic UI

Starting from Zeppelin 0.12.0, this UI has become optional. To use this UI, please build with the following profile:

```
-Pweb-classic
```

Afterward, you can switch to the classic UI via the `Swtich to Classic UI` button in the settings menu of the new UI app.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/switch_to_classic_ui.png" width="130" />


### Configuring the default UI

Zeppelin allows you to configure the default, especially for users who prefer the classic UI.

To set the default UI to classic, add the following property to the `zeppelin-site.xml` file:

```xml
<property>
  <name>zeppelin.default.ui</name>
  <value>classic</value>
  <description>Default UI for Zeppelin. Options: classic or new. Default configuration is 'new'</description>
</property>
```

## Main home

The first time you connect to Zeppelin ([default installations start on http://localhost:8080](http://localhost:8080/)), you'll land at the main page similar to the below screen capture.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/homepage.png" />

On the left of the page are listed all existing notes. Those notes are stored by default in the `$ZEPPELIN_HOME/notebook` folder.

You can filter them by name using the input text form. You can also create a new note, refresh the list of existing notes
(in case you manually copy them into the `$ZEPPELIN_HOME/notebook` folder) and import a note.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/notes_management.png" width="230px" />

When clicking on `Import Note` link, a new dialog open. From there you can import your note from local disk or from a remote location
if you provide the URL.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/note_import_dialog.png" />

By default, the name of the imported note is the same as the original note but you can override it by providing a new name.

<br />
## Menus

### Notebook

The `Notebook` menu proposes almost the same features as the note management section in the home page. From the drop-down menu you can:

1. Open a selected note
2. Filter node by name
3. Create a new note

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/notebook_menu.png" width="170px" />

### Settings
This menu gives you access to settings and displays information about Zeppelin. User name is set to `anonymous` if you use default shiro configuration. If you want to set up authentication, see [Shiro Authentication](../setup/security/shiro_authentication.html).

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/settings_menu.png" width="170px" />

#### About Zeppelin

You can check Zeppelin version in this menu.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/about_menu.png" width="450px" />

#### Interpreter

In this menu you can:

1. Configure existing **interpreter instance**
2. Add/remove **interpreter instances**

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/interpreter_menu.png" />

#### Credential

This menu allows you to save credentials for data sources which are passed to interpreters.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/credential_menu.png" />

#### Configuration

This menu displays all the Zeppelin configuration that are set in the config file `$ZEPPELIN_HOME/conf/zeppelin-site.xml`

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/configuration_menu.png" />


<br />
## Note Layout

Each Zeppelin note is composed of 1 .. N paragraphs. The note can be viewed as a paragraph container.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/note_paragraph_layout.png" />

### Paragraph

Each paragraph consists of 2 sections: `code section` where you put your source code and `result section` where you can see the result of the code execution.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/paragraph_layout.png" />

On the top-right corner of each paragraph there are some commands to:

* execute the paragraph code
* hide/show `code section`
* hide/show `result section`
* configure the paragraph

To configure the paragraph, just click on the gear icon:

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/paragraph_configuration_dialog.png" width="180px" />

From this dialog, you can (in descending order):

* find the **paragraph id** ( **20150924-163507_134879501** )
* control paragraph width. Since Zeppelin is using the grid system of **Twitter Bootstrap**, each paragraph width can be changed from 1 to 12
* move the paragraph 1 level up
* move the paragraph 1 level down
* create a new paragraph
* change paragraph title
* show/hide line number in the `code section`
* disable the run button for this paragraph
* export the current paragraph as an **iframe** and open the **iframe** in a new window
* clear the `result section`
* delete the current paragraph

### Note toolbar

At the top of the note, you can find a toolbar which exposes command buttons as well as configuration, security and display options.

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/note_toolbar.png" />

On the far right is displayed the note name, just click on it to reveal the input form and update it.

In the middle of the toolbar you can find the command buttons:

* execute all the paragraphs **sequentially**, in their display order
* hide/show `code section` of all paragraphs
* hide/show `result section` of all paragraphs
* clear the `result section` of all paragraphs
* clone the current note
* export the current note to a JSON file. _Please note that the `code section` and `result section` of all paragraphs will be exported. If you have heavy data in the `result section` of some paragraphs, it is recommended to clean them before exporting
* commit the current node content
* delete the note
* schedule the execution of **all paragraph** using a CRON syntax

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/note_commands.png" width="300px"/>

On the right of the note tool bar you can find configuration icons:

* display all the keyboard shortcuts
* configure the interpreters binding to the current note
* configure the note permissions
* switch the node display mode between `default`, `simple` and `report`

<img src="{{BASE_PATH}}/assets/themes/zeppelin/img/ui-img/note_configuration.png" width="180px"/>
