# hacks

## 1. Multiple github accounts on Mac with osxkeychain

    git config --global credential.github.com.helper osxkeychain
    git config --global credential.github.com.useHttpPath true
    
    
## 2. Error Upgrading Ubuntu 20.04 + Python 3.10

   Error:
   
    The following packages have unmet dependencies:
     libpython3.10 : Depends: libpython3.10-stdlib (= 3.10.4-1+focal2) but 3.10.4-1+focal1 is installed
     libpython3.10-dev : Depends: libpython3.10-stdlib (= 3.10.4-1+focal2) but 3.10.4-1+focal1 is installed
     python3.10 : Depends: libpython3.10-stdlib (= 3.10.4-1+focal2) but 3.10.4-1+focal1 is installed
     python3.10-minimal : Depends: libpython3.10-minimal (= 3.10.4-1+focal2) but 3.10.4-1+focal1 is installed
     E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution)
     
   Solution:
   
    sudo dpkg --force-all --remove libpython3.10-stdlib libpython3.10-minimal
That forces the two colliding packages to uninstall, even though others depend on them.

    sudo apt-get install libpython3.10-stdlib libpython3.10-minimal

   
