# RedHat

### Red Hat Enterprise Linux (RHEL) Command Line Interface (CLI)

#### System Information and Management

- **View System Information:**
  ```bash
  uname -a
  ```

- **View RHEL Version:**
  ```bash
  cat /etc/redhat-release
  ```

- **Check Kernel Version:**
  ```bash
  uname -r
  ```

- **List All Loaded Kernel Modules:**
  ```bash
  lsmod
  ```

- **View CPU Information:**
  ```bash
  lscpu
  ```

- **View Memory Information:**
  ```bash
  free -h
  ```

#### Package Management

- **List Installed Packages:**
  ```bash
  rpm -qa
  ```

- **Install a Package:**
  ```bash
  yum install package_name
  ```

- **Remove a Package:**
  ```bash
  yum remove package_name
  ```

- **Update All Packages:**
  ```bash
  yum update
  ```

- **Search for a Package:**
  ```bash
  yum search package_name
  ```

- **List Available Updates:**
  ```bash
  yum check-update
  ```

- **Install a Package from an RPM File:**
  ```bash
  rpm -ivh package_name.rpm
  ```

- **Upgrade a Package with RPM:**
  ```bash
  rpm -Uvh package_name.rpm
  ```

#### User and Group Management

- **Add a New User:**
  ```bash
  useradd username
  ```

- **Delete a User:**
  ```bash
  userdel username
  ```

- **Change User Password:**
  ```bash
  passwd username
  ```

- **Add a Group:**
  ```bash
  groupadd groupname
  ```

- **Delete a Group:**
  ```bash
  groupdel groupname
  ```

- **Add User to Group:**
  ```bash
  usermod -aG groupname username
  ```

- **List All Users:**
  ```bash
  cat /etc/passwd
  ```

- **List All Groups:**
  ```bash
  cat /etc/group
  ```

#### File and Directory Management

- **List Files and Directories:**
  ```bash
  ls -l
  ```

- **Change Directory:**
  ```bash
  cd /path/to/directory
  ```

- **Create a New Directory:**
  ```bash
  mkdir directoryname
  ```

- **Remove a Directory:**
  ```bash
  rmdir directoryname
  ```

- **Copy Files:**
  ```bash
  cp sourcefile destinationfile
  ```

- **Move Files:**
  ```bash
  mv sourcefile destinationfile
  ```

- **Delete Files:**
  ```bash
  rm filename
  ```

- **Search for Files:**
  ```bash
  find /path -name filename
  ```

- **Find Files Containing Specific Text:**
  ```bash
  grep -r "searchtext" /path/to/directory
  ```

#### Network Management

- **View Network Configuration:**
  ```bash
  ip addr show
  ```

- **View Routing Table:**
  ```bash
  ip route show
  ```

- **Configure Network Interface:**
  ```bash
  nmtui
  ```

- **Restart Network Service:**
  ```bash
  systemctl restart network
  ```

- **Check Network Service Status:**
  ```bash
  systemctl status network
  ```

- **Ping a Host:**
  ```bash
  ping hostname
  ```

- **Trace Route to a Host:**
  ```bash
  traceroute hostname
  ```

- **View Network Connections:**
  ```bash
  netstat -an
  ```

- **Display Open Ports:**
  ```bash
  ss -tuln
  ```

#### Firewall Management

- **Check Firewall Status:**
  ```bash
  systemctl status firewalld
  ```

- **Start Firewall Service:**
  ```bash
  systemctl start firewalld
  ```

- **Stop Firewall Service:**
  ```bash
  systemctl stop firewalld
  ```

- **Enable Firewall Service:**
  ```bash
  systemctl enable firewalld
  ```

- **Disable Firewall Service:**
  ```bash
  systemctl disable firewalld
  ```

- **Add Firewall Rule:**
  ```bash
  firewall-cmd --permanent --add-port=port_number/tcp
  firewall-cmd --reload
  ```

