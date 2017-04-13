# Howto Windows

## Stop windows 7 from auto-restarting

Just follow this [guide](https://www.groovypost.com/howto/microsoft/stop-windows-7-from-auto-restarting-after-update/).

Here a quick guide based on it:

1. Open `regedit.exe`
2. Go in `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows`
3. Add a **key** named `WindowsUpdate` and go there
4. Add a **key** named `AU` and go there
5. Add a **DWORD (32-bit) Value** named `NoAutoRebootWithLoggedOnUsers`
6. Select the **Modify...** command on it and input a **Value data** of `1`

This work for Windows 7, and should also work for some other versions.

## How to prevent windows 10 from auto-downloading updates

You can follow this [guide](https://www.howtogeek.com/262477/how-to-set-an-ethernet-connection-as-metered-in-windows-8-and-10/) for ethernet connection.

This other [guide](https://www.howtogeek.com/224471/how-to-prevent-windows-10-from-automatically-downloading-updates/) tell you how to do so for all other kind of connection.

As for the quick guide for an ethernet connection:

1. Open `regedit.exe`
2. Go in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\NetworkList\DefaultMediaCost`
3. [Take ownership](https://www.howtogeek.com/262464/how-to-gain-full-permissions-to-edit-protected-registry-keys/) of the key `DefaultMediaCost`
4. Select the **Modify...** command on the key named `Ethernet` and set the **Value data** to `2`

## Open a console

### Easy mode

In the search bar from the **"Start"** menu, search for the keyword `cmd.exe` and open the program.

### Advanced mode

On a repository displayed in the explorer, do **SHIFT + RIGHT MOUSE CLIC** and then select **"Open a commands window here"**.

### Nightmare mode

If you don't have access to the explorer, there is a last method available to you to be able to open a console:

1. do **CTRL + ALT + SUPPR**
2. open the **"Tasks manager"**
3. On the menu, select `File > New task (Execute...)`
4. Enter `cmd` in the prompt and then click on **"OK"**

## Refresh and flush the DNS

In a console, do:

```cmd
ipconfig /renew
ipconfig /flushdns
```

## Restart explorer once it is down

In a console:

```cmd
explorer.exe
```

## Start, Stop and Restart a windows service

Windows give you a tool to manage services, which is named: **services**.

This tool display all available windows services, and allow you to: start, stop or restart them.
