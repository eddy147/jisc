Jisc; Jira Sub-task Creator
===========================

Small command line app to quickly create sub-tasks for Jira stories.

![PHP from Travis config](https://img.shields.io/badge/PHP-%5E7.0-blue.svg?no-cache=1)

Installation
------------
Clone the repository to a directory by your choosing.

    git clone https://github.com/BowlOfSoup/jisc.git directory

To make the script accessible form anywhere, go into your cloned directory and run:

    echo "PATH=\$PATH:`pwd`/jisc" >> ~/.bash_profile && . ~/.bash_profile

Depending on your settings, use `~/.bashrc` or `~/.bash_profile`. (**on MacOS**, choose `~/.bashrc`).

Usage
-----

#### Create sub tasks

Run `jisc subtask:create` with the following optional options:

```
-u, --user[=USER]          Username to authenticate with Jira instance.
-p, --password[=PASSWORD]  Password to authenticate with Jira instance.
-s, --story[=STORY]        (Parent) Story to use to do actions on with this script.
-k, --key[=KEY]            Project key for story.
-t, --task[=TASK]          Add this single task to given story.
-f, --file[=FILE]          (Only) the filename for a file containing sub-tasks with one task per line.
-h, --help                 Display this help message
```

The script will ask questions for needed options you did not pass yourself. You are free to use the options when calling the script.

**You can create your own set files** and put them in the `~/.jisc` directory. (`~` means, your home directory).
Each line in that file should contain a sub-task.

Examples:
- Create a single sub-task.
```
bin/console subtask:create -t title_for_the_task -u jira_username -p jira_password -s story_number -k project_key
```

- Create sub-tasks from a pre-defined set.

```
bin/console subtask:create -f file_name_with_a_set_of_tasks
```