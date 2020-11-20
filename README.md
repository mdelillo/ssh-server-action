# SSH Server Action

This action starts an SSH server and makes it available using [ngrok](https://ngrok.com/). A free ngrok account will allow you to run a single SSH tunnel.

When the server is ready, you will see a message in your workflow output similar to the following:

```bash
To SSH to this runner: `ssh -i /path/to/private/key -p 11111 runner@0.tcp.ngrok.io`
```

Due to [an issue with workflow output](https://github.community/t/how-to-see-the-full-log-while-a-workflow-is-in-progress/17455), you will only see the message if you were already viewing the workflow logs when the message was printed (or when the workflow finishes, but the server will no longer be running).
In that case you can find the tunnel address on [ngrok's status page](https://dashboard.ngrok.com/status/tunnels).

# Usage

See [action.yml](action.yml) for a description of the options. A sample workflow showing how to run this action if a step fails can be found [here](.github/workflows/sample.yml).

```yaml
steps:
- uses: mdelillo/ssh-server-action@v1
  with:
    ngrok-authtoken: "<your-ngrok-authtoken>"
    ssh-public-key: "ssh-rsa AAAAB3NzaC1yc2E..."
```
