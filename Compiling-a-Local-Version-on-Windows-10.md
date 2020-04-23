Compiling a Local Version of the Website (Windows 10 Platform)

tl;dr Windows 10 does not play well with PATH environments. Installing Ubuntu 16.04 LTS is the _path of least resistance_ way to develop locally on Windows 10.

# Ubuntu

1\. Run as Administrator the Windows PowerShell App and run:

`$ Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`

2\. Restart your computer when prompted.

3\. Check your build: Settings > System > About. Must be Windows 10 version 16215.0 or higher.

4\. [Ubuntu 16.04 LTS](https://www.microsoft.com/store/apps/9pjn388hp8c9). See System Requirements; Your device must meet all minimum requirements to open this product. Click "Get." Redirected to Microsoft Store. Click "Get" again.

5\. Click "Launch."

6\. Once installation is complete, you will be prompted to create a new user account (and its password).

**When you elevate a process using sudo, you will need to enter your password, so make sure you choose a password you can easily remember!**

7\. Update & upgrade your distro's packages: 

`$ sudo apt update && sudo apt upgrade`

8\. Remove Windows path from WSL PATH:

`$ sudo vim /etc/wsl.conf`

a. Press `i` to insert text (you should see `-- INSERT --` at the bottom-left of the console).

b. Type:

```
[interop]
appendWindowsPath = False
```

c. Press Esc key to exit `-- INSERT --` mode.

d. Type `:x`, press Enter key to exit vim and save work.

9\. To verify your work, type: `cat /etc/wsl.conf` and you should see:

```
[interop]
appendWindowsPath = False
```

# Download & Install Lektor

10\. Required for Ubuntu:

`$ sudo apt-get install python-dev libssl-dev libffi-dev`

`$ sudo apt-get install imagemagick`

11\. Go to https://www.getlektor.com/install.sh and download .sh file on your desktop.

12\. Open up install.sh in your Editor (not sure what you use, I use Sublime Text 3)

13\. On line 39, change the line to this:

`VENV_URL = "https://pypi.org/pypi/virtualenv/16.7.9/json"`

14\. Save changes in the file. Move it to `C:\`

15\. In your Ubuntu console, cd to where the file is in your `C:\` drive by typing:

`$ cd /mnt/c`

16\. Run sh file in sudo:

`$ sudo ./install.sh`

**You will get this prompt, but everything will install correctly.**

`/usr/bin/python: can't open file './src/virtualenv.py': [Errno 2] No such file or directory`

17\. cd back to your `/home/[username]/` directory

`$ cd /home/nicolei` (the name you chose not my name)

# Clone the Repo from Torgit

18\. Download and clone whichever repo you want:

Tor Project Main: `$ git clone https://git.torproject.org/project/web/tpo.git`

Tor Browser Manual:  `$ git clone https://git.torproject.org/project/web/manual.git`

Support Portal:  `$ git clone https://git.torproject.org/project/web/support.git`

Community portal:  `$ git clone https://git.torproject.org/project/web/community.git`

# Install the Dependencies for the lektor-i18n-plugin

`$ sudo apt-get install gettext python3-babel`

I skipped the translations repo.

19\. cd into whichever repo you cloned. I cloned the manual so I typed:

`$ cd manual`

For you, it might be: `$ cd support` OR `$ cd tpo` OR `$ cd community`

# Initialize the Building Blocks Submodule

20\. cd into the `/lego` folder & init the building blocks submodule:

`$ cd /lego`

`$ git submodule update --init --recursive`

# Install the Rest of the Plugins

`$ lektor plugins reinstall`

# Troubleshoot

21\. Fix 3 errors.

i. We need to edit the `lektor_xml_to_html.py` file:

`$ cd packages/xml-to-html/`

`$ vim lektor_xml_to_html.py`

a. Press `i` for `-- INSERT --` mode.

b. Use arrow keys to move down to line and change `from urllib import request` to `from urllib3 import request`.

c. Press Esc key to exit `-- INSERT --` mode.

d. Type `:x` and press Enter key to save changes and exit.

ii. We also need to edit the `lektor_txt_to_html.py` file:

`$ cd ../txt-to-html/`

`$ vim lektor_txt_to_html.py`

a. Press `i` for `-- INSERT --` mode.

b. Use arrow keys to move down to change `from urllib import request` to `from urllib3 import request`.

c. Press Esc key to exit `-- INSERT --` mode.

d. Type `:x` and press Enter key to save changes and exit. 

iii. We need to edit the `lektor_i18n.py` file:

`$ cd ../i18n/`

`$ vim lektor_i18n.py`

a. Press `i` for `-- INSERT --` mode.

b. Use arrow keys to move underneath the line that says `import sys` and add:

```
reload(sys)
sys.setdefaultencoding('utf8')
```

c. Press Esc key to exit `-- INSERT --` mode.

d. Type `:x` and press Enter key to save changes and exit.

# Develop

22\. Finally, local server.

cd back to main repo folder:

`$ cd ../../..`

`$ lektor server`

You should be able to access your local lektor instance at http://127.0.0.1:5000/ from your computer.