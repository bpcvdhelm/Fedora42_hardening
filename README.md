# Fedora 42 hardening
In the beginning I did the hardening by Head, with in the end forgetting to harden stuff. Must be the age!
Then I had a bunch of shell scripts. Just a lot of work and boring.

So for now I created an ansible job. Just install ansible, become root and execute ansible-playbook ansible.yml.

Steps in the job:
- Run 'authselect local with-silent-lastlog' when different. You can change this to any setting you want. Do not forget the checking step!
- Store the keys of my yubikeys. This prevents me from using the tool and saves me a lot of time!
- Store the pam file that includes required u2f authentication. This file is included when needed.
- Store default polkit-1 (it is not there) including u2f-required. This demands u2f use when elevate priviledge.
- Add u2f demand when using sudo.
- Disable, in my mind, unneeded services.
- Remove some scary pam files.
- Store and activate network trackability reduction config. Got it somewhere from internet and I haven't checked if it works?
- Store and activate a safe chony.
- Set the host name.
- Prevent showing the user list when loging in with gdm. In my mind the userid is also secret. It cannot be masked during typing in.
- Here at house the list is longer with private stuff...
