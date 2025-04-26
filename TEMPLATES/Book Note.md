---
cssclasses:
  - list-cards
  - cards-col-2
prefer-view: read
Description: 
tags:
  - Book
---
<%*
const title = await tp.system.prompt("Title");

const folders = this.app.vault.getAllLoadedFiles()
  .filter(f => f.children) // This filters to folders
  .map(f => f.path);       // Then maps to their paths

const folder = await tp.system.suggester(folders, folders);

// Rename and move the current file
await tp.file.rename(title);
await tp.file.move(`${folder}/${title}`);
%>