---
starts_on: 2025-08-10
end_on: 2025-08-15
estimates: 5 days
task_id: 
type: Task
status: Todo
tags:
  - task_notes
date: 2025-08-10
---
# Overview

> [!warning]+ Overdue Task Or Due Today
>
> ```dataviewjs
> const currentFileName = dv.current().file.name;
> dv.pages("")
.filter(page => page.file.name === currentFileName) // Filter pages by current file
.file.tasks
.filter(task => !task.completed && task.due && task.due <= dv.date("today")) // Filter tasks that are not completed and due today or earlier
.sort(task => task.due, 'asc') // Sort by due date in ascending order
.forEach(task => dv.taskList([task], false)); // Render tasks;
> ```

> [!todo]+ Started/Starting Today But Not Completed Tasks
>
> ```dataviewjs
> const currentFileName = dv.current().file.name;
> dv.pages("")
.filter(page => page.file.name === currentFileName) // Filter pages by current file
.file.tasks
.filter(task => !task.completed && task.start && task.start <= dv.date("today"))
.sort(task => task.start, 'asc') // Sort by due date in ascending order
.forEach(task => dv.taskList([task], false)); // Render tasks;
> ```

> [!success]+ Completed Task
> ```dataviewjs
> const currentFileName = dv.current().file.name;
> dv.pages("")
.filter(page => page.file.name === currentFileName) // Filter pages by current file
.file.tasks
.filter(task => task.completed)
.sort(task => task.due, 'asc') // Sort by due date in ascending order
.forEach(task => dv.taskList([task], false)); // Render tasks;
> ```

___
# Requirements

___
# Sub Task
___
# Ideas, Discussions And Notes

___
# Example Code Blocks

___
# Web Links

___

