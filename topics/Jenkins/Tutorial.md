# Install on OpenSuse
 ## update system
sudo zypper refresh
sudo zypper update

## Install java
    sudo zypper install java-11-openjdk

##  Add Jenkins Repository
    sudo zypper addrepo -f https://pkg.jenkins.io/opensuse-stable/ jenkins
    sudo zypper refresh

## Import Jenkins Key
    sudo rpm --import https://pkg.jenkins.io/jenkins.io.key

## Install jenkins
    zypper install dejavu-fonts fontconfig java-17-openjdk
    zypper install jenkins

    mkdir -p /var/cache/jenkins/tmp
    chown -R jenkins:jenkins /var/cache/jenkins/tmp
    systemctl show jenkins
    systemd-analyze verify jenkins.service
    systemctl start jenkins
    systemctl --full status jenkins
    journalctl -u jenkins
    sudo mkdir -p /etc/init.d/rc5.d
    sudo mkdir -p /etc/init.d/rc3.d

    systemctl enable jenkins
    systemctl start jenkins

    sudo firewall-cmd --permanent --add-port=8080/tcp
    sudo firewall-cmd --reload
    sudo systemctl stop firewalld

    http://your_server_ip:8080

## Unlock Jenkins
    sudo cat /var/lib/jenkins/secrets/initialAdminPassword




