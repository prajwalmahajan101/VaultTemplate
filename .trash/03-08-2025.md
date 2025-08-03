---
tags:
  - daily_note
---
## <% moment(tp.file.title, "DD-MM-YYYY").format("dddd Do MMMM YYYY") %>


<< [[<% moment(tp.file.title, 'DD-MM-YYYY').subtract(1, 'd').format('[00_Daily_Notes]/YYYY/MMMM/DD-MM-YYYY') %>|Yesterday]] | [[<% moment(tp.file.title, 'DD-MM-YYYY').add(1, 'd').format('[00_Daily_Notes]/YYYY/MMMM/DD-MM-YYYY') %>|Tomorrow]] >>


> [!warning]+ Overdue
> ```tasks
> not done
> sort by due date
> due before <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
> ```

> [!warning]+ Due Today
> ```tasks
> not done
> due on <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
> sort by due date
> ```

> [!todo]+ In Progress
> ```tasks
> not done
> starts before <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
> due after <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
> sort by priority
> ```

> [!todo]+ Starts Today
> ```tasks
> not done
> starts on <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
> due after <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
> sort by priority
> ```

> [!Warning]+ Unscheduled Tasks
 > ```tasks
 > not done
 > no due date
 > sort by priority
 > ```

> [!success]+ Tasks Done Today
> ```tasks 
> done <% moment(tp.file.title, 'DD-MM-YYYY').format('YYYY-MM-DD') %>
>  hide due date
>  ```


___
## Notes


___
## Reminders And Tasks


___
## Meetings Scheduled Today

___
