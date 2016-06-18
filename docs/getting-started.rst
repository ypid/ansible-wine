Getting started
===============

.. contents::
   :local:

.. include:: includes/all.rst


Example inventory
-----------------

Add the hosts on which Wine should be setup to the
``debops_service_wine`` Ansible inventory group:

.. code:: ini

    [debops_service_wine]
    hostname

Example playbook
----------------

Here's an example playbook that can be used to setup Wine:

.. literalinclude:: playbooks/wine.yml
   :language: yaml

This playbooks is shipped with this role under
:file:`docs/playbooks/wine.yml` from which you can symlink it to your
playbook directory.
In case you use multiple roles maintained by ypid_, consider
using the `ypid-ansible-common`_.

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after host is first
configured to speed up playbook execution, when you are sure that most of the
configuration has not been changed.

Available role tags:

``role::wine``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.

``role::wine:pkgs``
  Tasks related to system package management like installing, upgrading or
  removing packages.
