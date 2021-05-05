# Hosting Migration 2021

## Migration Tracking

To help track the progress of this migration, we are using the <a href="https://docs.google.com/spreadsheets/d/1duk6oSMVem-U9xJtb4PUWXWMlXjUDCvqOOCsyT7j-ZU/edit#gid=2028465986" target="_blank">Company 119 Server Migration 2021</a> spreadsheet.

## Site Testing

After sites are initially moved to their new Chimera VPS, testing must be done to ensure the sites are functioning and appearing as expected.

In order to test the sites, you will need to temporarily set the DNS for a site using your local `hosts` file. To do that, follow these steps:

1. [Open](#how-to-open-the-hosts-file) & [edit](#how-to-format-the-hosts-file) your computer's `hosts` file
1. [Confirm](#how-to-test-the-hosts-file-changes) the `hosts` file changes are in place and working
1. Test the website's functionality and appearance
1. Once tested, mark the 'Testing Results' column in the <a href="https://docs.google.com/spreadsheets/d/1duk6oSMVem-U9xJtb4PUWXWMlXjUDCvqOOCsyT7j-ZU/edit#gid=2028465986" target="_blank">Migration Tracking spreadsheet</a> with the proper response
1. If issues are found during testing, describe the issues within the 'Testing Notes' column in the <a href="https://docs.google.com/spreadsheets/d/1duk6oSMVem-U9xJtb4PUWXWMlXjUDCvqOOCsyT7j-ZU/edit#gid=2028465986" target="_blank">Migration Tracking spreadsheet</a>
1. [Remove](#how-to-remove-the-hosts-file-changes) the `hosts` file changes

---

### How to open the `hosts` file

#### On Windows

1. Press the `Windows` key
1. Type `Notepad` in the search field
1. In the search results, right-click `Notepad` and select `Run as administrator`
1. From Notepad, open the following file: `c:\Windows\System32\Drivers\etc\hosts`
1. Make the necessary changes to the file
1. Select `File` > `Save` to save your changes
1. In the `Command Prompt`, type `ipconfig /flushdns` to clear your machine's DNS cache

#### On Mac

1. Launch Terminal
1. Type `sudo nano /etc/hosts` and press `Return`
1. Enter your admin password
1. Make the necessary changes to the file.
1. Save the file by pressing `Ctrl + O`
1. Exit with `Ctrl + X`
1. In `Terminal`, type `sudo killall -HUP mDNSResponder` followed by `Return` to clear your machine’s DNS cache

---

### How to edit the `hosts` file

1. Add a new line below any existing records
1. Type in the `IP address`
1. Press the `Tab` key
1. Enter the `domain name`
1. Save your changes

---

### How to test the `hosts` file changes

#### On Windows

1. Press the `Windows` key
1. Type `cmd` in the search field and press `Enter`
1. In the `Command Prompt`, type `ipconfig domain.com` (replace `domain.com` with the domain you are testing)
1. Press `Enter`
1. In the results, look for the line labeled `IPv4 Address` and make sure it matches the IP address set in your `hosts` file
1. If the IP address is not correct, verify that you edited the `hosts` file correctly

#### On Mac

1. Launch Terminal
1. Type `ping domain.com` (replace `domain.com` with the domain you are testing)
1. Press `Return`
1. In the results, make sure the returned IP address matches the IP address set in your `hosts` file
1. If the IP address is not correct, verify that you edited the `hosts` file correctly

---

### How to remove the `hosts` file changes

1. [Open your `hosts` file](#how-to-open-the-hosts-file)
1. Either remove the added lines or type `#` in front of the lines you want to ignore
1. Save your changes
