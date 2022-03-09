# Testing purpose

The content in this folder use for testing purpose only

We will use docker environment as the testing place to test ansible scripts

## Usage

**Step 1**: Create your own ssh key, if you already have one please skip this step

**Step 2**: Copy the public key and paste it into file `authorized_keys`

**Step 3**: Build testing docker image

```bash
  docker build -t ubuntu-test .
```

**Step 4**: Run the docker image to simulate environment

```bash
  docker run -it -d --name test -p 2222:22 --privileged ubuntu-test:latest tail -f /dev/null
```

**Step 5**: Try to access to the docker container with ssh to ensure ansible can access

```bash
  ssh -i <your-private-key> ubuntu@localhost -p 2222
```

**Step 6**: Go to the playbook that we want to test and update the host file
  
```yml
[remote]
server ansible_ssh_host=localhost ansible_user=ubuntu ansible_port=2222 ansible_become_user=root ansible_ssh_private_key_file=<Your-public-key>
```

> **Note**: Remeber to set the `ansible_ssh_private_key_file` with the path to your private key
