OCP GET Token
=============

This is a simple role designed to get an OpenShift user access token from a given OpenShift username and password.

Requirements
------------

* curl command.
* grep command.

Role Variables
--------------

### Inputs

Vars used by this role are usually provided at the execution time and defined dinamically by the Ansible playbook.

**Set Fact**

|Variable|Description|Type|
|---|---|---|
|ocp|Red Hat OpenShift console|String|

**Vars Prompt**

|Variable|Description|Type|
|---|---|---|
|ocp_username|Red Hat OpenShift username|String|
|ocp_password|Red Hat OpenShift User password|String|

### Outputs

**Set Fact**

|Variable|Description|Type|
|---|---|---|
|ocp_token|Red Hat OpenShift Access Token|String|

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use this role:

```
---
- hosts: localhost
  gather_facts: no
  vars:
    ocp: https://master.example.com:8443
    ocp_username: developer
    ocp_password: openshift
  tasks:
  - name: "[include_role] Role Name: ocp-get-token"
    include_role:
      name: ocp-get-token
  - name: "[debug] Pring OCP User Access Token"
    debug:
      msg: "Access Token: {{ ocp_token }}"
```

License
-------

BSD

Author Information
------------------

* Francisco Rodríguez Rocha @Red Hat

Main References
---------------

* [Obtaining OAuth Tokens](https://docs.openshift.com/container-platform/3.5/architecture/additional_concepts/authentication.html#obtaining-oauth-tokens)

