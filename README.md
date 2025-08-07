[![CI](https://github.com/de-it-krachten/ansible-role-windows_features/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-windows_features/actions?query=workflow%3ACI)


# ansible-role-windows_features

Installs Windows features



## Dependencies

#### Roles
None

#### Collections
- ansible.windows
- ansible.windows

## Platforms

Supported platforms

- Windows Server 2012 R2<sup>1</sup>
- Windows Server 2016<sup>1</sup>
- Windows Server 2019<sup>1</sup>
- Windows Server 2022<sup>1</sup>
- Windows Server 2025<sup>1</sup>

Note:
<sup>1</sup> : no automated testing is performed on these platforms

## Role Variables
### defaults/main.yml
<pre><code>
## List of Windows features to install
# windows_features:
#   - name: AD-domain-services
#     include_management_tools: true
#     include_sub_features: true

# Skip required reboot
windows_features_skip_reboot: false
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'windows_features'
  hosts: all
  become: 'yes'
  vars:
    windows_features:
      - name: D-domain-services
        include_management_tools: true
        include_sub_features: true
  tasks:
    - name: Include role 'windows_features'
      ansible.builtin.include_role:
        name: windows_features
</pre></code>
