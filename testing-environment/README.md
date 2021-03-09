# Testing purpose 

The content in this folder use for testing purpose only

We will use docker environment as the testing place to test ansible scripts

## Usage

**Step 1**: Build testing docker image

```bash
  docker build -t ubuntu-test .
```

**Step 2**: Run the docker image to simulate environment

```bash
  docker run -it -d --name test -p 2222:22 --privileged ubuntu-test:latest tail -f /dev/null
```

**Step 3**: Go to the playbook that we want to test and update the host file
  
```yml
[remote]
server ansible_ssh_host=localhost ansible_user=ubuntu ansible_port=2222 ansible_become_user=root ansible_ssh_private_key_file=~/.ssh/tien_all
```
