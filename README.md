# Welcome hackclub retrospect refugees!
If you're not from hackclub and you're trying to build a j2me application in 2025, I question your motives but heres the most up to guide on the internet for it. 

## Install a 32 bit JDK
Download and extract [java-8-openjdk-32.tar.gz](https://files.mercurywork.shop/rafflesia/java-8-openjdk-32.tar.gz) and move its contents into `/usr/lib/jvm/java-8-openjdk-32`, e.g. with `sudo tar -xzf java-8-openjdk-32.tar.gz --directory=/usr/lib/jvm/`

Set it as your default jre with `sudo archlinux-java set java-8-openjdk-32`

# Enable Multilib
* I don't know exactly what you need installed but you need `lib32-libxtst` for sure

# Download sun-wtk from the AUR
* Self explanatory

# Download these plugins 
1. Download [oracle-jmesdk-3-4-rr-nb-plugins.zip](https://files.mercurywork.shop/rafflesia/oracle-jmesdk-3-4-rr-nb-plugins.zip)
2. Extract this file
3. You'll use this later

## Installing Mobility
Install Netbeans 8.2. This requires an oracle account so I posted it here.
1. Run the installer I linked [here](https://files.mercurywork.shop/rafflesia/netbeans-8.2-linux.sh)
2. When asked for jvm, use the java-8-openjdk-32 you installed
3. Finish installation
4. Open tools > plugins
5. Install the **Mobility** Plugin

## Installing the other plugins you need (Painful)
1. Go back to Tools > Plugins
2. Open the Downloaded tab
3. Click Add Plugins
4. Select all the plugins from the zip file you used earlier. Some of them will give you an error. unselect these and try again until you have all the plugins you *can* install

## Setting the platform
1. Go back to the main page and select Tools > Java Platforms
2. Click Add Platform
3. Select Platform Type: Java ME CLDC Emulators
4. Select `/opt/sun-wtk`
5. Proceed and finish

### Note:
If this fails, try setting your `WTK_JRE_PATH="/usr/lib/jvm/java-8-openjdk-32/"` environment variable, and then launching netbeans. If this works, you can add it to `/etc/environment`

## Creating your first project
* The examples plugin didn't install for you most likely, but I have extracted the Samples and put them in `Samples/` of this repo
* You can also just create a new project (Box icon), select Java ME, and have your fun that way

## Notes:
* The run button is broken, install microemulator and build every time you need to run, running `microemulator (yourthing).jad` in the commandline
* If you have images to submit to this guide, open a github issue and I'll be happy to add them
* I didn't test this guide exactly in this order, but its still the correct steps to my knowledge
