## What i did at first
- Followed the default installation setup which includes setting account name, setting siri and more.
- Watched some videos on YouTube for getting some idea. Videos sources:
    - https://youtu.be/Lg3-vc081m8
    - https://www.youtube.com/watch?v=JNA2TSXatuU
    - https://www.youtube.com/watch?v=xNDRWXnLKH0

## Setup
- Created a new Apple ID and signed in from the Apple Account option in system settings.

### Homebrew

The Missing Package Manager for macOS (or Linux)


```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Paste that in a macOS Terminal or Linux shell prompt.

After installing homebrew, you need to export it's path to zsh by:

```bash
export PATH="/opt/homebrew/bin:$PATH" >> ~/.zshrc
```

Now you are ready to install most of the packages that runs on linux.

To install any package:

```bash
brew install <pkg>
```

To search any package:

```bash
brew search <pkg>
```
https://github.com/harshdeepsinghin/dotfiles/tree/main/macOS_Ventura
