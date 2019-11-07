Ansible Deploy for DaaC
============

This playbook deploys the Desktop Containers as a Service Project ontop OpenShift (including Code Ready Containers)

Demo
------------
![Demo](./demo/daac-ansible.svg)


Requirements
------------

This module requires the following python requirements:
* ansible
* openshift
* kubernetes-validate

Role Variables
--------------

```bash
# Defaults
NAMESPACE: guac
OCP_APPS_DOMAIN: "{{ VAULT_OCP_APPS_DOMAIN }}"

# description: POSTGRES username
POSTGRES_USER: guac

# description: POSTGRES password
POSTGRES_PASSWORD: "{{ VAULT_POSTGRES_PASSWORD }}"

# description: POSTGRES database name
POSTGRES_DATABASE: guacamole_db

# description: Guacadmin Password
GUACADMIN_PASSWORD: "{{ VAULT_GUACADMIN_PASSWORD }}"

# description: openid-authorization-endpoint
oauth_endpoint: "{{ vault_oauth_endpoint }}"

# description: openid-jwks-endpoint
oauth_jwks_endpoint: "{{ vault_oauth_jwks_endpoint }}"

# description: openid-issuer
oauth_issuer: "{{ vault_oauth_issuer }}"

# description: openid-client-id
oauth_client_id: "{{ vault_oauth_client_id }}"

# description: openid-client-secret
oauth_client_secret: "{{ vault_oauth_client_secret }}"

# description: openid-redirect-uri
oauth_redirect_uri: "https://guac.{{ OCP_APPS_DOMAIN }}"

# description: openid-username-claim-type
openid_username_claim_type: email

auth0_domain: "{{ vault_auth0_domain }}"

# description: Log Level
LOG_LEVEL: INFO
```

Vault Variables
---------------

```bash
# Defaults POSTGRES password
VAULT_POSTGRES_PASSWORD: 

# description: Guacadmin Password
VAULT_GUACADMIN_PASSWORD: 

# description: openid-authorization-endpoint
vault_oauth_endpoint: 

# description: openid-jwks-endpoint
vault_oauth_jwks_endpoint: 

# description: openid-issuer
vault_oauth_issuer: 

# description: openid-client-id
vault_oauth_client_id: 

# description: openid-client-secret
vault_oauth_client_secret:

# description: auth0 domain
vault_auth0_domain:

# description: apps.domain of OpenShift
VAULT_OCP_APPS_DOMAIN:
```

