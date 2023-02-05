原文地址 [Archive Hook bookmarks with DEVONthink – Decoding](https://decoding.io/2022/02/archive-hook-bookmarks-with-devonthink/)

I was in a [Tinderbox Meetup](https://vimeo.com/679537458) last week, which was more about [Hook](https://hookproductivity.com/) than [Tinderbox](https://www.eastgate.com/Tinderbox/). I’m not a Tinderbox user, but I’m interested in how other people use their tools.  
上周我参加了一个 Tinderbox 聚会，更多的是关于 Hook 而不是 Tinderbox。我不是 Tinderbox 用户，但我对其他人如何使用他们的工具很感兴趣。

In the middle of the call, somebody had a question about Hook bookmarks. More specifically, can Hook archive its bookmarks as [archive.org](https://archive.org/) does with websites in general? Well there is no feature like that in Hook, and to be honest, doesn’t even need to be, because Hook has great [Apple Script integration](https://hookproductivity.com/help/automation/hooks-applescript-dictionary/), so we can query bookmarks from its database.  
在通话过程中，有人对 Hook 书签提出了疑问。更具体地说，Hook 能否像 archive.org 对一般网站所做的那样归档其书签？ Hook 中没有这样的功能，老实说，甚至不需要，因为 Hook 有很好的 Apple Script 集成，所以我们可以从它的数据库中查询书签。

In conjunction with [DEVONthink](https://www.devontechnologies.com/apps/devonthink), we can archive our bookmarks from Hook and save them as Pinboard does. I made a script for this a while back and it’s really helpful. It runs once a week, archives all websites from my Hook database into DEVONthink.  
结合 DEVONthink ，我们可以从 Hook 存档我们的书签，并像 Pinboard 一样保存它们。我不久前为此制作了一个脚本，它真的很有帮助。它每周运行一次，将我的 Hook 数据库中的所有网站存档到 DEVONthink。

### Setting up the script 设置脚本

First, download the script from [here](https://decoding.io/wp-content/uploads/2022/02/Archive-Hook-Bookmarks.zip).  
首先，从这里下载脚本。

The scripts collect everything into one group in DEVONthink, so you have to create one where the archive can be stored. I would advise a new database even if you don’t have something similar already.  
这些脚本将所有内容收集到 DEVONthink 中的一个组中，因此您必须创建一个可以存储存档的组。即使您还没有类似的东西，我也会建议您使用一个新的数据库。

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.02.29.png)

Open the script you downloaded. You’ll see two lines at the top of the file.  
打开您下载的脚本。您会在文件顶部看到两行。

set webArchiveDatabaseUUID to "databaseUUID"  
将 webArchiveDatabaseUUID 设置为“databaseUUID”

set hookedWebsitesGroupUUID to "groupdUUID"  
将 hookedWebsitesGroupUUID 设置为“groupdUUID”

set webArchiveDatabaseUUID to "databaseUUID" set hookedWebsitesGroupUUID to "groupdUUID"

```
set webArchiveDatabaseUUID to "databaseUUID"
set hookedWebsitesGroupUUID to "groupdUUID"

```

You have to replace the `databaseUUID` and the `groupdUUID` part with the UUID of the database and group from DEVONthink. To do this, open DEVONthink, ⌃click on the database in the sidebar, and pick “Copy Item Link”.  
您必须将 `databaseUUID` 和 `groupdUUID` 部分替换为来自 DEVONthink 的数据库和组的 UUID。为此，打开 DEVONthink，⌃ 单击侧边栏中的数据库，然后选择“复制项目链接”。

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.03.28.png)

Now, replace `databaseUUID`, with the link you copied. You’ll see something like this.  
现在，将 `databaseUUID` 替换为您复制的链接。你会看到这样的东西。

set webArchiveDatabaseUUID to "x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D"  
将 webArchiveDatabaseUUID 设置为“x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D”

set hookedWebsitesGroupUUID to "groupdUUID"  
将 hookedWebsitesGroupUUID 设置为“groupdUUID”

set webArchiveDatabaseUUID to "x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "groupdUUID"

```
set webArchiveDatabaseUUID to "x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "groupdUUID"

```

Now, remove the `x-devonthink-item://` part, so the top of the script should look like this.  
现在，删除 `x-devonthink-item://` 部分，因此脚本的顶部应如下所示。

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"  
将 webArchiveDatabaseUUID 设置为“CA3A9072-0650-4AF3-A608-1786F9D1A98D”

set hookedWebsitesGroupUUID to "groupdUUID"  
将 hookedWebsitesGroupUUID 设置为“groupdUUID”

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "groupdUUID"

```
set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "groupdUUID"

```

Go back to DEVONthink and copy the group’s link from the same database (**it is important to keep the group in the same database**) by ⌃clicking on it and picking “Copy Item Link” again.  
返回 DEVONthink 并通过 ⌃ 单击它并再次选择“复制项目链接”从同一数据库复制组的链接（将组保持在同一数据库中很重要）。

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.15.24.png)

Replace `groupdUUID` with the copied link in the script again.  
再次用脚本中复制的链接替换 `groupdUUID` 。

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"  
将 webArchiveDatabaseUUID 设置为“CA3A9072-0650-4AF3-A608-1786F9D1A98D”

set hookedWebsitesGroupUUID to "x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D"  
将 hookedWebsitesGroupUUID 设置为“x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D”

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D"

```
set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D"

```

Remove the `x-devonthink-item://` part and then save your changes. The top of the script should look something like this now.  
删除 `x-devonthink-item://` 部分，然后保存更改。脚本的顶部现在应该看起来像这样。

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"  
将 webArchiveDatabaseUUID 设置为“CA3A9072-0650-4AF3-A608-1786F9D1A98D”

set hookedWebsitesGroupUUID to "B6C2C659-5682-45B5-8D59-107A641F8C2D"  
将 hookedWebsitesGroupUUID 设置为“B6C2C659-5682-45B5-8D59-107A641F8C2D”

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "B6C2C659-5682-45B5-8D59-107A641F8C2D"

```
set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "B6C2C659-5682-45B5-8D59-107A641F8C2D"

```

Now comes the fun part. You can run the script and DEVONthink will start downloading your Hook bookmarks into the group you choose.  
有趣的来了。您可以运行该脚本，DEVONthink 将开始将您的 Hook 书签下载到您选择的组中。

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.13.24.png)

The first run can take a while depending on the size of your Hook database. Subsequent runs should be faster since the script downloads only newly added bookmarks.  
第一次运行可能需要一段时间，具体取决于 Hook 数据库的大小。后续运行应该会更快，因为脚本只下载新添加的书签。

It is important to know that the script doesn’t sync Hook and DEVONthink, deleted bookmarks from Hook will still be present in DEVONthink.  
重要的是要知道该脚本不会同步 Hook 和 DEVONthink，从 Hook 中删除的书签仍会存在于 DEVONthink 中。

Also good to know, if you want to archive sites behind a login, you have to sign-in in DEVONthink before you run the script.  
也很高兴知道，如果你想在登录后存档网站，你必须在运行脚本之前登录 DEVONthink。

### Triggers 触发器

I keep this script in the `~/Libary/Scripts/Applications/DEVONthink 3` folder, so it’s available from the [script menu](https://support.apple.com/guide/script-editor/access-scripts-using-the-script-menu-scpedt27975/mac) in macOS – or in my case, from [FastScripts](https://redsweater.com/fastscripts/). This way, you can run the script manually from DEVONthink.  
我将此脚本保存在 `~/Libary/Scripts/Applications/DEVONthink 3` 文件夹中，因此可以从 macOS 的脚本菜单中获得它——或者在我的情况下，可以从 FastScripts 中获得。这样，您可以从 DEVONthink 手动运行脚本。

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.25.43.png)

You can even make it run automatically. If you use FastScripts, you can create a new DEVONthink reminder on the group you created to store Hook’s bookmarks and set it to run an Apple Script like this every week.  
您甚至可以让它自动运行。如果你使用 FastScripts，你可以在你创建的组上创建一个新的 DEVONthink 提醒来存储 Hook 的书签，并设置它每周运行一个这样的 Apple Script。

on performReminder(theRecord) 在 performReminder(theRecord)

tell application "FastScripts"  
告诉应用程序“FastScripts”

set scriptItem to first script item whose name is "Archive Hook Bookmarks"  
将 scriptItem 设置为名称为“Archive Hook Bookmarks”的第一个脚本项

tell scriptItem to invoke 告诉 scriptItem 调用

end performReminder  end 执行提醒

on performReminder(theRecord) tell application "FastScripts" set scriptItem to first script item whose name is "Archive Hook Bookmarks" tell scriptItem to invoke end tell end performReminder

```
on performReminder(theRecord)
tell application "FastScripts"
set scriptItem to first script item whose name is "Archive Hook Bookmarks"
tell scriptItem to invoke
end tell
end performReminder

```

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.28.51.png)

If you want to run it outside of DEVONthink, you can use for example [Lingon](https://www.peterborgapps.com/lingon/), which makes it possible to run any Apple Script in the background daily, weekly, monthly, or whatever interval you want.  
如果你想在 DEVONthink 之外运行它，你可以使用例如 Lingon ，它可以每天、每周、每月或任何你想要的时间间隔在后台运行任何 Apple Script。
