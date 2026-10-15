For specifications in this folder, we provide a sample project in CODESYS which contains the the synthesized controller. 
Then the user can execute the CODESYS project to observe the behavior of the synthesized controller. The I/O is implemented 
using industrial communication protocol ModbusTCP, currently with configuration that master (PLC) and slave (I/O) are all localhost.

We assume that the reader has basic knowledge in installing and running CODESYS Projects version 3.5. 

-------------------

Step 1: Open the project. The CODESYS project is created under version 3.5.6, with English IDE. 

[IMPORTANT] For newer version of CODESYS (e.g., 3.5.7 Patch v2), there can be compile errors simply due to version incompatibility in 
libraries. Simple solution is to select "Do not update" (see VersioningProblem_CODESYS.jpg in this folder). Or alternatively, remove 
libraries (from Library manager) and then use "add library" > "advanced" to select all libraries {IoStandard, 3SLicense, Standard, 
IoDrvModbusTCP} again, to do re-compilation. 


Step 2: Execute the following for triggering a Modbus-TCP slave listening to the Soft PLC

java -jar Simulator_ModbusIO/ModbusSlave.jar localhost 502 

Step 3: On the menu bar, select "Online -> Login", then "Debug -> Start"