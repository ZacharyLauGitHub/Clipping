> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [decoding.io](https://decoding.io/2022/02/archive-hook-bookmarks-with-devonthink/)

> I was in a Tinderbox Meetup last week, which was more about Hook than Tinderbox. I’m not a Tinderbox ......

I was in a [Tinderbox Meetup](https://vimeo.com/679537458) last week, which was more about [Hook](https://hookproductivity.com/) than [Tinderbox](https://www.eastgate.com/Tinderbox/). I’m not a Tinderbox user, but I’m interested in how other people use their tools.

In the middle of the call, somebody had a question about Hook bookmarks. More specifically, can Hook archive its bookmarks as [archive.org](https://archive.org/) does with websites in general? Well there is no feature like that in Hook, and to be honest, doesn’t even need to be, because Hook has great [Apple Script integration](https://hookproductivity.com/help/automation/hooks-applescript-dictionary/), so we can query bookmarks from its database.

In conjunction with [DEVONthink](https://www.devontechnologies.com/apps/devonthink), we can archive our bookmarks from Hook and save them as Pinboard does. I made a script for this a while back and it’s really helpful. It runs once a week, archives all websites from my Hook database into DEVONthink.

### Setting up the script

First, download the script from [here](https://decoding.io/wp-content/uploads/2022/02/Archive-Hook-Bookmarks.zip).

The scripts collect everything into one group in DEVONthink, so you have to create one where the archive can be stored. I would advise a new database even if you don’t have something similar already.

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.02.29.png)

Open the script you downloaded. You’ll see two lines at the top of the file.

set webArchiveDatabaseUUID to "databaseUUID"

set hookedWebsitesGroupUUID to "groupdUUID"

set webArchiveDatabaseUUID to "databaseUUID" set hookedWebsitesGroupUUID to "groupdUUID"

```
set webArchiveDatabaseUUID to "databaseUUID"
set hookedWebsitesGroupUUID to "groupdUUID"


```

You have to replace the `databaseUUID` and the `groupdUUID` part with the UUID of the database and group from DEVONthink. To do this, open DEVONthink, ⌃click on the database in the sidebar, and pick “Copy Item Link”.

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.03.28.png)

Now, replace `databaseUUID`, with the link you copied. You’ll see something like this.

set webArchiveDatabaseUUID to "x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D"

set hookedWebsitesGroupUUID to "groupdUUID"

set webArchiveDatabaseUUID to "x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "groupdUUID"

```
set webArchiveDatabaseUUID to "x-devonthink-item://CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "groupdUUID"


```

Now, remove the `x-devonthink-item://` part, so the top of the script should look like this.

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"

set hookedWebsitesGroupUUID to "groupdUUID"

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "groupdUUID"

```
set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "groupdUUID"


```

Go back to DEVONthink and copy the group’s link from the same database (**it is important to keep the group in the same database**) by ⌃clicking on it and picking “Copy Item Link” again.

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.15.24.png)

Replace `groupdUUID` with the copied link in the script again.

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"

set hookedWebsitesGroupUUID to "x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D"

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D"

```
set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "x-devonthink-item://B6C2C659-5682-45B5-8D59-107A641F8C2D"


```

Remove the `x-devonthink-item://` part and then save your changes. The top of the script should look something like this now.

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"

set hookedWebsitesGroupUUID to "B6C2C659-5682-45B5-8D59-107A641F8C2D"

set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D" set hookedWebsitesGroupUUID to "B6C2C659-5682-45B5-8D59-107A641F8C2D"

```
set webArchiveDatabaseUUID to "CA3A9072-0650-4AF3-A608-1786F9D1A98D"
set hookedWebsitesGroupUUID to "B6C2C659-5682-45B5-8D59-107A641F8C2D"


```

Now comes the fun part. You can run the script and DEVONthink will start downloading your Hook bookmarks into the group you choose.

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.13.24.png)

The first run can take a while depending on the size of your Hook database. Subsequent runs should be faster since the script downloads only newly added bookmarks.

It is important to know that the script doesn’t sync Hook and DEVONthink, deleted bookmarks from Hook will still be present in DEVONthink.

Also good to know, if you want to archive sites behind a login, you have to sign-in in DEVONthink before you run the script.

### Triggers

I keep this script in the `~/Libary/Scripts/Applications/DEVONthink 3` folder, so it’s available from the [script menu](https://support.apple.com/guide/script-editor/access-scripts-using-the-script-menu-scpedt27975/mac) in macOS – or in my case, from [FastScripts](https://redsweater.com/fastscripts/). This way, you can run the script manually from DEVONthink.

![](https://decoding.io/wp-content/uploads/2022/02/Screen-Shot-2022-02-23-at-17.25.43.png)

You can even make it run automatically. If you use FastScripts, you can create a new DEVONthink reminder on the group you created to store Hook’s bookmarks and set it to run an Apple Script like this every week.

on performReminder(theRecord)

tell application "FastScripts"

set scriptItem to first script item whose name is "Archive Hook Bookmarks"

tell scriptItem to invoke

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