# Notes

## External Secrets

Before deploying a single secret must be created manually. Some wonky stuff usually happens with newlines,
so a workaround is advised.

1. In Bitwarden Secrets Manager, go to Machine Accounts, your machine account, then Access tokens.
2. Create a new token if needed, and copy the result to clipboard.
3. `read -s bw_token` and paste the token, press enter.
4. `k create ns external-secrets` if the namespace does not already exist
5. `k create secret generic bitwarden-access-token --from-literal=token=$(cat /tmp/asd | tr -d '\n')`

