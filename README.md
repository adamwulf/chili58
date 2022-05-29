# Chili58 Keyboard

Based on the [Lily58](https://github.com/kata0510/Lily58), this design uses choc spacing for all the keys. The PCB, baseplates, etc can be generated using [Ergogen](https://ergogen.cache.works/).

This design is a work in progress, and is by no means complete or even functional.

## Steps To Build

1. Paste yaml into https://ergogen.cache.works/ and generate PCB.
2. Open pcb file in KiCad, and route all connections
   - Inspect Menu -> Design Rules Checker -> Run DRC -> Confirm no errors
3. generate gerber files
4. upload to print PCB somewhere (?)
5. upload edge cuts to cut acrylic case somewhere (?)

## Steps To Build (alt)

1. cd into ergogen fork
2. run.sh
3. generated files are in ~/Downloads/pcbs/
4. Open pcb file in KiCad, and route all connections
   - Inspect Menu -> Design Rules Checker -> Run DRC -> Confirm no errors
5. upload to print PCB somewhere (?)
6. upload edge cuts to cut acrylic case somewhere (?)


## Autoroute

### From Kicad:

1. "Export Specctra DSN..." and save `.dsn` file

### Install Freerouting

Download latest release of Freerouting from [https://github.com/freerouting/freerouting/releases](https://github.com/freerouting/freerouting/releases).

Install Java: [stack overflow link](https://stackoverflow.com/questions/52524112/how-do-i-install-java-on-mac-osx-allowing-version-switching/52524114#52524114).

```
brew update
brew install java
```

`java` is now available from `/usr/local/opt/openjdk/bin/java`


### Launch Freerouting

```
/usr/local/opt/openjdk/bin/java -jar /path/to/freerouting.jar
```

1. Click "Open Your Own Design" and choose the `.dsn` file exported above
2. Click "Autorouter"
3. Once complete, File -> Export Secctra Session File

### From Kicad:

1. File -> Import -> Secctra Session...
2. Choose `.ses` file exported above
3. routing appears in Kicad!
