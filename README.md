# PHP Roles Collection for Ansible

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

## Usage

Install this collection locally:

    ansible-galaxy collection install nholuong.php_roles -p ./collections

Then you can use the roles from the collection in your playbooks:

    ---
    - hosts: all
    
      collections:
        - nholuong.php_roles
    
      roles:
        - php
        - role: php-versions
          vars:
            php_version: '7.3'

> If you want to be more explicit, you can use the fully-qualified role name when referring to a role in this collection, like `nholuong.php_roles.php` instead of just `php`. This could be helpful if, for example, you maintain a separate `php` role in another place on your local workstation.

## Development

Currently, all the PHP roles (inside `roles/`) are Git submodules, and work on the roles themselves should take place in the upstream Role repository. At some point, the roles might move into this repository for their canonical home.

This collection has some integration tests (inside `tests/`), however, which pull all the roles together and ensure they work in tandem on the latest supported platforms.

The integrated tests use `ansible-test`. You can run them with the following command:

    ansible-test integration --docker nholuong/docker-ubuntu1804-ansible

> Note: You can switch out `ubuntu1804` with any other supported operating system (e.g. `centos7`).

### Pushing a new version

Before tagging a new version, make sure all the git submodules are up to date:

    git submodule update --recursive --remote

Then commit and push all changes, and make sure all tests are passing.

Then tag the new version of the collection and push the tag.

Once pushed, if tests pass, Travis CI will deploy the new collection version using the playbook in `scripts/deploy.yml`. That directory also contains the `galaxy.yml` template that will be used to build the collection metadata.

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
