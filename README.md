# Kali Install

1) Change the Kali password
```
passwd
```
2) then add a root account password
```
sudo -i 
```
3) add the root password

Log out and log back in as root

4) Kali Infrastructure Script to download and install

```
curl -sS https://raw.githubusercontent.com/a7t0fwa7/Attack_Infra_Setup/main/Kali_Setup/C2andToolsSetupKali.sh | sudo bash -

```
5) Allow SSH as root

- Open sshd_config file
`nano /etc/ssh/sshd_config`

- Find the Authentication section and modify the line 
`PermitRootLogin yes`

- Save an exit

- Restart ssh server:
`systemctl restart sshd` or `service sshd restart`


## Alternative Kali Install

Download PimpmyKali from `https://github.com/Dewalt-arch/pimpmykali.git` follow instructions

To Launch: `sudo bash pimpmykali.sh`

# Windows Install

On the Windows VM, open a PowerShell prompt as Administrator and run:
1) ```Set-ExecutionPolicy Unrestricted```

2) ```. { Invoke-WebRequest -useb https://boxstarter.org/bootstrapper.ps1 } | iex; Get-Boxstarter -Force```
3) If step 2 doesn't work try this:
```Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://boxstarter.org/bootstrapper.ps1')); Get-Boxstarter -Force```

Once the installation has completed, a Boxstarter Shell icon will appear on your desktop.  

## Launch the **Boxstarter Shell** and enter the following commands:

1) ``` $Cred = Get-Credential $env:USERNAME ```

2) ``` Install-BoxstarterPackage -PackageName https://raw.githubusercontent.com/a7t0fwa7/Attack_Infra_Setup/main/windows.choco```


## Launch Powershell config script
3) ``` iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/a7t0fwa7/Attack_Infra_Setup/main/windows.ps1'));-Force```

4) If all the above fails then download files as ZIP and install locally



Once the Boxstarter packages have been installed, install the three Visual Studio applications in your Downloads folder.  When installing Visual Studio Community edition, select the .NET and C++ Desktop Development Environments from the main Workloads menu, then find and select the Windows XP v141 tools from the Individual components menu.

Then perform one final manual reboot.
