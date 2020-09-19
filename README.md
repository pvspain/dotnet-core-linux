# Microsoft .Net Core on Linux

- [Microsoft .Net Core on Linux](#microsoft-net-core-on-linux)
  - [References](#references)
  - [Installation](#installation)
  - [HelloWorld - console](#helloworld---console)

## References

- [Install .NET Core SDK on Ubuntu][2]
- [Kicking the tyres][1]

## Installation

- Ubuntu 20.04
  
```bash
# Install snapd if required...
sudo apt update && \
sudo apt install --yes snapd

# Install dotnet-sdk snap...
sudo apt update && \
sudo snap install dotnet-sdk --classic

# Add 'dotnet' executable to PATH...
cat >> ~/.bashrc <<"EOF"

# Add .NET Core to PATH
export PATH=$PATH:/snap/dotnet-sdk/current/
# Don't emit usage data
DOTNET_CLI_TELEMETRY_OPTOUT=1

EOF

# Re-source ~/.bashrc...
. ~/.bashrc

```

## HelloWorld - console

```bash
# Create new directory...
PROJECT="hello-world"
mkdir --parents $PROJECT && pushd $PROJECT

## Initialise console project..
# Creates a project based on the name of the current directory, $PROJECT
# --force will clobber any existing:
# ${PROJECT}.csproj
# Program.cs
dotnet new console --force

## Boiler-plate build-run cycle commands...
# Ensure dependencies and build
dotnet restore && \
dotnet build
# Run
dotnet run

popd

```


[1]: https://www.dotnetforall.com/creating-my-first-net-core-cli-project/
[2]: https://snapcraft.io/install/dotnet-sdk/ubuntu
