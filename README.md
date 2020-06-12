[![Build Status](https://travis-ci.com/darkwizard242/ansible-role-inspec.svg?branch=master)](https://travis-ci.com/darkwizard242/ansible-role-inspec) ![Ansible Role](https://img.shields.io/ansible/role/47528?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/47528?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/47528?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-inspec&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-inspec) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-inspec?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-inspec?color=orange&style=flat-square)

# Ansible Role: Inspec

Role to install (_by default_) extended [inspec](https://github.com/inspec/inspec) on **Debian**, **Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
inspec_app: inspec
inspec_version: 4.20.2
inspec_debian_os: "{{ ansible_distribution|lower }}"
inspec_debian_os_version: "{{ ansible_distribution_major_version }}"
inspec_debian_os_arch: amd64
inspec_debian_dl_url: "https://packages.chef.io/files/stable/{{ inspec_app }}/{{ inspec_version }}/{{ inspec_debian_os }}/{{ inspec_debian_os_version }}/{{ inspec_app }}_{{ inspec_version }}-1_{{ inspec_debian_os_arch }}.deb"
inspec_ubuntu_os: "{{ ansible_distribution|lower }}"
inspec_ubuntu_os_version: "{{ ansible_distribution_version}}"
inspec_ubuntu_os_arch: amd64
inspec_ubuntu_dl_url: "https://packages.chef.io/files/stable/{{ inspec_app }}/{{ inspec_version }}/{{ inspec_debian_os }}/{{ inspec_debian_os_version }}/{{ inspec_app }}_{{ inspec_version }}-1_{{ inspec_debian_os_arch }}.deb"
inspec_el_os: el
inspec_el_os_arch: x86_64
inspec_el_os_version: "{{ ansible_distribution_major_version }}"
inspec_el_dl_url: "https://packages.chef.io/files/stable/{{ inspec_app }}/{{ inspec_version }}/{{ inspec_el_os }}/{{ inspec_el_os_version }}/{{ inspec_app }}-{{ inspec_version }}-1.el{{ inspec_el_os_version }}.{{ inspec_el_os_arch }}.rpm"
```

### Variables table:

Variable                 | Description
------------------------ | ---------------------------------------------------------------------------------------------------------------------------------
inspec_app               | Defines the app to install i.e. **inspec**
inspec_version           | Defined to dynamically fetch the desired version to install. Defaults to: **4.20.2**
inspec_debian_os         | Defined to collect the operating system name and store it's value in lowercase
inspec_debian_os_version | Gathers facts to collect OS Version.
inspec_debian_os_arch    | Defines os architecture. Used for obtaining the correct type of binaries based on OS System Architecture. Defaults to: **amd64**
inspec_debian_dl_url     | Defines URL to download the inspec debian file from for Debain Systems.
inspec_ubuntu_os         | Defined to collect the operating system name and store it's value in lowercase
inspec_ubuntu_os_version | Gathers facts to collect OS Version.
inspec_ubuntu_os_arch    | Defines os architecture. Used for obtaining the correct type of binaries based on OS System Architecture. Defaults to: **amd64**
inspec_ubuntu_dl_url     | Defines URL to download the inspec debian file from for Ubuntu Systems.
inspec_el_os             | Defined to for EL based systems.
inspec_el_os_version     | Gathers facts to collect OS major version on EL based systems.
inspec_el_os_arch        | Defines os architecture. Used for obtaining the correct type of binaries based on OS System Architecture. Defaults to: **x86_64**
inspec_el_dl_url         | Defines URL to download the inspec rpm file from for EL based Operating Systems.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **inspec**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.inspec
```

For customizing behavior of role (i.e. specifying the desired **inspec** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.inspec
  vars:
    inspec_version: 4.18.99
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-inspec/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.linkedin.com/in/ali-muhammad-759791130/).
