# Ansible Role: Java


Installs Java for RedHat/CentOS and Debian/Ubuntu linux servers.

## Example Playbook (using default package)

    - hosts: servers
      roles:
        - role: ./roles/java
          become: yes

## Example Playbook (install OpenJDK 8)

For RHEL / CentOS:

    - hosts: server
      roles:
        - role: ./roles/java
          when: "ansible_os_family == 'RedHat'"
          java_packages:
            - java-1.8.0-openjdk

For Ubuntu < 16.04:

    - hosts: server
      tasks:
        - name: installing repo for Java 8 in Ubuntu
  	      apt_repository: repo='ppa:openjdk-r/ppa'
    
    - hosts: server
      roles:
        - role: ./roles/java
          when: "ansible_os_family == 'Debian'"
          java_packages:
            - openjdk-8-jdk

## License

MIT 

## Author Information

This role was created in 2020 by [Arbaz Khan]