- **Remove Firewall Rule:**
  ```bash
  firewall-cmd --permanent --remove-port=port_number/tcp
  firewall-cmd --reload
  ```

- **List All Firewall Rules:**
  ```bash
  firewall-cmd --list-all
  ```

#### System Monitoring

- **View System Load:**
  ```bash
  uptime
  ```

- **View Memory Usage:**
  ```bash
  free -m
  ```

- **Monitor System Processes:**
  ```bash
  top
  ```

- **View Disk Usage:**
  ```bash
  df -h
  ```

- **Check Disk Space Usage by Directory:**
  ```bash
  du -sh /path/to/directory
  ```

- **List All Running Processes:**
  ```bash
  ps -aux
  ```

- **View System Logs:**
  ```bash
  journalctl -xe
  ```

- **Monitor Real-Time Logs:**
  ```bash
  tail -f /var/log/messages
  ```

#### Disk Management

- **List All Disks:**
  ```bash
  lsblk
  ```

- **Check Disk Partitions:**
  ```bash
  fdisk -l
  ```

- **Create a New Partition:**
  ```bash
  fdisk /dev/sda
  ```

- **Format Partition:**
  ```bash
  mkfs.ext4 /dev/sda1
  ```

- **Mount a Partition:**
  ```bash
  mount /dev/sda1 /mnt
  ```

- **Unmount a Partition:**
  ```bash
  umount /mnt
  ```

- **Check Disk Filesystem:**
  ```bash
  fsck /dev/sda1
  ```

#### Service Management

- **List All Services:**
  ```bash
  systemctl list-units --type=service
  ```

- **Start a Service:**
  ```bash
  systemctl start service_name
  ```

- **Stop a Service:**
  ```bash
  systemctl stop service_name
  ```

- **Restart a Service:**
  ```bash
  systemctl restart service_name
  ```

- **Enable a Service:**
  ```bash
  systemctl enable service_name
  ```

- **Disable a Service:**
  ```bash
  systemctl disable service_name
  ```

- **Check Service Status:**
  ```bash
  systemctl status service_name
  ```

#### Advanced Techniques

- **Configure SELinux Mode:**
  ```bash
  setenforce 0  # Permissive Mode
  setenforce 1  # Enforcing Mode
  ```

- **Check SELinux Status:**
  ```bash
  sestatus
  ```

- **List All SELinux Booleans:**
  ```bash
  getsebool -a
  ```

- **Enable/Disable SELinux Boolean:**
  ```bash
  setsebool boolean_name on/off
  ```

- **Generate SSH Key Pair:**
  ```bash
  ssh-keygen -t rsa -b 2048
  ```

- **Copy SSH Key to Remote Host:**
  ```bash
  ssh-copy-id user@remote_host
  ```

- **Mount NFS Share:**
  ```bash
  mount -t nfs remote_host:/path/to/share /mnt
  ```

- **Mount CIFS Share:**
  ```bash
  mount -t cifs //remote_host/share /mnt -o username=user,password=pass
  ```

- **Create Logical Volume:**
  ```bash
  lvcreate -L 10G -n lv_name vg_name
  ```

- **Extend Logical Volume:**
  ```bash
  lvextend -L +10G /dev/vg_name/lv_name
  ```

- **Reduce Logical Volume:**
  ```bash
  lvreduce -L -10G /dev/vg_name/lv_name
  ```

- **Display Logical Volumes:**
  ```bash
  lvdisplay
  ```

- **Display Volume Groups:**
  ```bash
  vgdisplay
  ```

- **Display Physical Volumes:**
  ```bash
  pvdisplay
  ```

- **Set System Timezone:**
  ```bash
  timedatectl set-timezone America/New_York
  ```

- **Synchronize System Time with NTP:**
  ```bash
  timedatectl set-ntp true
  ```

### Summary

This extensive list of RHEL CLI commands covers a broad range of tasks for system management, package management, user and group management, file and directory operations, network configuration, firewall management, system monitoring, disk management, service management, and advanced techniques. These commands
