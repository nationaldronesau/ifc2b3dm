# Instructions

#### 1. BimServer Setup

In order to implement and make use of this script, you need to set up BimServer. Download the correct server version from the below link.

https://github.com/opensourceBIM/BIMserver/releases/tag/v1.5.162

Running the jar file will open the server GUI where you can start the setup. Click "start" to run the bimserver setup. After this is completed, click "launch web browser" to open the web GUI. Complete the setup by filling out your details. Make sure to install all suggested plugins on the plugin installation page, these are necessary for the operation of this program.

#### 2. Upload IFC model to BimServer

In the web GUI, open the BimViews plugin. From the project tab, you can create a new project. Then you can open the project,and click on the small dropdown arrow next to the project name and click "Checkin" to upload your model.

#### 3. Configure Converter folder structure

After the BimServer setup, a converter folder needs to be created and obj2gltf needs to be cloned and included in the folder and IfcConvert.exe needs to be downloaded and included in the folder. This folder can be located anywhere on the computer, the path to it needs to be supplied to the script.

Create a folder within the converter folder with the same name as the BimServer project

Running the script will generate all folders within the model folder. The `ModelName`.json file needs to be downloaded from the BimServer in the next step

--Converter:

--------------obj2gltf

--------------IfcConvert.exe

--------------`ModelName`:

--------------------------IFCs

--------------------------SJSONs

--------------------------OBJs

--------------------------GLTFs

--------------------------`ModelName`.json

#### 4. Download and format IFC model JSON

In the BimViews web GUI, select the revisions tab and click "Download" and select the "Json" serializer. Copy the output to a text file and save it as `ModelName`.json in the `ModelName` folder. This file has unnecessary keys which need to be deleted. All `_u`, `_r` and `_s` keys and their respective values need to be deleted. After this is completed, save the file.

#### 5. Build the project

Download and install Eclipse to open and build this project. Using Eclipse, open this project. Edit the Main.java file and configure the variables that are located at the start of the file with your details, such as the BimServer address, username and password, etc. After this is completed, click File -> Export -> Java -> Runnable JAR file to build the project as a JAR file. Export this JAR file to the root of the IFC2GLTF folder.

That's the end of the setup for this stage. The JAR file that you've exported is used in the bash script to compile an IFC straight into a B3DM. This will need to be recompiled every time the IFC model name changes, since this is one of the variables in the java file. 
