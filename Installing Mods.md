# Installing Mods:

Installing mods is really simple, all you have to do is put the `.jar` file in the `mods` folder created at the end of [Installing fabric](https://github.com/xX-poggers-Xx/minecraft-stuff/blob/main/Installing%20Fabric.md). 

It is generally preferred to install mods straight from GitHub (in the releases page on the right hand side) or from Modrinth instead of CurseForge as the releases available there will probably be more up to date (especially for GitHub). For the latest version (sometimes unstable) use GitHub actions or compile the mod yourself.

## Modrinth:

- Click on the `versions` tab
- Look for the version for the minecraft version you are using
- Click the <svg data-v-48927166="" data-v-bca524f6="" width="20" height="20" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" class=""><path data-v-48927166="" data-v-bca524f6="" d="M4 16L4 17C4 18.6569 5.34315 20 7 20L17 20C18.6569 20 20 18.6569 20 17L20 16M16 12L12 16M12 16L8 12M12 16L12 4" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"></path></svg> icon

## CurseForge:

- Click on the `files` tab
- Look for the version for the minecraft version you are using
- Click the `Download` button

## GitHub:

### Releases:

- Click on the `Releases` tab on the right
- Check the titles for the correct version for the minecraft version you are using
- Click on `Assets` to expand it
- Click on the `.jar` file
- If there are several `.jar` files chooses the one without `sources` or `dev` in the name

### Actions:

- **To download from actions you will need a [GitHub account](https://github.com/join)**
- **Not all projects have GitHub actions set up so there might not be anything there**
- Click on the `actions` tab at the top
- Click on the top item
- At the bottom there should be a box titled `Artifacts`
- Click on `build-artifacts`
- It will download a `.zip` file which you will have to unzip
- It should contain a `.jar` file
- If there are several `.jar` files chooses the one without `sources` or `dev` in the name

## Compiling from Source

### Mac:

#### Requirements:

To compile mods from source you will need Git and a Java 8 JDK.

- Open a terminal window (cmd + space to open finder then type in terminal)
- Now we need to install [Homebrew](https://brew.sh/)
- Run `brew --version` to check if Homebrew is installed, if you get an output with a first line something like `Homebrew 3.1.5` it is installed
- If it isn't installed run the following command to install it

``` bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- Next we need to install [Git](https://git-scm.com/download/mac)
- Run `git --version` to check if Git is installed, if it is installed you should get an output something like `git version 2.31.1`
- If it isn't installed run the following command to install it

``` bash
brew install git
```

- If this gives you an error check the Homebrew common issues page [here](https://docs.brew.sh/Common-Issues)
- Next we need to install a Java 8 JDK
- Run `java -version` to check if java is installed, in the first line there should be some numbers in speech marks, if the first one is and 8 then you have a Java 8 installation (e.g `"8.0.0"`)
- If it isn't installed you can either install Java from [here](https://adoptopenjdk.net/?variant=openjdk8&jvmVariant=hotspot) (the link selects the version you need) or via Homebrew by running `brew cask install adoptopenjdk8`

#### Compiling mods:

- One the GitHub page of the mod you want to compile click on the green `code` button
- Next check you on the `HTTPS` tap and copy the URL
- Open a terminal window (cmd + space to open finder then type in terminal)
- Run the following command to switch to your desktop

``` bash
cd Desktop
```

- Next type `git clone` with the URL you copied after it (you can also add `--depth=1` after to URL so it only downloads the most recent commits), press enter to run the command
- Once it has cloned look at the first line which should say `Cloning into 'the mod name'...`
- Run `cd {the mod name}` (without the curly brackets) to switch to the folder it just cloned into
- Now run `./gradlew build --no-daemon`, this will download gradle and start compiling the mod, `--no-daemon` isn't necessary for this to work but prevents the daemon from sticking around and take up memory once the mod has been built
	- If you get an error which says `permission denied`, try running `chmod +x ./gradlew` and then the previous command again
- **Check the mods GitHub page for special instructions**, e.g. [LambDynamicLights](https://github.com/LambdAurora/LambDynamicLights) asks you to run `./gradlew shadowRemapJar`, if the mod asks you to run a gradle task simply replace `build` with the task it asks you to run (`--no-daemon` can always be added to the end)
- Once the mod has compiled the `.jar` will be in `builds/libs/` in the mods folder (the one it cloned into), you want the one without `sources` or `dev` in the name

##### Example:

To install [LambDynamicLights](https://github.com/LambdAurora/LambDynamicLights) I would run these commands:

``` bash
cd Desktop
git clone https://github.com/LambdAurora/LambDynamicLights.git --depth=1
cd LambDynamicLights
chmod +x ./gradlew
./gradlew shadowRemapJar --no-daemon
```
