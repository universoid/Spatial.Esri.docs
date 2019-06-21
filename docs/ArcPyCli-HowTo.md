# ArcPyCli - DotNet Tool - HowTo

ArcPyCli is a little commandline tool to call a python script / module / command in the ArcGIS Python environment.

## Installation
Install the tool as a global dotnet tool with the following command.
```
dotnet tool install -g Universoid.Spatial.Esri.ArcPyCli.Tool
```

## List Command

The Command prints all available ArcGIS enabled Python instances.

Options  
-e, --environment -- Switch between the Python environments, if available. (Python 2.7 only 'current' environment available)  
-r, --runtime -- Switch between 'ArcMap' and 'ArcGIS' runtime.  
-a, --architecture -- Switch between 'X32' and 'X64' process architecture. (Only ArcMap.)  

```
arcpy-cli list [options] [--path]
```

Sample output:  
```
Architecture: X64, Runtime: ArcGIS, Environment: arcgispro-py3, Path: C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3  
Architecture: X64, Runtime: ArcGIS, Environment: base, Path: C:\Program Files\ArcGIS\Pro\bin\Python  
Architecture: X32, Runtime: ArcMap, Environment: current, Path: C:\Python27\ArcGIS10.6  
Architecture: X64, Runtime: ArcGIS, Environment: test-1, Path: C:\Users\username\AppData\Local\ESRI\conda\envs\test-1  
Architecture: X64, Runtime: ArcGIS, Environment: current, Path: C:\Program Files\ArcGIS\Pro\bin\Python\envs\arcgispro-py3
```

## Run Command

The Command executes the Python Command with the desired ArcGIS enabled Python environment.

Options  
-e, --environment -- Switch between the Python environments, if available. (Python 2.7 only 'current' environment available)  
-r, --runtime -- Switch between 'ArcMap' and 'ArcGIS' runtime.  
-a, --architecture -- Switch between 'X32' and 'X64' process architecture. (Only ArcMap.)  
--pycmd -- Command delimiter Flag (left side ArcPyCli; rigth side Python)

```
arcpy-cli run [arcpy options] [--pycmd] [python options] python_command command_args
```

Sample:
```
arcpy-cli run -r ArcMap --pycmd -m pip --version
Prints to console:
pip 9.0.1 from C:\Python27\ArcGIS10.6\lib\site-packages (python 2.7)
```
