---
created: 2023-02-08T02:21:40 (UTC +08:00)
tags: []
source: https://github.com/rxhanson/Rectangle/wiki/Todo-Mode
author: 
---

# Todo Mode · rxhanson/Rectangle Wiki

---
New in v0.42, you can use Rectangle to keep a chosen application (presumably, your todo application) visible on the right of your primary screen at all times.

Currently, this feature is hidden. To unhide this feature, execute this Terminal command and restart the app:

```
defaults write com.knollsoft.Rectangle todo -int 1

```

It looks like this:

![](https://user-images.githubusercontent.com/6983/105098579-1e333f00-5a5f-11eb-97ef-c93d0eee4684.png)

In Todo Mode, all other movement shortcuts on the primary display will treat the display as shrunken by the size of the todo sidebar.

To enable Todo Mode:

1.  Activate your chosen todo application.
2.  In the Rectangle menu, select "Use \[Application\] as Todo App".
3.  In the Rectangle menu, enable Todo Mode.

While in Todo Mode, you can force a reflow of the Todo Mode layout (to correct the placement of some errant windows, for example) by selecting "Reflow Todo" in the Rectangle menu, or activating the associated keyboard shortcut.

You can adjust the width of the todo application with the following command and an app restart:

```
defaults write com.knollsoft.Rectangle todoSidebarWidth -float 400

```

This feature was created by Patrick Collison and Nat Friedman 👍
