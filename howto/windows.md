# Howto Windows

## Stop windows from auto-restarting

Just follow this [guide](https://www.groovypost.com/howto/microsoft/stop-windows-7-from-auto-restarting-after-update/).

Here a quick guide based on it:

1. Open `regedit.exe`
2. Go in `HKEY_LOCAL_MACHINE > SOFTWARE > Policies> Microsoft > Windows`.
3. Add a **key** named `WindowsUpdate` and go there.
4. Add a **key** named `AU` and go there
5. Add a **DWORD (32-bit) Value** named `NoAutoRebootWithLoggedOnUsers`
6. Select the **Modify...** command on it and input a **Value data** of `1`

This work for Windows 7, and should also work for some other versions.

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
