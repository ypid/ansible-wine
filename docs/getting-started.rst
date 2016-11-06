Getting started
===============

.. include:: includes/all.rst

.. contents::
   :local:


Example inventory
-----------------

Add the hosts on which Wine should be setup to the
``ypid_service_wine`` Ansible inventory group:

.. code:: ini

   [ypid_service_wine]
   hostname

Example playbook
----------------

Here's an example playbook that uses the ``ypid.wine`` role:

.. literalinclude:: playbooks/wine.yml
   :language: yaml

The playbooks is shipped with this role under
:file:`docs/playbooks/wine.yml` from which you can symlink it to your
playbook directory.
In case you use multiple roles maintained by ypid_, consider
using the `ypid-ansible-common`_.

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after a host was first
configured to speed up playbook execution, when you are sure that most of the
configuration is already in the desired state.

Available role tags:

``role::wine``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.

``role::wine:pkgs``
  Tasks related to system package management like installing or
  removing packages.
