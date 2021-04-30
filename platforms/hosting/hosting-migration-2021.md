# Hosting Migration 2021

## Site Testing

After sites are initially moved to their new Chimera VPS, testing must be done to ensure the sites are functioning as expected.

In order to properly test the sites, you will need to temporarily set the DNS for a site using your local `hosts` file.

-  [How to open the `hosts` file](#how-to-open-the-hosts-file)
-  [How to format the `hosts` file](#how-to-format-the-hosts-file)
-  [How to test the `hosts` file changes](#how-to-test-the-hosts-file-changes)
-  [How to remove the `hosts` file changes](#how-to-remove-the-hosts-file-changes)

---

### How to open the `hosts` file

#### On Windows

1. Press the `Windows key`
1. Type `Notepad` in the search field
1. In the search results, right-click `Notepad` and select `Run as administrator`
1. From Notepad, open the following file: `c:\Windows\System32\Drivers\etc\hosts`
1. Make the necessary changes to the file
1. Select `File` > `Save` to save your changes

#### On Mac

1. Launch Terminal
1. Type `sudo nano /etc/hosts` and press `Return`
1. Enter your admin password
1. Make the necessary changes to the file.
1. Save the file by pressing `Ctrl + O`
1. Exit with `Ctrl + X`
1. In Terminal, type `sudo killall -HUP mDNSResponder` followed by `Return` to clear your Mac’s DNS cache

---

### How to format the `hosts` file

1. Add a new line below any existing records
1. Type in the `IP address`
1. Press the `Tab` key
1. Enter the `domain name`
1. Save your changes

---

### How to test the `hosts` file changes

#### On Windows

1. Press the `Windows key`
1. Type `cmd` in the search field and press `Enter`
1. In the `Command Prompt`, type `ipconfig domain.com` (replace `domain.com` with the domain you are testing)
1. Press `Enter`
1. In the results, look for the line labeled `IPv4 Address` and make sure it matches the IP address set in your `hosts` file

#### On Mac

1. Launch Terminal
1. Type `ping domain.com` (replace `domain.com` with the domain you are testing)
1. Press `Return`
1. In the results, make sure the returned IP address matches the IP address set in your `hosts` file
1. Terminate the process with `Ctrl + Z`

---

### How to remove the `hosts` file changes

1. [Open](#how-to-open-the-hosts-file) your `hosts` file
1. Either remove the added lines or type `#` in front of the lines you want to ignore
1. Save your changes
