# firstboot configuration for ansible

This basically sets up ssh for ansible,
which normally is configured as part of
a custom kickstart or saved base image.

## how to run

This example limits to a group 'raspi' containing the new host we want to one-time configure.

Full syntax:

    ansible-playbook site.yml -i hosts --limit=raspi -k -u pi -b --become-user=root --become-method=sudo
       -k = prompt for password
       -u = which user to ssh into
       -b = become a different user
            --become-user = who to become
            --become-method = how to become them

Shorter (deprecated) syntax:

    ansible-playbook site.yml -i hosts --limit=raspi -k -u pi --sudo



