
# Week 1 – Day 4: Linux Networking and Git Workflow Practice

## Part A: Linux Networking and Server Connectivity

### 1. Understanding Network Interfaces

A network interface connects a computer to a network.

Command:

```bash
ip -br addr
```

Displays network interfaces and their IP addresses in a brief format.

Important interfaces observed:

- `lo`: Loopback interface used for local communication.
- `eth0`: Main network interface used by the Linux environment.
- `127.0.0.1`: Localhost IPv4 address.
- `172.27.45.37`: IP address assigned to the Linux environment.

### 2. Understanding IP Addresses

An IP address identifies a device on a network.

Command:

```bash
ip addr
```

Displays detailed information about network interfaces, including IP addresses, network masks, and interface status.

### 3. Understanding Routing Tables

A routing table determines where network traffic should go.

Command:

```bash
ip route
```

Important concepts:

- Default gateway: The next network device used to reach external networks.
- Default route: The route used when no more specific route exists.
- Network route: Defines how to reach a particular network.

Example observed:

```text
default via 172.27.32.1 dev eth0
```

This indicates that traffic destined for external networks is sent through the gateway `172.27.32.1`.

### 4. Checking Listening Ports and Network Services

A port identifies a communication endpoint used by an application or service.

Command:

```bash
sudo ss -tulnp
```

Options:

- `-t`: Display TCP sockets.
- `-u`: Display UDP sockets.
- `-l`: Display listening sockets.
- `-n`: Display numerical addresses and ports.
- `-p`: Display processes using sockets.

To check Nginx:

```bash
sudo ss -tlnp | grep nginx
```

We observed Nginx listening on:

- `0.0.0.0:80`: Listening for IPv4 connections on all interfaces.
- `[::]:80`: Listening for IPv6 connections on all interfaces.

Port 80 is the default HTTP port.

### 5. Important Networking Concepts

- TCP: Provides reliable, connection-oriented communication.
- UDP: Provides connectionless communication.
- DNS: Translates domain names into IP addresses.
- HTTP: Protocol used for web communication.
- HTTPS: Encrypted HTTP communication.
- SSH: Secure protocol used to access remote systems.

### 6. Useful Networking Commands

```bash
ip -br addr
ip route
ip route get 1.1.1.1
sudo ss -tulnp
sudo ss -tlnp | grep nginx
getent hosts github.com
nslookup github.com
resolvectl status
ssh -V
sudo ufw status verbose
ping -c 4 172.27.32.1
nc -vz github.com 443
curl -I http://localhost
```

Purpose:

- `getent hosts`: Checks hostname resolution.
- `nslookup`: Queries DNS records.
- `resolvectl`: Displays DNS resolver information.
- `ssh -V`: Displays the installed SSH version.
- `ufw`: Manages the uncomplicated firewall.
- `ping`: Tests network connectivity.
- `nc`: Tests connectivity to a specific host and port.
- `curl -I`: Retrieves HTTP response headers.
- `ip route get`: Shows the route selected for a destination.

### 7. Testing the Local Web Server

Command:

```bash
curl -I http://localhost
```

This checks whether the local web server responds to an HTTP request.

Nginx was installed and running, listening on port 80.

---

## Part B: Git Workflow Practice

### 1. Understanding Git Branches

A Git branch is an independent line of development.

Branches allow developers to work on features without directly changing the main branch.

Common branches:

- `main`: The primary branch containing the stable project.
- Feature branch: Used to develop a particular feature.
- Documentation branch: Used to make documentation changes.

### 2. Checking Repository Status

```bash
cd ~/devops-labs
git status
git branch
```

- `git status`: Shows modified, staged, and untracked files.
- `git branch`: Lists local branches.
- The asterisk (*) identifies the currently active branch.

### 3. Creating and Switching to a Feature Branch

```bash
git switch -c feature/linux-documentation
```

This creates a new branch and switches to it.

To switch between branches:

```bash
git switch main
git switch feature/linux-documentation
```

### 4. Creating Documentation

Create a directory and file:

```bash
mkdir -p git-practice
nano git-practice/branching.md
```

The file documents the purpose of branching and the Git workflow being practised.

### 5. Staging and Committing Changes

```bash
git status
git add git-practice/branching.md
git commit -m "Add Git branching practice documentation"
```

Important concepts:

- `git add`: Stages changes for the next commit.
- `git commit`: Saves a snapshot of staged changes.
- Commit messages should describe the changes clearly.

### 6. Pushing a Feature Branch to GitHub

```bash
git push -u origin feature/linux-documentation
```

Explanation:

- `git push`: Uploads local commits to a remote repository.
- `origin`: The name of the remote repository.
- `-u`: Sets the upstream tracking relationship.
- `feature/linux-documentation`: The branch being uploaded.

After setting the upstream, future pushes can usually use:

```bash
git push
```

### 7. Merging Branches

Merging combines changes from one branch into another.

Example:

```bash
git switch main
git merge feature/linux-documentation
```

This merges the feature branch into `main`.

After merging:

```bash
git log --oneline --graph --all
```

This displays the commit history and branch structure.

Push the updated main branch:

```bash
git push
```

### 8. Understanding Remote Repositories

A remote repository is a version of the project hosted on a platform such as GitHub.

Useful commands:

```bash
git remote -v
git branch -a
git fetch
git pull
git push
```

- `git remote -v`: Displays configured remote repositories.
- `git branch -a`: Displays local and remote-tracking branches.
- `git fetch`: Downloads remote changes without merging them.
- `git pull`: Fetches and integrates remote changes.
- `git push`: Uploads local commits.

### 9. Pull Requests and Code Reviews

A Pull Request (PR) is a request to merge changes from one branch into another.

Typical workflow:

1. Create a feature branch.
2. Make changes.
3. Stage and commit the changes.
4. Push the feature branch to GitHub.
5. Open a Pull Request.
6. Review the changes.
7. Merge the Pull Request into the target branch.

Pull Requests allow developers to review code, discuss improvements, and identify problems before merging.

### 10. Git Workflow Best Practices

- Avoid developing directly on `main`.
- Use descriptive branch names.
- Write meaningful commit messages.
- Commit small, focused changes.
- Review changes before committing.
- Push feature branches to the remote repository.
- Use Pull Requests for collaboration and code reviews.
- Keep the main branch stable.

---

## Day 4 Summary

By completing Day 4, I practised:

### Linux Networking
- Identifying network interfaces.
- Understanding IP addresses.
- Reading routing tables.
- Identifying default gateways.
- Checking listening ports.
- Understanding TCP, UDP, DNS, HTTP, HTTPS, and SSH.
- Inspecting Nginx network connectivity.
- Learning commands for network troubleshooting.

### Git and GitHub
- Understanding Git branches.
- Creating and switching branches.
- Creating project documentation.
- Staging and committing changes.
- Pushing feature branches to GitHub.
- Merging branches.
- Inspecting commit history.
- Understanding remote repositories.
- Understanding Pull Requests and code reviews.

## Why These Skills Matter in DevOps

Linux networking helps DevOps engineers troubleshoot connectivity, diagnose server problems, understand ports, and maintain services.

Git and GitHub support collaboration, version control, change tracking, and code review. These skills are essential when building CI/CD pipelines and managing infrastructure code.

Day 4 strengthened my foundation in Linux administration, networking, and professional software development workflows.
