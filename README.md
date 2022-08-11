# Power BI 3D
Custom Visual for **Power BI** to visualize 3D models and connect them to your data. It uses the library three.js and its fantastic [3DM loader](https://threejs.org/docs/#examples/en/loaders/3DMLoader) to visualize 3D models in power BI. It currently only supports Rhino3d models, but the visual can be easily expanded to support other file formats.
<br />

## Acknowledgement
This custom visual was developed by Diego Apellániz.<br/> <br/> 
Thanks to [McNeel](https://discourse.mcneel.com/t/3dmloader-for-three-js/107702) for the wonderful 3DM loader for three.js.

## How to use
### Add custom visual to Power BI
1) Download last [release](https://github.com/diego-apellaniz/PowerBI3D/releases) of this repository.
2) Download and install [Power BI Desktop](https://www.microsoft.com/store/productId/9NTXR16HNW1T).
3) Open Power BI, create a new file and go to *Files -> Import -> Power BI Visual from File* and select *3DVisor.pbiviz* from the ***downloaded files***.
4) Create a 3D Visor in Power BI by select the imported visual from the visualizations panel on the right side. It won't display anything though until we connect it to our data and upload the 3D model. <br />
### Add data to your Power BI dashboard
1) Prepare a Excel table with the following format. One column must contain the GUIDs of the objects of your 3D model you want to import in Power BI. Additional columns may include different categories for the GUIDs and different values. It's important that all cells of the table are filed:

   If you are using Rhino3D as the source of your 3D model, you can easily use Grasshopper to create your Excel table:

2) Upload Excel table to Power BI
3) Connect GUIDs with the 3D Visor. The input form to introduce the URL of your 3D model should appear now in the 3D Visor.

### Import 3D model in Power BI
1) Post-process your 3D modell. Delete the elements you don't want to import in Power BI and you didn't include in the GUIDs column of your table. In case you're using a Rhino model, it's strongly recommended to convert all geometry elements to **meshes**, since other geometry types may not be implemented in the 3DM loader yet.
2) Get your 3D model online. Only 3D models uploaded to a https domain with CORS enabled can be imported in Power BI. In case you don't have access to such a domain, you can use one of the following resources:</br>

#### Localhost
Make your 3D model accessible through yor **Localhost** IP adress. In the downloaded files from the last [release](https://github.com/diego-apellaniz/PowerBI3D/releases), you will find a Python script to make files accessible through a localhost IP adress. In order to use it, we need to create a SSL Certificate For Localhost first</br>.
1) Install [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)
2) Create certificate file. You can watch this [video](https://www.youtube.com/watch?v=jSkQ27sTto0) or follow these steps:
a) Open the command prompt by using **Windows Key + R** and then typin **cmd**.
b) On the command promt type **openssl** to check that it's installed. Then use **Ctrl + C** to exit openssl.
c) On the command prompt type **cd PATH** where **PATH** is the directory where you downloaded the python script and in which the file **config.txt** should also be.
d) On the command prompt type **openssl req -x509 -out localhost.crt -keyout localhost.key -newkey rsa:2048 -days 1024 -nodes -sha256 -subj "/C=US/O=Dev-Certificate/CN=my_name" -extensions EXT -config config.txt**. A certificate key should've been created.
3) Install [Python](https://www.python.org/downloads/) in your computer.</br>

### OneDrive.
<br />

## Connect 3D model to your data


## Enable support for other file formats

