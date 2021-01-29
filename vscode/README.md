## VSCODE Setup

### Connected Account &nbsp;🔗

Connecting an account to vscode allows you to activate the editor's `Settings Sync` feature which provides a great syncing experience of both settings and extensions.

If you're good with your current synced settings then you're all done. Otherwise you can follow the steps below to sync the provided settings to your account.

### No Account 🕵️‍♀️

If you're a new vscode user, or simply prefer to avoid linking an account for whatever reason, follow the steps below:

- Both `settings.json` and `keybindings.json` can be copied to their proper place via the vscode gui.
  
  > The location of both files should be `~/Library/Application Support/Code/User`
  
- Install all the extensions in the `extensions.txt` file using the following command:

  ```sh
  cat extensions.txt | xargs -L 1 code --install-extension
  ```
  
  > The `code --install-extension` command accepts a single extension id only so we have to run it for each extension. You can generate an extensions file from your currently installed extensions by running `code --list-extensions > extensions.txt`.
  
### Alternative Extension Syncing Methods

#### Extension Pack

An Extension Pack is a bundle of multiple extensions that can be installed at once. Creating an Extension Pack is very easy - refer to the offical docs if you're interested.

The generated `VSIX` package can be shared offline or publised to the vscode marketplace. Pulishing is also easy and is a actually a really neat option both for personal storage and sharing your pack. 

Packing extensions combined with the ability to enable/disable them together provides great control over your editor's focus and resource consumption all the way down to the workspace (project) level.

#### Recommended Extensions

You can create a recommended extensions list per workspace via the command palette or by adding an extension through the extension manager.

This will generate an `extensions.json` file under your project's `.vscode` settings with a `recommendations` key pointing to an array of extension ids.

You can source control your `extensions.json` to share with project contributors, but you can also save and use that file yourself to help with the initial installation of your extensions. 
Once loaded for the first time, vscode will prompt you to install the recommended list. If you dismissed that notification you can go to the extension manager and choose to install all extensions under the recommended filter.
