# Elvinos - Homebrew App Replacer Python Script (Updated from Micheal Herb)

- Updated for the current homebrew configuration
- Added check for whether the application is already managed by HomeBrew
- Added `microsoft-office` install check
- Switched order of send2trash of application to make sure brew could correctly copy.
- Updated requirements

*WARNING:*  Make sure that you understand that the application will delete the original app from the Applications folder before getting the files from home-brew. This should in theory be safe but has not been fully tested

---

# Homebrew-App-Replace

Use Homebrew cask replacer to replace installed apps with their Homebrew equivalents.

## Usage

Go to the directory containing this file in your command line.

```bash

pip install -r requirements.txt
python brew_app_replace.py

```

- Update the `ignore.txt` file to add any other applications that you do not wish to port to HomeBrew.


**Parameters**

```bash

python brew_app_replace.py -f # Include Mac Appstore Apps
python brew_app_replace.py -y # Replace all Apps automatically (yes to all)

```

## How it Works

* Skip {application} from Appstore [-f turnoff]
* check http://raw.github.com/caskroom/homebrew-cask/master/Casks/{application} is exist
* Print application info and check if you want to replace it with brew cask [-y yes to all]
* Send old {application_path} to trash (may fail)
* Install application using 'brew cask install {application}'

