Certbot Cloudfare
=========

Use Cloudflare DNS for wildcard certbot generation

Requirements
------------

- Cloudflare DNS setup
- Cloudflare API Key
- Wildcard domian setup (for wildcard certs) [*.domain.com or *.subdomain.domain.com]

Role Variables
--------------

    certbot_cloudflare_email: "cloudflare@example.com"

Your Cloudflare email address

    certbot_cloudflare_api_key: ''

Your Cloudflare Global API Key, optionally encryped `ansible-vault encrypt_string 'cloudflareAPIKey' --name 'certbot_cloudflare_api_key'`

    certbot_certs:
      - email: {{certbot_cloudflare_email}}
        domains:
          - *.example3.com

The wildcard domain to create the cert for. For non-wildcard domains I recommend using [geerlingguy.certbot](https://github.com/geerlingguy/ansible-role-certbot)


Dependencies
------------

- geerlingguy.pip
- geerlingguy.certbot

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
    
      vars:
        certbot_cloudflare_email: "cloudflare@example.com"
        certbot_cloudflare_api_key: 'myapikey'
        certbot_certs:
          - email: {{certbot_cloudflare_email}}
            domains:
              - *.example3.com

      roles:
         - michaelpporter.certbot-cloudflare

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2018 by [Michael Porter](https://www.michaelpporter.com/).

