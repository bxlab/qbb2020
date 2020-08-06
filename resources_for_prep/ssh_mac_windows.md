# Instructions to access MARCC from your laptop

## For macOS and Windows 10

macOS and Windows 10 both have a built in program called `ssh` that allows the user to connect securely to a remote server (e.g. MARCC)

To open an ssh connection to MARCC in macOS or Windows 10:

1. Open your terminal/command prompt.<br /><br />On macOS, open the terminal app. If terminal is not on your toolbar, you can search **terminal** in **Finder** or open spotlight search using the shortcut `cmd`+`Space` and then searching **terminal**.<br /><br />If you are on Windows 10, open the command prompt app. Click on the **magnifying glass** icon at the bottom of the screen to open a search, and search **command prompt**. Alternatively, use the shortcut `windows key`+`R` to open the **run** window, type **cmd** and then click **OK**.

2. Once your terminal/command prompt app is open, type the command `ssh <JHEDID>@jhu.edu@login.marcc.jhu.edu`.<br /><br />Your JHEDID is the bit before *@jh.edu* or *jhu.edu* in your JHU email. For example, if my JHU email was johndoe@jh.edu, I would log in with the command `ssh johndoe@jhu.edu@login.marcc.jhu.edu`.

Congratulations! You're now on MARCC.

## For earlier versions of Windows (7, 8)

Depending on your version of Windows, you may or may not have `ssh` natively installed on your computer. You can easily check by opening **command prompt** and running `ssh` using the instructions above. If you get an error message along the lines of `'ssh' is not recognized as an internal or external command` then it is likely not installed. To get around this, we're going to install a program called **PuTTY**.<br /><br />

1. The first thing you're going to need to do is determine whether you're running a 32-bit or 64-bit version of Windows. You can find this information in the **System** panel.<br /><br />In Windows 8, the **System** panel can be opened by first opening the **Charms bar** using the keyboard shortcut `windows key` + `C`, then clicking on **Settings** and then clicking on **PC info**. You'll want to look at the *System type* to determine whether you're running a 32-bit or 64-bit operating system.<br /><br />![Charms Bar](https://raw.githubusercontent.com/bxlab/qbb2020/master/resources_for_prep/charms_bar.png)			![win8 settings](https://raw.githubusercontent.com/bxlab/qbb2020/master/resources_for_prep/windows8_settings.png)<br /><br />![Win8 System](https://raw.githubusercontent.com/bxlab/qbb2020/master/resources_for_prep/windows8_system.png)<br /><br />In Windows 7, the **System** panel can be opened by first clicking on the **Start** button at the bottom-right of the screen, then **right-clicking on Computer** in the righthand panel of the Start Menu, and finally clicking **Properties**. You'll want to look at the *System type* to determine whether you're running a 32-bit or 64-bit operating system.

2. Once you've determined which type of operating system you're running, visit [this link](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html). Select the `.msi` file from the **Package files** section that matches your operating system type, and download it.

3. Find the `.msi` file in your **Downloads** and open it to begin the Setup Wizard. Follow the instructions to install PuTTY.

4. Open the PuTTY Application. Depending on your version of Windows, you may see something slightly different, but the GUI should look something like this:<br/><br/>![PuTTY GUI](https://raw.githubusercontent.com/bxlab/qbb2020/master/resources_for_prep/PuTTY_gui.png)

5. In the **Host Name (or IP address)** field, enter `<JHEDID>@jhu.login.marcc.jhu.edu`.Your JHEDID is the bit before *@jh.edu* or *jhu.edu* in your JHU email. For example, if my JHU email was johndoe@jh.edu, I would enter `ssh johndoe@jhu.edu@login.marcc.jhu.edu`. In the **Port** field, enter `22`.<br /><br />![PuTTY GUI2](https://raw.githubusercontent.com/bxlab/qbb2020/master/resources_for_prep/PuTTY_gui_hostname.png)

6. Make sure that **SSH** is selected under **Connection type**. Click **Open** to start your SSH session.<br /><br />![PuTTY GUI3](https://raw.githubusercontent.com/bxlab/qbb2020/master/resources_for_prep/PuTTY_gui_open.png)