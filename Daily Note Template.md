---
tags:
  - dailies
created: <% tp.file.creation_date() %>
sleep: 
reading: 
exercise: 
drawing: 
screen_time: 
studying:
---
## <% moment(tp.file.title, "DD-MM-YYYY").format('dddd Do MMMM - YYYY') %>
- << [[Daily notes/2025/10/<% fileDate = moment(tp.file.title, 'DD-MM-YYYY').subtract(1, 'd').format('DD-MM-YYYY') %>|Yesterday]] | [[Daily notes/2025/10/<% fileDate = moment(tp.file.title, 'DD-MM-YYYY').add(1, 'd').format('DD-MM-YYYY') %>|Tomorrow]] >>


![Uncle Iroh|320x320](https://media.tenor.com/_PEwdam8b84AAAAC/iroh-tea.gif)

>[!Quote]+ Quote of the day	
 <% tp.web.daily_quote() %>



*Remember your dreams.*
## ボッチの想い:
- 


## Goals
```dataview  
Table without ID L.text As "Today's Goals"  
FROM [[dailies]]  
FLATTEN file.lists As L  
WHERE meta(L.section).subpath="Plans for tomorrow" and file.name="<% fileDate = moment(tp.file.title, 'DD-MM-YYYY').subtract(1, 'd').format('DD-MM-YYYY') %>" and L.text != "Goal 1" and L.text != "Goal 2"

```


# End of day routine:
[[End of Work Routine]]


## Lists 
> [!success]+ What did I accomplish today?  
> - 1  
> - 2  

> [!tip]  Highlights of the day:
> - 1
> - 2

> [!done] Tasks done
```dataviewjs
const filename = dv.current().file.name;
if (filename.includes("-")) {
    const parts = filename.split("-");
    const date = `${parts[2]}-${parts[1]}-${parts[0]}`;

    dv.taskList(
        dv.pages().file.tasks
        .where(t => t.completed 
            && t.completion?.toISODate() === date
            && !/^(\d{1,2}:\d{2}\s-\s\d{1,2}:\d{2})/.test(t.text)
        ),
        true
    );
} else {
    dv.paragraph("⚠️ Save this note with a valid date filename to show tasks.");
}
```

## Plans for tomorrow:
> [!note]+ Action Plan
> - Goal 1
> - Goal 2


## Room for Improvement
	- What could I have done to make today better?
		- 
	- What or who took my time that wasn't in the plan?
		- 


[[dailies]] 
