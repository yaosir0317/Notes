# Playbook Keywords

## Play

- any_errors_fatal

  Force any un-handled task errors on any host to propagate to all hosts and end the play.

- **become**

  Boolean that controls if privilege escalation is used or not on [Task](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-task) execution.

- become_flags

  A string of flag(s) to pass to the privilege escalation program when [become](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-93) is True.

- become_method

  Which method of privilege escalation to use (such as sudo or su).

- **become_user**

  User that you ‘become’ after using privilege escalation. The remote/login user must have permissions to become this user.

- check_mode

  A boolean that controls if a task is executed in ‘check’ mode

- collections

  UNDOCUMENTED!!

- connection

  Allows you to change the connection plugin used for tasks to execute on the target.

- debugger

  Enable debugging tasks based on state of the task result. See [Playbook Debugger](https://docs.ansible.com/ansible/latest/user_guide/playbooks_debugger.html#playbook-debugger)

- diff

  Toggle to make tasks return ‘diff’ information or not.

- environment

  A dictionary that gets converted into environment vars to be provided for the task upon execution. This cannot affect Ansible itself nor its configuration, it just sets the variables for the code responsible for executing the task.

- fact_path

  Set the fact path option for the fact gathering plugin controlled by [gather_facts](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-gather-facts).

- force_handlers

  Will force notified handler execution for hosts even if they failed during the play. Will not trigger if the play itself fails.

- gather_facts

  A boolean that controls if the play will automatically run the ‘setup’ task to gather facts for the hosts.

- gather_subset

  Allows you to pass subset options to the fact gathering plugin controlled by [gather_facts](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-gather-facts).

- gather_timeout

  Allows you to set the timeout for the fact gathering plugin controlled by [gather_facts](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-gather-facts).

- handlers

  A section with tasks that are treated as handlers, these won’t get executed normally, only when notified after each section of tasks is complete. A handler’s listen field is not templatable.

- hosts

  A list of groups, hosts or host pattern that translates into a list of hosts that are the play’s target.

- ignore_errors

  Boolean that allows you to ignore task failures and continue with play. It does not affect connection errors.

- ignore_unreachable

  Boolean that allows you to ignore unreachable hosts and continue with play. This does not affect other task errors (see [ignore_errors](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-108)) but is useful for groups of volatile/ephemeral hosts.

- max_fail_percentage

  can be used to abort the run after a given percentage of hosts in the current batch has failed.

- module_defaults

  Specifies default parameter values for modules.

- name

  Identifier. Can be used for documentation, in or tasks/handlers.

- no_log

  Boolean that controls information disclosure.

- order

  Controls the sorting of hosts as they are used for executing the play. Possible values are inventory (default), sorted, reverse_sorted, reverse_inventory and shuffle.

- port

  Used to override the default port used in a connection.

- post_tasks

  A list of tasks to execute after the [tasks](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-tasks) section.

- pre_tasks

  A list of tasks to execute before [roles](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-roles).

- remote_user

  User used to log into the target via the connection plugin.

- roles

  List of roles to be imported into the play

- **run_once**

  Boolean that will bypass the host loop, forcing the task to attempt to execute on the first host available and afterwards apply any results and facts to all active hosts in the same batch.

- serial

  Explicitly define how Ansible batches the execution of the current play on the play’s target

- strategy

  Allows you to choose the connection plugin to use for the play.

- tags

  Tags applied to the task or included tasks, this allows selecting subsets of tasks from the command line.

- tasks

  Main list of tasks to execute in the play, they run after [roles](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-roles) and before [post_tasks](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-post-tasks).

- vars

  Dictionary/map of variables

- vars_files

  List of files that contain vars to include in the play.

- vars_prompt

  list of variables to prompt for.

## Role

- any_errors_fatal

  Force any un-handled task errors on any host to propagate to all hosts and end the play.

- become

  Boolean that controls if privilege escalation is used or not on [Task](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-task) execution.

- become_flags

  A string of flag(s) to pass to the privilege escalation program when [become](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-93) is True.

- become_method

  Which method of privilege escalation to use (such as sudo or su).

- become_user

  User that you ‘become’ after using privilege escalation. The remote/login user must have permissions to become this user.

- check_mode

  A boolean that controls if a task is executed in ‘check’ mode

- collections

  UNDOCUMENTED!!

- connection

  Allows you to change the connection plugin used for tasks to execute on the target.

- debugger

  Enable debugging tasks based on state of the task result. See [Playbook Debugger](https://docs.ansible.com/ansible/latest/user_guide/playbooks_debugger.html#playbook-debugger)

- delegate_facts

  Boolean that allows you to apply facts to a delegated host instead of inventory_hostname.

- delegate_to

  Host to execute task instead of the target (inventory_hostname). Connection vars from the delegated host will also be used for the task.

- diff

  Toggle to make tasks return ‘diff’ information or not.

- environment

  A dictionary that gets converted into environment vars to be provided for the task upon execution. This cannot affect Ansible itself nor its configuration, it just sets the variables for the code responsible for executing the task.

- ignore_errors

  Boolean that allows you to ignore task failures and continue with play. It does not affect connection errors.

- ignore_unreachable

  Boolean that allows you to ignore unreachable hosts and continue with play. This does not affect other task errors (see [ignore_errors](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-108)) but is useful for groups of volatile/ephemeral hosts.

- module_defaults

  Specifies default parameter values for modules.

- name

  Identifier. Can be used for documentation, in or tasks/handlers.

- no_log

  Boolean that controls information disclosure.

- port

  Used to override the default port used in a connection.

- remote_user

  User used to log into the target via the connection plugin.

- **run_once**

  Boolean that will bypass the host loop, forcing the task to attempt to execute on the first host available and afterwards apply any results and facts to all active hosts in the same batch.

- tags

  Tags applied to the task or included tasks, this allows selecting subsets of tasks from the command line.

- vars

  Dictionary/map of variables

- when

  Conditional expression, determines if an iteration of a task is run or not.

## Block

- always

  List of tasks, in a block, that execute no matter if there is an error in the block or not.

- any_errors_fatal

  Force any un-handled task errors on any host to propagate to all hosts and end the play.

- become

  Boolean that controls if privilege escalation is used or not on [Task](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-task) execution.

- become_flags

  A string of flag(s) to pass to the privilege escalation program when [become](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-93) is True.

- become_method

  Which method of privilege escalation to use (such as sudo or su).

- become_user

  User that you ‘become’ after using privilege escalation. The remote/login user must have permissions to become this user.

- block

  List of tasks in a block.

- check_mode

  A boolean that controls if a task is executed in ‘check’ mode

- collections

  UNDOCUMENTED!!

- connection

  Allows you to change the connection plugin used for tasks to execute on the target.

- debugger

  Enable debugging tasks based on state of the task result. See [Playbook Debugger](https://docs.ansible.com/ansible/latest/user_guide/playbooks_debugger.html#playbook-debugger)

- delegate_facts

  Boolean that allows you to apply facts to a delegated host instead of inventory_hostname.

- delegate_to

  Host to execute task instead of the target (inventory_hostname). Connection vars from the delegated host will also be used for the task.

- diff

  Toggle to make tasks return ‘diff’ information or not.

- environment

  A dictionary that gets converted into environment vars to be provided for the task upon execution. This cannot affect Ansible itself nor its configuration, it just sets the variables for the code responsible for executing the task.

- ignore_errors

  Boolean that allows you to ignore task failures and continue with play. It does not affect connection errors.

- ignore_unreachable

  Boolean that allows you to ignore unreachable hosts and continue with play. This does not affect other task errors (see [ignore_errors](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-108)) but is useful for groups of volatile/ephemeral hosts.

- module_defaults

  Specifies default parameter values for modules.

- name

  Identifier. Can be used for documentation, in or tasks/handlers.

- no_log

  Boolean that controls information disclosure.

- port

  Used to override the default port used in a connection.

- remote_user

  User used to log into the target via the connection plugin.

- rescue

  List of tasks in a [block](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-block) that run if there is a task error in the main [block](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-block) list.

- **run_once**

  Boolean that will bypass the host loop, forcing the task to attempt to execute on the first host available and afterwards apply any results and facts to all active hosts in the same batch.

- tags

  Tags applied to the task or included tasks, this allows selecting subsets of tasks from the command line.

- vars

  Dictionary/map of variables

- when

  Conditional expression, determines if an iteration of a task is run or not.

## Task

- **action**

  The ‘action’ to execute for a task, it normally translates into a C(module) or action plugin.

- any_errors_fatal

  Force any un-handled task errors on any host to propagate to all hosts and end the play.

- **args**

  A secondary way to add arguments into a task. Takes a dictionary in which keys map to options and values.

- **async**

  Run a task asynchronously if the C(action) supports this; value is maximum runtime in seconds.

- **become**

  Boolean that controls if privilege escalation is used or not on [Task](https://docs.ansible.com/ansible/latest/reference_appendices/glossary.html#term-task) execution.

- become_flags

  A string of flag(s) to pass to the privilege escalation program when [become](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-93) is True.

- become_method

  Which method of privilege escalation to use (such as sudo or su).

- **become_user**

  User that you ‘become’ after using privilege escalation. The remote/login user must have permissions to become this user.

- changed_when

  Conditional expression that overrides the task’s normal ‘changed’ status.

- check_mode

  A boolean that controls if a task is executed in ‘check’ mode

- collections

  UNDOCUMENTED!!

- connection

  Allows you to change the connection plugin used for tasks to execute on the target.

- debugger

  Enable debugging tasks based on state of the task result. See [Playbook Debugger](https://docs.ansible.com/ansible/latest/user_guide/playbooks_debugger.html#playbook-debugger)

- delay

  Number of seconds to delay between retries. This setting is only used in combination with [until](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-until).

- delegate_facts

  Boolean that allows you to apply facts to a delegated host instead of inventory_hostname.

- **delegate_to**

  Host to execute task instead of the target (inventory_hostname). Connection vars from the delegated host will also be used for the task.

- diff

  Toggle to make tasks return ‘diff’ information or not.

- environment

  A dictionary that gets converted into environment vars to be provided for the task upon execution. This cannot affect Ansible itself nor its configuration, it just sets the variables for the code responsible for executing the task.

- failed_when

  Conditional expression that overrides the task’s normal ‘failed’ status.

- ignore_errors

  Boolean that allows you to ignore task failures and continue with play. It does not affect connection errors.

- ignore_unreachable

  Boolean that allows you to ignore unreachable hosts and continue with play. This does not affect other task errors (see [ignore_errors](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-108)) but is useful for groups of volatile/ephemeral hosts.

- **local_action**

  Same as action but also implies `delegate_to: localhost`

  这些操作将在本地计算机（Ansible控制主机）上执行，但在变量方面仍然在远程主机的上下文中

- loop

  Takes a list for the task to iterate over, saving each list element into the `item` variable (configurable via loop_control)

- loop_control

  Several keys here allow you to modify/set loop behaviour in a task.

- module_defaults

  Specifies default parameter values for modules.

- name

  Identifier. Can be used for documentation, in or tasks/handlers.

- no_log

  Boolean that controls information disclosure.

- **notify**

  List of handlers to notify when the task returns a ‘changed=True’ status.

- poll

  Sets the polling interval in seconds for async tasks (default 10s).

- port

  Used to override the default port used in a connection.

- **register**

  Name of variable that will contain task status and module return data.

  在ansible的playbook中task之间的相互传递变量

- remote_user

  User used to log into the target via the connection plugin.

- retries

  Number of retries before giving up in a [until](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-until) loop. This setting is only used in combination with [until](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-until).

- **run_once**

  Boolean that will bypass the host loop, forcing the task to attempt to execute on the first host available and afterwards apply any results and facts to all active hosts in the same batch.

- tags

  Tags applied to the task or included tasks, this allows selecting subsets of tasks from the command line.

- until

  This keyword implies a ‘[retries](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-retries) loop’ that will go on until the condition supplied here is met or we hit the [retries](https://docs.ansible.com/ansible/latest/reference_appendices/playbooks_keywords.html?highlight=run_once#term-retries) limit.

- vars

  Dictionary/map of variables

- **when**

  Conditional expression, determines if an iteration of a task is run or not.

- with_<lookup_plugin>

  The same as `loop` but magically adds the output of any lookup plugin to generate the item list.

# Modules

## command

- 功能

  在远程节点上执行指定的命令,但不会通过shell处理,因此

   `$HOME` 和以下类似操作符号 `"<"`, `">"`, `"|"`, `";"` and `"&"` 不会生效

- 参数

  | Parameter       | Comments                                                     |
  | --------------- | ------------------------------------------------------------ |
  | argv(`list`)    | Passes the command as a list rather than a string.                                                                  Use `argv` to avoid quoting values that would otherwise be interpreted incorrectly (for example "user name").                                                                                                            Only the string or the list form can be provided, not both. One or the other must be provided. |
  | chdir(`path`)   | Change into this directory before running the command.       |
  | creates(`path`) | A filename or (since 2.0) glob pattern. If it already exists, this step **won't** be run. |
  | removes(`path`) | A filename or (since 2.0) glob pattern. If it already exists, this step **will** be run. |

- 示例

  ```yaml
  - name: return motd to registered var
    command: cat /etc/motd
    register: mymotd
  
  - name: Run command if /path/to/database does not exist (without 'args').
    command: /usr/bin/make_database.sh db_user db_name creates=/path/to/database
  
  # 'args' is a task keyword, passed at the same level as the module
  - name: Run command if /path/to/database does not exist (with 'args').
    command: /usr/bin/make_database.sh db_user db_name
    args:
      creates: /path/to/database
  
  - name: Change the working directory to somedir/ and run the command as db_owner if /path/to/database does not exist.
    command: /usr/bin/make_database.sh db_user db_name
    become: yes
    become_user: db_owner
    args:
      chdir: somedir/
      creates: /path/to/database
  
  # 'argv' is a parameter, indented one level from the module
  - name: Use 'argv' to send a command as a list - leave 'command' empty
    command:
      argv:
        - /usr/bin/make_database.sh
        - Username with whitespace
        - dbname with whitespace
  
  - name: safely use templated variable to run command. Always use the quote filter to avoid injection issues.
    command: cat {{ myfile|quote }}
    register: myoutput
  ```

  

## script

- 功能

  在远程节点上执行本地脚本

- 参数

  | Parameter                        | Comments                                                     |
  | -------------------------------- | ------------------------------------------------------------ |
  | chdir                            | Change into this directory on the remote node before running the script. |
  | creates                          | A filename on the remote node, when it already exists, this step will **not** be run. |
  | decrypt(`boolean`) *default=yes* | This option controls the autodecryption of source files using vault. |
  | executable                       | Name or path of a executable to invoke the script with.      |
  | removes                          | A filename on the remote node, when it does not exist, this step will **not** be run. |

- 示例

  ```yaml
  - name: Run a script with arguments
    script: /some/local/script.sh --some-argument 1234
  
  - name: Run a script only if file.txt does not exist on the remote node
    script: /some/local/create_file.sh --some-argument 1234
    args:
      creates: /the/created/file.txt
  
  - name: Run a script only if file.txt exists on the remote node
    script: /some/local/remove_file.sh --some-argument 1234
    args:
      removes: /the/removed/file.txt
  
  - name: Run a script using an executable in a non-system path
    script: /some/local/script
    args:
      executable: /some/remote/executable
  
  - name: Run a script using an executable in a system path
    script: /some/local/script.py
    args:
      executable: python3
  ```

  

## shell

- 功能

  通过远程节点的shell(bin/bash)执行所指定的命令

- 参数

  | Parameter          | Comments                                                     |
  | ------------------ | ------------------------------------------------------------ |
  | chdir(`path`)      | Change into this directory before running the command.       |
  | creates(`path`)    | A filename, when it already exists, this step will **not** be run. |
  | executable(`path`) | Change the shell used to execute the command.                                                This expects an absolute path to the executable. |
  | removes(`path`)    | A filename, when it does not exist, this step will **not** be run. |

- 示例

  ```yaml
  - name: Execute the command in remote shell; stdout goes to the specified file on the remote.
    shell: somescript.sh >> somelog.txt
  
  - name: Change the working directory to somedir/ before executing the command.
    shell: somescript.sh >> somelog.txt
    args:
      chdir: somedir/
  
  # You can also use the 'args' form to provide the options.
  - name: This command will change the working directory to somedir/ and will only run when somedir/somelog.txt doesn't exist.
    shell: somescript.sh >> somelog.txt
    args:
      chdir: somedir/
      creates: somelog.txt
  
  - name: Run a command that uses non-posix shell-isms (in this example /bin/sh doesn't handle redirection and wildcards together but bash does)
    shell: cat < /tmp/*txt
    args:
      executable: /bin/bash
  
  - name: Run a command using a templated variable (always use quote filter to avoid injection)
    shell: cat {{ myfile|quote }}
  
  # You can use shell to run other executables to perform actions inline
  - name: Run expect to wait for a successful PXE boot via out-of-band CIMC
    shell: |
      set timeout 300
      spawn ssh admin@{{ cimc_host }}
  
      expect "password:"
      send "{{ cimc_password }}\n"
  
      expect "\n{{ cimc_name }}"
      send "connect host\n"
  
      expect "pxeboot.n12"
      send "\n"
  
      exit 0
    args:
      executable: /usr/bin/expect
    delegate_to: localhost
  
  # Disabling warnings
  - name: Using curl to connect to a host via SOCKS proxy (unsupported in uri). Ordinarily this would throw a warning.
    shell: curl --socks5 localhost:9000 http://www.ansible.com
    args:
      warn: no
  ```

  

## copy

- 功能

  将本地文件复制到远程节点

- 参数

  | Parameter                       | Comments                                                     |
  | ------------------------------- | ------------------------------------------------------------ |
  | src(`path`)                     | Local path to a file to copy to the remote server.                                                                       This can be absolute or relative.                                                                                                        If path is a directory, it is copied recursively. In this case, if path ends with "/", only inside contents of that directory are copied to destination. Otherwise, if it does not end with "/", the directory itself with all contents is copied. This behavior is similar to the `rsync` command line tool. |
  | dest(`path`)                    | Remote absolute path where the file should be copied to.                                                     If `src` is a directory, this must be a directory too.                                                                    If `dest` is a non-existent path and if either `dest` ends with "/" or `src` is a directory, `dest` is created. |
  | owner                           | Name of the user that should own the file/directory, as would be fed to *chown*. |
  | group                           | Name of the group that should own the file/directory, as would be fed to *chown*. |
  | mode(`path`)                    | The permissions of the destination file or directory.                                                               For those used to `/usr/bin/chmod` remember that modes are actually octal numbers. You must either add a leading zero so that Ansible's YAML parser knows it is an octal number (like `0644` or `01777`)or quote it (like `'644'` or `'1777'`) so Ansible receives a string and can do its own conversion from string into number. Giving Ansible a number without following one of these rules will end up with a decimal number which will have unexpected results.                                                             As of Ansible 1.8, the mode may be specified as a symbolic mode (for example, `u+rwx` or `u=rw,g=r,o=r`).                                                                                                               As of Ansible 2.3, the mode may also be the special string `preserve`.                               `preserve` means that the file will be given the same permissions as the source file. |
  | backup(`boolean`)               | Create a backup file including the timestamp information so you can get the original file back if you somehow clobbered it incorrectly.(`default=no`) |
  | validate                        | The validation command to run before copying into place.                                           The path to the file to validate is passed in via '%s' which must be present as in the examples below.                                                                                                              The command is passed securely so shell features like expansion and pipes will not work. |
  | follow(`boolean`)  *default=no* | This flag indicates that filesystem links in the destination, if they exist, should be folloowed. |
  | content                         | When used instead of `src`, sets the contents of a file directly to the specified value.                                                                                                                                        For advanced formatting or if `content` contains a variable, use the `template` module. |

- 示例

  ```yaml
  - name: Copy file with owner and permissions
    copy:
      src: /srv/myfiles/foo.conf
      dest: /etc/foo.conf
      owner: foo
      group: foo
      mode: '0644'
  
  - name: Copy file with owner and permission, using symbolic representation
    copy:
      src: /srv/myfiles/foo.conf
      dest: /etc/foo.conf
      owner: foo
      group: foo
      mode: u=rw,g=r,o=r
  
  - name: Another symbolic mode example, adding some permissions and removing others
    copy:
      src: /srv/myfiles/foo.conf
      dest: /etc/foo.conf
      owner: foo
      group: foo
      mode: u+rw,g-wx,o-rwx
  
  - name: Copy a new "ntp.conf file into place, backing up the original if it differs from the copied version
    copy:
      src: /mine/ntp.conf
      dest: /etc/ntp.conf
      owner: root
      group: root
      mode: '0644'
      backup: yes
  
  - name: Copy a new "sudoers" file into place, after passing validation with visudo
    copy:
      src: /mine/sudoers
      dest: /etc/sudoers
      validate: /usr/sbin/visudo -cf %s
  
  - name: Copy a "sudoers" file on the remote machine for editing
    copy:
      src: /etc/sudoers
      dest: /etc/sudoers.edit
      remote_src: yes
      validate: /usr/sbin/visudo -cf %s
  
  - name: Copy using inline content
    copy:
      content: '# This file was moved to /etc/other.conf'
      dest: /etc/mine.conf
  
  - name: If follow=yes, /path/to/file will be overwritten by contents of foo.conf
    copy:
      src: /etc/foo.conf
      dest: /path/to/link  # link to /path/to/file
      follow: yes
  
  - name: If follow=no, /path/to/link will become a file and be overwritten by contents of foo.conf
    copy:
      src: /etc/foo.conf
      dest: /path/to/link  # link to /path/to/file
      follow: no
  ```



## fetch

- 功能

  将远程节点上的文件复制到本地

- 参数

  | Parameter                    | Comments                                                     |
  | ---------------------------- | ------------------------------------------------------------ |
  | dest                         | A directory to save the file into.                                                                                                    For example, if the *dest* directory is `/backup` a *src* file named `/etc/profile` on host `host.example.com`, would be saved into `/backup/host.example.com/etc/profile`. The host name is based on the inventory name. |
  | src                          | The file on the remote system to fetch.                                                                                     This *must* be a file, not a directory.                                                                                             Recursive fetching may be supported in a later release. |
  | flat(`boolean`) *default=no* | Allows you to override the default behavior of appending hostname/path/to/file to the destination.                                                                                                                            If `dest` ends with '/', it will use the basename of the source file, similar to the copy module. |

- 示例

  ```yaml
  - name: Store file into /tmp/fetched/host.example.com/tmp/somefile
    fetch:
      src: /tmp/somefile
      dest: /tmp/fetched
  
  - name: Specifying a path directly
    fetch:
      src: /tmp/somefile
      dest: /tmp/prefix-{{ inventory_hostname }}
      flat: yes
  
  - name: Specifying a destination path
    fetch:
      src: /tmp/uniquefile
      dest: /tmp/special/
      flat: yes
  
  - name: Storing in a path relative to the playbook
    fetch:
      src: /tmp/uniquefile
      dest: special/prefix-{{ inventory_hostname }}
      flat: yes
  ```



## file

- 功能

  为文件,链接,文件夹设置属性

- 参数

  | Parameter                           | Comments                                                     |
  | ----------------------------------- | ------------------------------------------------------------ |
  | path(`path`)                        | Path to the file being managed.                              |
  | owner                               | Name of the user that should own the file/directory, as would be fed to *chown*. |
  | group                               | Name of the group that should own the file/directory, as would be fed to *chown*. |
  | mode                                | The permissions the resulting file or directory should have.                                                        For those used to */usr/bin/chmod* remember that modes are actually octal numbers. You must either add a leading zero so that Ansible's YAML parser knows it is an octal number (like `0644` or `01777`) or quote it (like `'644'` or `'1777'`) so Ansible receives a string and can do its own conversion from string into number.                                                             Giving Ansible a number without following one of these rules will end up with a decimal number which will have unexpected results.                                                                                                   As of Ansible 1.8, the mode may be specified as a symbolic mode (for example, `u+rwx` or `u=rw,g=r,o=r`).                                                                                                              As of Ansible 2.6, the mode may also be the special string `preserve`.                                 When set to `preserve` the file will be given the same permissions as the source file. |
  | state                *default=file* | If `absent`, directories will be recursively deleted, and files or symlinks will be unlinked. Note that `absent` will not cause `file` to fail if the `path` does not exist as the state did not change.                                                                                                                 If `directory`, all intermediate subdirectories will be created if they do not exist. Since Ansible 1.7 they will be created with the supplied permissions.                                     If `file`, without any other options this works mostly as a 'stat' and will return the current state of `path`. Even with other options (i.e `mode`), the file will be modified but will NOT be created if it does not exist; see the `touch` value or the copy or template module if you want that behavior.                                                                                                If `hard`, the hard link will be created or changed.                                                                      If `link`, the symbolic link will be created or changed.                                                             If `touch` (new in 1.4), an empty file will be created if the `path` does not exist, while an existing file or directory will receive updated file access and modification times (similar to the way `touch` works from the command line). |
  | src(`path`)                         | Path of the file to link to.                                                                                                                 This applies only to `state=link` and `state=hard`.                                                                    Will accept absolute and non-existing paths.                                                                             Will accept relative paths unless state=hard.                                                                              Relative paths are relative to the file being created (`path`) which is how the Unix command `ln -s SRC DEST` treats relative paths. |

- 示例

  ```yaml
  - name: Change file ownership, group and permissions
    file:
      path: /etc/foo.conf
      owner: foo
      group: foo
      mode: '0644'
  
  - name: Create an insecure file
    file:
      path: /work
      owner: root
      group: root
      mode: '1777'
  
  - name: Create a symbolic link
    file:
      src: /file/to/link/to
      dest: /path/to/symlink
      owner: foo
      group: foo
      state: link
  
  - name: Create two hard links
    file:
      src: '/tmp/{{ item.src }}'
      dest: '{{ item.dest }}'
      state: link
    with_items:
      - { src: x, dest: y }
      - { src: z, dest: k }
  
  - name: Touch a file, using symbolic modes to set the permissions (equivalent to 0644)
    file:
      path: /etc/foo.conf
      state: touch
      mode: u=rw,g=r,o=r
  
  - name: Touch the same file, but add/remove some permissions
    file:
      path: /etc/foo.conf
      state: touch
      mode: u+rw,g-wx,o-rwx
  
  - name: Touch again the same file, but dont change times this makes the task idempotent
    file:
      path: /etc/foo.conf
      state: touch
      mode: u+rw,g-wx,o-rwx
      modification_time: preserve
      access_time: preserve
  
  - name: Create a directory if it does not exist
    file:
      path: /etc/some_directory
      state: directory
      mode: '0755'
  
  - name: Update modification and access time of given file
    file:
      path: /etc/some_file
      state: file
      modification_time: now
      access_time: now
  
  - name: Set access time based on seconds from epoch value
    file:
      path: /etc/another_file
      state: file
      access_time: '{{ "%Y%m%d%H%M.%S" | strftime(stat_var.stat.atime) }}'
  
  - name: Recursively change ownership of a directory
    file:
      path: /etc/foo
      state: directory
      recurse: yes
      owner: foo
      group: foo
  ```



## lineinfile

- 功能

  更改文件中的某一具体的行

- 参数

  | Parameter                                             | Comments                                                     |
  | ----------------------------------------------------- | ------------------------------------------------------------ |
  | path(`path`)                                          | The file to modify.                                          |
  | state                               *default=present* | Whether the line should be there or not.                     |
  | regexp                                                | The regular expression to look for in every line of the file.                                       For `state=present`, the pattern to replace if found. Only the last line found will be replaced.                                                                                                                                For `state=absent`, the pattern of the line(s) to remove.                                                  If the regular expression is not matched, the line will be added to the file in keeping with `insertbefore` or `insertafter` settings.                                                    When modifying a line the regexp should typically match both the initial state of the line as well as its state after replacement by `line` to ensure idempotence. |
  | line                                                  | The line to insert/replace into the file.                                                                                  Required for `state=present`.                                                                                                If `backrefs` is set, may contain backreferences that will get expanded with the `regexp` capture groups if the regexp matches. |
  | group                                                 | Name of the group that should own the file/directory, as would be fed to *chown*. |
  | owner                                                 | Name of the user that should own the file/directory, as would be fed to *chown*. |
  | mode                                                  | The permissions the resulting file or directory should have.                                            For those used to */usr/bin/chmod* remember that modes are actually octal numbers. You must either add a leading zero so that Ansible's YAML parser knows it is an octal number (like `0644` or `01777`) or quote it (like `'644'` or `'1777'`) so Ansible receives a string and can do its own conversion from string into number.                                                                                                                           Giving Ansible a number without following one of these rules will end up with a decimal number which will have unexpected results.                                                       As of Ansible 1.8, the mode may be specified as a symbolic mode (for example, `u+rwx` or `u=rw,g=r,o=r`).                                                                                                      As of Ansible 2.6, the mode may also be the special string `preserve`.                           When set to `preserve` the file will be given the same permissions as the source file. |
  | insertafter                                           | Used with `state=present`.                                                                                                        If specified, the line will be inserted after the last match of specified regular expression.                                                                                                                                  If the first match is required, use(firstmatch=yes).                                                              A special value is available; `EOF` for inserting the line at the end of the file.                   If specified regular expression has no matches, EOF will be used instead.                                                                                                   If `insertbefore` is set, default value `EOF` will be ignored.                                                                                                                                 If regular expressions are passed to both `regexp` and `insertafter`, `insertafter` is only honored if no match for `regexp` is found.                                                             May not be used with `backrefs` or `insertbefore`. |
  | insertbefore                                          | Used with `state=present`.                                                                                                        If specified, the line will be inserted before the last match of specified regular expression.                                                                                                                                 If the first match is required, use(firstmatch=yes).                                                              A value is available; `BOF` for inserting the line at the beginning of the file.                   If specified regular expression has no matches, the line will be inserted at the end of the file.                                                                                                                      If regular expressions are passed to both `regexp` and `insertbefore`, `insertbefore` is only honored if no match for `regexp` is found.                                                                                                                            May not be used with `backrefs` or `insertafter`. |

- 示例

  ```yaml
  # NOTE: Before 2.3, option 'dest', 'destfile' or 'name' was used instead of 'path'
  - name: Ensure SELinux is set to enforcing mode
    lineinfile:
      path: /etc/selinux/config
      regexp: '^SELINUX='
      line: SELINUX=enforcing
  
  - name: Make sure group wheel is not in the sudoers configuration
    lineinfile:
      path: /etc/sudoers
      state: absent
      regexp: '^%wheel'
  
  - name: Replace a localhost entry with our own
    lineinfile:
      path: /etc/hosts
      regexp: '^127\.0\.0\.1'
      line: 127.0.0.1 localhost
      owner: root
      group: root
      mode: '0644'
  
  - name: Ensure the default Apache port is 8080
    lineinfile:
      path: /etc/httpd/conf/httpd.conf
      regexp: '^Listen '
      insertafter: '^#Listen '
      line: Listen 8080
  
  - name: Ensure we have our own comment added to /etc/services
    lineinfile:
      path: /etc/services
      regexp: '^# port for http'
      insertbefore: '^www.*80/tcp'
      line: '# port for http by default'
  
  - name: Add a line to a file if the file does not exist, without passing regexp
    lineinfile:
      path: /tmp/testfile
      line: 192.168.1.99 foo.lab.net foo
      create: yes
  
  # NOTE: Yaml requires escaping backslashes in double quotes but not in single quotes
  - name: Ensure the JBoss memory settings are exactly as needed
    lineinfile:
      path: /opt/jboss-as/bin/standalone.conf
      regexp: '^(.*)Xms(\\d+)m(.*)$'
      line: '\1Xms${xms}m\3'
      backrefs: yes
  
  # NOTE: Fully quoted because of the ': ' on the line. See the Gotchas in the YAML docs.
  - name: Validate the sudoers file before saving
    lineinfile:
      path: /etc/sudoers
      state: present
      regexp: '^%ADMIN ALL='
      line: '%ADMIN ALL=(ALL) NOPASSWD: ALL'
      validate: /usr/sbin/visudo -cf %s
  ```



## synchronize

- 功能

  同步文件,同步多层目录时效率高于`copy`模块,是`rsync`的封装

- 参数

  | Parameter          | Comments                                                     |
  | ------------------ | ------------------------------------------------------------ |
  | src                | Path on the source host that will be synchronized to the destination.                                  The path can be absolute or relative. |
  | dest               | Path on the destination host that will be synchronized from the source.                             The path can be absolute or relative. |
  | delete             | Delete files in `dest` that don't exist (after transfer, not before) in the `src` path.    This option requires `recursive=yes`. |
  | mode               | Specify the direction of the synchronization.                                                                             In push mode the localhost or delegate is the source.                                                            In pull mode the remote host in context is the source. |
  | archive(`boolean`) | Mirrors the rsync archive flag, enables recursive, links, perms, times, owner, group flags and -D. |
  | rsync_opts         | Specify additional rsync options by passing in an array.                                                 Note that an empty string in `rsync_opts` will end up transfer the current working directory. |
  | rsync_path         | Specify the rsync command to run on the remote host. See `--rsync-path` on the rsync man page.                                                                                                               To specify the rsync command to run on the local host, you need to set this your task var `ansible_rsync_path`. |

- 示例

  ```yaml
  - name: Synchronization of src on the control machine to dest on the remote hosts
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
  
  - name: Synchronization using rsync protocol (push)
    synchronize:
      src: some/relative/path/
      dest: rsync://somehost.com/path/
  
  - name: Synchronization using rsync protocol (pull)
    synchronize:
      mode: pull
      src: rsync://somehost.com/path/
      dest: /some/absolute/path/
  
  - name:  Synchronization using rsync protocol on delegate host (push)
    synchronize:
      src: /some/absolute/path/
      dest: rsync://somehost.com/path/
    delegate_to: delegate.host
  
  - name: Synchronization using rsync protocol on delegate host (pull)
    synchronize:
      mode: pull
      src: rsync://somehost.com/path/
      dest: /some/absolute/path/
    delegate_to: delegate.host
  
  - name: Synchronization without any --archive options enabled
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
      archive: no
  
  - name: Synchronization with --archive options enabled except for --recursive
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
      recursive: no
  
  - name: Synchronization with --archive options enabled except for --times, with --checksum option enabled
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
      checksum: yes
      times: no
  
  - name: Synchronization without --archive options enabled except use --links
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
      archive: no
      links: yes
  
  - name: Synchronization of two paths both on the control machine
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
    delegate_to: localhost
  
  - name: Synchronization of src on the inventory host to the dest on the localhost in pull mode
    synchronize:
      mode: pull
      src: some/relative/path
      dest: /some/absolute/path
  
  - name: Synchronization of src on delegate host to dest on the current inventory host.
    synchronize:
      src: /first/absolute/path
      dest: /second/absolute/path
    delegate_to: delegate.host
  
  - name: Synchronize two directories on one remote host.
    synchronize:
      src: /first/absolute/path
      dest: /second/absolute/path
    delegate_to: "{{ inventory_hostname }}"
  
  - name: Synchronize and delete files in dest on the remote host that are not found in src of localhost.
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
      delete: yes
      recursive: yes
  
  # This specific command is granted su privileges on the destination
  - name: Synchronize using an alternate rsync command
    synchronize:
      src: some/relative/path
      dest: /some/absolute/path
      rsync_path: su -c rsync
  
  # Example .rsync-filter file in the source directory
  # - var       # exclude any path whose last part is 'var'
  # - /var      # exclude any path starting with 'var' starting at the source directory
  # + /var/conf # include /var/conf even though it was previously excluded
  
  - name: Synchronize passing in extra rsync options
    synchronize:
      src: /tmp/helloworld
      dest: /var/www/helloworld
      rsync_opts:
        - "--no-motd"
        - "--exclude=.git"
  
  # Hardlink files if they didn't change
  - name: Use hardlinks when synchronizing filesystems
    synchronize:
      src: /tmp/path_a/foo.txt
      dest: /tmp/path_b/foo.txt
      link_dest: /tmp/path_a/
  
  # Specify the rsync binary to use on remote host and on local host
  - hosts: groupofhosts
    vars:
          ansible_rsync_path: /usr/gnu/bin/rsync
  
    tasks:
      - name: copy /tmp/localpath/ to remote location /tmp/remotepath
        synchronize:
          src: /tmp/localpath/
          dest: /tmp/remotepath
          rsync_path: /usr/gnu/bin/rsync
  ```



## template

- 功能

  复制的时候可以使用`jinjia2`模版替换参数

- 参数

  | Parameter | Comments                                                     |
  | --------- | ------------------------------------------------------------ |
  | src       | Path of a Jinja2 formatted template on the Ansible controller.                                               This can be a relative or an absolute path.                                                                                 The file must be encoded with `utf-8` but *output_encoding* can be used to control the encoding of the output template. |
  | dest      | Location to render the template to on the remote machine.    |

- 示例

  ```yaml
  - name: Template a file to /etc/files.conf
    template:
      src: /mytemplates/foo.j2
      dest: /etc/file.conf
      owner: bin
      group: wheel
      mode: '0644'
  
  - name: Template a file, using symbolic modes (equivalent to 0644)
    template:
      src: /mytemplates/foo.j2
      dest: /etc/file.conf
      owner: bin
      group: wheel
      mode: u=rw,g=r,o=r
  
  - name: Copy a version of named.conf that is dependent on the OS. setype obtained by doing ls -Z /etc/named.conf on original file
    template:
      src: named.conf_{{ ansible_os_family}}.j2
      dest: /etc/named.conf
      group: named
      setype: named_conf_t
      mode: 0640
  
  - name: Create a DOS-style text file from a template
    template:
      src: config.ini.j2
      dest: /share/windows/config.ini
      newline_sequence: '\r\n'
  
  - name: Copy a new sudoers file into place, after passing validation with visudo
    template:
      src: /mine/sudoers
      dest: /etc/sudoers
      validate: /usr/sbin/visudo -cf %s
  
  - name: Update sshd configuration safely, avoid locking yourself out
    template:
      src: etc/ssh/sshd_config.j2
      dest: /etc/ssh/sshd_config
      owner: root
      group: root
      mode: '0600'
      validate: /usr/sbin/sshd -t -f %s
      backup: yes
  ```



## timezone

- 示例

  ```yaml
  - name: Set timezone
    timezone:
      name: Asia/Shanghai
  ```



## fail

- 示例

  ```
  # Example playbook using fail and when together
  - fail:
      msg: The system may not be provisioned according to the CMDB status.
    when: cmdb_status != "to-be-staged"
  ```



## pip

- 参数

  | Parameter    | Comments                                                     |
  | ------------ | ------------------------------------------------------------ |
  | pip          | The state of module (absent/forcereinstall/latest/present)   |
  | requirements | The path to a pip requirements file, which should be local to the remote system. File can be specified as a relative path if using the chdir option. |
  | name         | The name of a Python library to install or the url(bzr+,hg+,git+,svn+) of the remote package.                                                                                                                                          This can be a list (since 2.2) and contain version specifiers (since 2.7). |
  | extra_args   | Extra arguments passed to pip.                               |
  | version      | The version number to install of the Python library specified in the *name* parameter. |

  

- 示例

  ```yaml
  # Install (Bottle) python package.
  - pip:
      name: bottle
  
  # Install (Bottle) python package on version 0.11.
  - pip:
      name: bottle==0.11
  
  # Install (bottle) python package with version specifiers
  - pip:
      name: bottle>0.10,<0.20,!=0.11
  
  # Install multi python packages with version specifiers
  - pip:
      name:
        - django>1.11.0,<1.12.0
        - bottle>0.10,<0.20,!=0.11
  
  # Install python package using a proxy - it doesn't use the standard environment variables, please use the CAPITALIZED ones below
  - pip:
      name: six
    environment:
      HTTP_PROXY: '127.0.0.1:8080'
      HTTPS_PROXY: '127.0.0.1:8080'
  
  # Install (MyApp) using one of the remote protocols (bzr+,hg+,git+,svn+). You do not have to supply '-e' option in extra_args.
  - pip:
      name: svn+http://myrepo/svn/MyApp#egg=MyApp
  
  # Install MyApp using one of the remote protocols (bzr+,hg+,git+).
  - pip:
      name: git+http://myrepo/app/MyApp
  
  # Install (MyApp) from local tarball
  - pip:
      name: file:///path/to/MyApp.tar.gz
  
  # Install (Bottle) into the specified (virtualenv), inheriting none of the globally installed modules
  - pip:
      name: bottle
      virtualenv: /my_app/venv
  
  # Install (Bottle) into the specified (virtualenv), inheriting globally installed modules
  - pip:
      name: bottle
      virtualenv: /my_app/venv
      virtualenv_site_packages: yes
  
  # Install (Bottle) into the specified (virtualenv), using Python 2.7
  - pip:
      name: bottle
      virtualenv: /my_app/venv
      virtualenv_command: virtualenv-2.7
  
  # Install (Bottle) within a user home directory.
  - pip:
      name: bottle
      extra_args: --user
  
  # Install specified python requirements.
  - pip:
      requirements: /my_app/requirements.txt
  
  # Install specified python requirements in indicated (virtualenv).
  - pip:
      requirements: /my_app/requirements.txt
      virtualenv: /my_app/venv
  
  # Install specified python requirements and custom Index URL.
  - pip:
      requirements: /my_app/requirements.txt
      extra_args: -i https://example.com/pypi/simple
  
  # Install specified python requirements offline from a local directory with downloaded packages.
  - pip:
      requirements: /my_app/requirements.txt
      extra_args: "--no-index --find-links=file:///my_downloaded_packages_dir"
  
  # Install (Bottle) for Python 3.3 specifically,using the 'pip-3.3' executable.
  - pip:
      name: bottle
      executable: pip-3.3
  
  # Install (Bottle), forcing reinstallation if it's already installed
  - pip:
      name: bottle
      state: forcereinstall
  
  # Install (Bottle) while ensuring the umask is 0022 (to ensure other users can use it)
  - pip:
      name: bottle
      umask: "0022"
    become: True
  ```



## package

- 示例

  ```yaml
  - name: install ntpdate
    package:
      name: ntpdate
      state: present
  
  # This uses a variable as this changes per distribution.
  - name: remove the apache package
    package:
      name: "{{ apache }}"
      state: absent
  ```

  

## service

- 参数

  | Parameter | Comments                                                     |
  | --------- | ------------------------------------------------------------ |
  | name      | Name of the service.                                         |
  | enabled   | Whether the service should start on boot.                                                                                       **At least one of state and enabled are required.** |
  | state     | `started`/`stopped` are idempotent actions that will not run commands unless necessary.                                                                                                                                          `restarted` will always bounce the service.                                                                                 `reloaded` will always reload.                                                                                                         Note that reloaded will start the service if it is not already started, even if your chosen init system wouldn't normally. |

- 示例

  ```yaml
  - name: Start service httpd, if not started
    service:
      name: httpd
      state: started
  
  - name: Stop service httpd, if started
    service:
      name: httpd
      state: stopped
  
  - name: Restart service httpd, in all cases
    service:
      name: httpd
      state: restarted
  
  - name: Reload service httpd, in all cases
    service:
      name: httpd
      state: reloaded
  
  - name: Enable service httpd, and not touch the state
    service:
      name: httpd
      enabled: yes
  
  - name: Start service foo, based on running process /usr/bin/foo
    service:
      name: foo
      pattern: /usr/bin/foo
      state: started
  
  - name: Restart network service for interface eth0
    service:
      name: network
      state: restarted
      args: eth0
  ```



## User

- 参数

  | Parameter | Comments                                                     |
  | --------- | ------------------------------------------------------------ |
  | name      | Name of the user to create, remove or modify.                |
  | state     | Whether the account should exist or not, taking action if the state is different from what is stated. |
  | shell     | Optionally set the user's shell.                                                                                                      On macOS, before Ansible 2.5, the default shell for non-system users was `/usr/bin/false`. Since Ansible 2.5, the default shell for non-system users on macOS is `/bin/bash`.                                                                                                                                    On other operating systems, the default shell is determined by the underlying tool being used. See Notes for details. |
  | comment   | Optionally sets the description (aka *GECOS*) of user account. |
  | append    | If `yes`, add the user to the groups specified in `groups`.                                                          If `no`, user will only be added to the groups specified in `groups`, removing them from all other groups. |
  | group     | Optionally sets the user's primary group (takes a group name). |
  | remove    | This only affects `state=absent`, it attempts to remove directories associated with the user.                                                                                                                                           The behavior is the same as `userdel --remove`, check the man page for details and support. |
  | expires   | An expiry time for the user in epoch, it will be ignored on platforms that do not support this.                                                                                                                                  Currently supported on GNU/Linux, FreeBSD, and DragonFlyBSD.                                        Since Ansible 2.6 you can remove the expiry time specify a negative value. Currently supported on GNU/Linux and FreeBSD. |

- 示例

  ```yaml
  - name: Add the user 'johnd' with a specific uid and a primary group of 'admin'
    user:
      name: johnd
      comment: John Doe
      uid: 1040
      group: admin
  
  - name: Add the user 'james' with a bash shell, appending the group 'admins' and 'developers' to the user's groups
    user:
      name: james
      shell: /bin/bash
      groups: admins,developers
      append: yes
  
  - name: Remove the user 'johnd'
    user:
      name: johnd
      state: absent
      remove: yes
  
  - name: Create a 2048-bit SSH key for user jsmith in ~jsmith/.ssh/id_rsa
    user:
      name: jsmith
      generate_ssh_key: yes
      ssh_key_bits: 2048
      ssh_key_file: .ssh/id_rsa
  
  - name: Added a consultant whose account you want to expire
    user:
      name: james18
      shell: /bin/zsh
      groups: developers
      expires: 1422403387
  
  - name: Starting at Ansible 2.6, modify user, remove expiry time
    user:
      name: james18
      expires: -1
  ```

  

## authorized_key

- 参数

  | Parameter | Comments                                                     |
  | --------- | ------------------------------------------------------------ |
  | user      | The username on the remote host whose authorized_keys file will be modified. |
  | key       | The SSH public key(s), as a string or (since Ansible 1.9) url (https://github.com/username.keys). |
  | state     | Whether the given key (with the given key_options) should or should not be in the file. |
  | path      | Alternate path to the authorized_keys file.                                                                                 When unset, this value defaults to *~/.ssh/authorized_keys*. |

  

- 示例

  ```yaml
  - name: Set authorized key taken from file
    authorized_key:
      user: charlie
      state: present
      key: "{{ lookup('file', '/home/charlie/.ssh/id_rsa.pub') }}"
  
  - name: Set authorized keys taken from url
    authorized_key:
      user: charlie
      state: present
      key: https://github.com/charlie.keys
  
  - name: Set authorized key in alternate location
    authorized_key:
      user: charlie
      state: present
      key: "{{ lookup('file', '/home/charlie/.ssh/id_rsa.pub') }}"
      path: /etc/ssh/authorized_keys/charlie
      manage_dir: False
  
  - name: Set up multiple authorized keys
    authorized_key:
      user: deploy
      state: present
      key: '{{ item }}'
    with_file:
      - public_keys/doe-jane
      - public_keys/doe-john
  
  - name: Set authorized key defining key options
    authorized_key:
      user: charlie
      state: present
      key: "{{ lookup('file', '/home/charlie/.ssh/id_rsa.pub') }}"
      key_options: 'no-port-forwarding,from="10.0.1.1"'
  
  - name: Set authorized key without validating the TLS/SSL certificates
    authorized_key:
      user: charlie
      state: present
      key: https://github.com/user.keys
      validate_certs: False
  
  - name: Set authorized key, removing all the authorized keys already set
    authorized_key:
      user: root
      key: '{{ item }}'
      state: present
      exclusive: True
    with_file:
      - public_keys/doe-jane
  
  - name: Set authorized key for user ubuntu copying it from current user
    authorized_key:
      user: ubuntu
      state: present
      key: "{{ lookup('file', lookup('env','HOME') + '/.ssh/id_rsa.pub') }}"
  ```



## git

- 参数

  |      |      |
  | ---- | ---- |
  |      |      |
  |      |      |
  |      |      |

- 示例

  ```yaml
  # Example git checkout from Ansible Playbooks
  - git:
      repo: 'https://foosball.example.org/path/to/repo.git'
      dest: /srv/checkout
      version: release-0.22
  
  # Example read-write git checkout from github
  - git:
      repo: git@github.com:mylogin/hello.git
      dest: /home/mylogin/hello
  
  # Example just ensuring the repo checkout exists
  - git:
      repo: 'https://foosball.example.org/path/to/repo.git'
      dest: /srv/checkout
      update: no
  
  # Example just get information about the repository whether or not it has
  # already been cloned locally.
  - git:
      repo: 'https://foosball.example.org/path/to/repo.git'
      dest: /srv/checkout
      clone: no
      update: no
  
  # Example checkout a github repo and use refspec to fetch all pull requests
  - git:
      repo: https://github.com/ansible/ansible-examples.git
      dest: /src/ansible-examples
      refspec: '+refs/pull/*:refs/heads/*'
  
  # Example Create git archive from repo
  - git:
      repo: https://github.com/ansible/ansible-examples.git
      dest: /src/ansible-examples
      archive: /tmp/ansible-examples.zip
  
  # Example clone a repo with separate git directory
  - git:
      repo: https://github.com/ansible/ansible-examples.git
      dest: /src/ansible-examples
      separate_git_dir: /src/ansible-examples.git
  ```

  