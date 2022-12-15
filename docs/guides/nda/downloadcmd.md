# Downloading NDA data packages with `nda-tools`

[`nda-tools`](https://github.com/NDAR/nda-tools) is a python package and command line client developed by National Institute of Mental Health Data Archives (NDA) to allow users to programmatically validate, package, submit, and/or download data. This documentation filters out information needed only to **download data packages** using their command line utility. More information of how to create a NDA data package can be found [here](https://nda.nih.gov/training/module?trainingModuleId=training.cloud-access&slideId=slide.creating.package).

### Pre-requisites
1. Python3, pip and nda-tools package
2. NDA authentication through command line 
3. downloading NDA data package 

### Install `nda-tools`
If you don't have `python3` and `pip` installed, please find the instructions on the official [`nda-tools` documentation page](https://github.com/NDAR/nda-tools#installing-python). To install `nda-tools`, run the following command:

```bash
pip install nda-tools
```

Some additional notes if you run into issues:
> * If the nda-tools needs special permission try:
>   * pip install nda-tools --user
> * If multiple versions of python or pip exists on the operation machine, the command prompt will not recognize the nda-tools script. Try the > following command instead:
>   * python -m NDATools.clientscripts.[NDAtoolcommand]
> * If a deprecated version of the tool is already installed, it'll prompt the user to upgrade. To update, follow the prompt command.
Source: https://github.com/NDAR/nda-tools#installing-the-client

### Storing authentication credentials with Keyring

[Keyring](https://pypi.org/project/keyring/) is a Python package that leverages the operating system's credential manager to securely store and retrieve user credentials. The following commands were run from the terminal on a macOS Catalina v10.15.7:

```bash
$ keyring --help                                                                                                                                                                                                                                                                                          
usage: keyring [-h] [-p KEYRING_PATH] [-b KEYRING_BACKEND] [--list-backends] [--disable] [operation] [service] [username]

positional arguments:
  operation             get|set|del
  service
  username

optional arguments:
  -h, --help            show this help message and exit
  -p KEYRING_PATH, --keyring-path KEYRING_PATH
                        Path to the keyring backend
  -b KEYRING_BACKEND, --keyring-backend KEYRING_BACKEND
                        Name of the keyring backend
  --list-backends       List keyring backends and exit
  --disable             Disable keyring and exit
```

The following commands use a hypothetical NDA user with username `ambedkar` who is trying to download a package with ID `123456`. He would need to type in his password that'll be stored securely on Keychain. 
```bash
$ keyring set nda-tools ambedkar                                                                                                                                                                                                                                                                            
Password for 'ambedkar' in 'nda-tools': 
```

`nda-tools` now trusts that you are indeed who you say you are! So here's the last command (hopefully) to actually download your data. Here's a few lines from the stdout:

```bash
$  downloadcmd -dp 123456
Running NDATools Version 0.2.21
Enter your NIMH Data Archives username:ambedkar

No value specified for --workerThreads. Using the default option of 15
Important - You can configure the thread count setting using the --workerThreads argument to maximize your download speed.


Getting Package Information...

Package-id: 123456
Name: testing
Has associated files?: Yes
Number of files in package: 25
Total Package Size: 9.55MB

Downloading all files from package with id: 123456

...

Finished processing all download requests @ 2022-12-09 11:29:17.910494.
     Total download requests 25
     Total errors encountered: 0

 Exiting Program...

```

By default, packages are downloaded to `~/NDA/nda-tools/<package-id>`. If you'd like it in a different directory, use the `-d` or `--directory` flag to specify path/to/destination. 
