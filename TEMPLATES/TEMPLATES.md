---
cssclasses:
  - list-cards
prefer-view: read
---
%% Begin Landmark %%
- [[ArticleNote]]
- [[Book Note]]
- [[CourseNote]]
- [[Daily Note]]
- [[FolderNote]]
- [[IndexNote]]
- [[RegularNote]]

%% End Landmark %%

```meta-bind-button
style: default
label: Create Normal Note
actions:
  - type: templaterCreateNote
    templateFile: "TEMPLATES/RegularNote.md"
    folderPath: /
    fileName: "New Lecture Note - RENAME ME"
```

```meta-bind-button
style: default
label: Create Folder Note
actions:
  - type: templaterCreateNote
    templateFile: "TEMPLATES/FolderNote.md"
    folderPath: /
    fileName: "New Lecture Note - RENAME ME"
```

```meta-bind-button
style: default
label: Create Article Note
actions:
  - type: templaterCreateNote
    templateFile: "TEMPLATES/ArticleNote.md"
    folderPath: /
    fileName: "New Lecture Note - RENAME ME"
```

```meta-bind-button
style: default
label: Create Index Note
actions:
  - type: templaterCreateNote
    templateFile: "TEMPLATES/IndexNote.md"
    folderPath: /
    fileName: "New Lecture Note - RENAME ME"
```

```meta-bind-button
style: default
label: Create Course Note
actions:
  - type: templaterCreateNote
    templateFile: "TEMPLATES/CourseNote.md"
    folderPath: /
    fileName: "New Lecture Note - RENAME ME"
```