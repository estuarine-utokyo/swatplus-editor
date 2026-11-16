# README #

> [!IMPORTANT]
> **This is not the official SWAT+ Editor repository.** It is a fork maintained by
> [estuarine-utokyo](https://github.com/estuarine-utokyo) for coastal and watershed modelling in Ghana
> (Volta and Densu basins). It may contain local modifications that are not in the official code.
> Use the official repository, [swat-model/swatplus-editor](https://github.com/swat-model/swatplus-editor),
> for the released SWAT+ Editor, and report issues with the official code there, not here.
>
> Branches of this fork:
> - `main` -- the maintainer's development branch (default; push and pull here);
> - `upstream-main` -- an unmodified copy of the official `swat-model/swatplus-editor` branch `main`,
>   updated by fast-forward only and merged into `main` from time to time.
>
> To follow the official repository in a clone:
> `git remote add upstream https://github.com/swat-model/swatplus-editor.git`, then `git fetch upstream`;
> update `upstream-main` with `git push origin upstream/main:upstream-main` and merge it into `main`.
> Do not press GitHub's "Sync fork" button on `main`: it compares `main` with the official branch and
> offers to discard the local commits.

Desktop interface to SWAT+ allowing the user to import a project from GIS, modify SWAT+ input, write the text files, and run the model.

Read the documentation at [swat-model.github.io/swatplus-editor-documentation/](https://swat-model.github.io/swatplus-editor-documentation/) and [join the user group](https://groups.google.com/g/swatplus-editor) to be notified of new releases.

## Installing and running the source code ##

### Back-end development stack ###

1. Install [Python 3](https://www.python.org/) (version 3.10 and up)
2. Set up virtual environment
    * Install `pipenv` following the [instructions here](https://pipenv.pypa.io/en/latest/installation.html).
    * From command prompt, go to source code `/src/api` directory
	* Create a directory `.venv` if it does not already exist
	* Run `pipenv install`
	* Run `pipenv --py` and confirm the python location matches the `pythonPath` in `/src/main/static/appsettings.json`

### Front-end development stack ###

1. Install [Node.js](https://nodejs.org/en/) (version 18 LTS)
2. Install required Node.js packages
    * From command prompt, go to the root directory of the source code
    * Run `npm install`

### Running the source code ###

1. From command prompt, go to the root directory of the source code
2. In Linux/Mac, you may need to set permissions on the electron package distribution:
   * `cd node_modules/electron/dist`
   * `sudo chown root chrome-sandbox`
   * `sudo chmod 4755 chrome-sandbox`
3. Run `npm run dev`

### Development tools ###

1. [Visual Studio Code](https://code.visualstudio.com/)

### Build the source code ###

1. From `/src/api` run the following depending on your OS:
	* Windows: `python-build-windows`
	* Linux: `sh python-build-linux.sh`
	* MacOS: `sh python-build-mac.sh`
2. From the root of the source code directory run the following depending on your OS:
	* Windows: `npm run build:win`
		* NOTE: If you encounter errors during this step, be sure to enable [Developer Mode](https://learn.microsoft.com/en-us/windows/apps/get-started/enable-your-device-for-development) on your PC
	* Linux: `npm run build:linux`
	* MacOS: `npm run build:mac`
3. Program will be in `/release/dist`
