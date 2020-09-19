# Microsoft .Net Core on Linux

## References

- [Install .NET Core SDK on Ubuntu]

## Installation

- Ubuntu 20.04
  
```bash
# Install snapd if required...
sudo apt update
sudo apt install --yes snapd
# Install dotnet-sdk snap...
sudo apt update
sudo snap install dotnet-sdk --classic
# Add to PATH...
cat >> ~/.bashrc <<"EOF"

# Add .NET Core to PATH
export PATH=$PATH:/snap/dotnet-sdk/current/
# Don't emit usage data
DOTNET_CLI_TELEMETRY_OPTOUT=1

EOF
# Re-source .bashrc...
. ~/.bashrc

```

[1]: https://www.dotnetforall.com/creating-my-first-net-core-cli-project/
[2]: https://snapcraft.io/install/dotnet-sdk/ubuntu
