DWDMModuleClntIntf Model Objects
=============================================================

*config/DWDMModuleClntIntf*
------------------------------------

- Multiple objects of this type can exist in a system.

+------------------------------+---------------+--------------------------------+-------------+-----------------------+
|      **PARAMETER NAME**      | **DATA TYPE** |        **DESCRIPTION**         | **DEFAULT** |   **VALID VALUES**    |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| ClntIntfId **[KEY]**         | uint8         | DWDM Module client interface   | N/A         | N/A                   |
|                              |               | identifier                     |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| ModuleId **[KEY]**           | uint8         | DWDM Module identifier         | N/A         | N/A                   |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| AdminState                   | string        | Administrative state of this   | UP          | UP, DOWN              |
|                              |               | client interface               |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| EnableIntSerdesNWLoopback    | bool          | Enable/Disable serdes internal | false       | N/A                   |
|                              |               | loopback                       |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostRxSerializerTap0Gain     | uint8         | Host RX Serializer tap 0       |           7 | N/A                   |
|                              |               | control                        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostRxSerializerTap2Gain     | uint8         | Host RX Serializer tap 2       |          15 | N/A                   |
|                              |               | control                        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostTxEqCtle                 | uint8         | Host interface TX deserializer |          18 | N/A                   |
|                              |               | equalization. LELRC CTLE LE    |             |                       |
|                              |               | gain code.                     |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| RXFECDecDisable              | bool          | 802.3bj FEC decoder            | false       | N/A                   |
|                              |               | enable/disable state for       |             |                       |
|                              |               | traffic from DWDM module to    |             |                       |
|                              |               | Host                           |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| EnableHostLoopback           | bool          | Enable/Disable loopback on     | false       | N/A                   |
|                              |               | all host lanes of this client  |             |                       |
|                              |               | interface                      |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostRxSerializerTap1Gain     | uint8         | Host RX Serializer tap 1       |           7 | N/A                   |
|                              |               | control                        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostRxSerializerTap2Delay    | uint8         | Host RX Serializer tap 2       |           5 | N/A                   |
|                              |               | control                        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostTxEqLfCtle               | uint8         | Host interface TX deserializer |           0 | N/A                   |
|                              |               | equalization. LELPZRC LF-CTLE  |             |                       |
|                              |               | LFPZ gain code.                |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| TxPRBSPattern                | string        | PRBS pattern to use for        | 2^31        | 2^7, 2^15, 2^23, 2^31 |
|                              |               | checker                        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| NwLaneTributaryToClntIntfMap | uint8         | Network lane/tributary id to   | N/A         | N/A                   |
|                              |               | map to client interface        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| RxPRBSPattern                | string        | RX PRBS generator pattern      | 2^31        | 2^7, 2^15, 2^23, 2^31 |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| TXFECDecDisable              | bool          | 802.3bj FEC decoder            | false       | N/A                   |
|                              |               | enable/disable state for       |             |                       |
|                              |               | traffic from Host to DWDM      |             |                       |
|                              |               | Module                         |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| EnableRxPRBS                 | bool          | Enable/Disable RX PRBS         | false       | N/A                   |
|                              |               | generation for all lanes of    |             |                       |
|                              |               | this client interface          |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| EnableTxPRBSChecker          | bool          | Enable/Disable TX PRBS checker | false       | N/A                   |
|                              |               | for all lanes of this client   |             |                       |
|                              |               | interface                      |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostRxSerializerTap0Delay    | uint8         | Host RX Serializer tap 0       |           7 | N/A                   |
|                              |               | control                        |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+
| HostTxEqDfe                  | uint8         | Host interface TX deserializer |           0 | N/A                   |
|                              |               | equalization. s-DFE            |             |                       |
+------------------------------+---------------+--------------------------------+-------------+-----------------------+



*FlexSwitch CURL API Supported*
------------------------------------

	- GET By Key
		 curl -X GET -H 'Content-Type: application/json' --header 'Accept: application/json' -d '{<Model Object as json-Data>}' http://device-management-IP:8080/public/v1/config/DWDMModuleClntIntf
	- GET By ID
		 curl -X GET http://device-management-IP:8080/public/v1/config/DWDMModuleClntIntf/<uuid>
	- GET ALL
		 curl -X GET http://device-management-IP:8080/public/v1/config/DWDMModuleClntIntf?CurrentMarker=<x>&Count=<y>
	- UPDATE(PATCH) By Key
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/DWDMModuleClntIntf
	- UPDATE(PATCH) By ID
		 curl -X PATCH -H 'Content-Type: application/json' -d '{<Model Object as json data>}'  http://device-management-IP:8080/public/v1/config/DWDMModuleClntIntf<uuid>


*FlexSwitch SDK API Supported:*
------------------------------------



- **GET**


::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getDWDMModuleClntIntf(ClntIntfId=clntintfid, ModuleId=moduleid)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **GET By ID**


::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getDWDMModuleClntIntfById(ObjectId=objectid)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'




- **GET ALL**


::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.getAllDWDMModuleClntIntfs()

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'




- **UPDATE**

::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.updateDWDMModuleClntIntf(ClntIntfId=clntintfid, ModuleId=moduleid, AdminState=adminstate, EnableIntSerdesNWLoopback=enableintserdesnwloopback, HostRxSerializerTap0Gain=hostrxserializertap0gain, HostRxSerializerTap2Gain=hostrxserializertap2gain, HostTxEqCtle=hosttxeqctle, RXFECDecDisable=rxfecdecdisable, EnableHostLoopback=enablehostloopback, HostRxSerializerTap1Gain=hostrxserializertap1gain, HostRxSerializerTap2Delay=hostrxserializertap2delay, HostTxEqLfCtle=hosttxeqlfctle, TxPRBSPattern=txprbspattern, NwLaneTributaryToClntIntfMap=nwlanetributarytoclntintfmap, RxPRBSPattern=rxprbspattern, TXFECDecDisable=txfecdecdisable, EnableRxPRBS=enablerxprbs, EnableTxPRBSChecker=enabletxprbschecker, HostRxSerializerTap0Delay=hostrxserializertap0delay, HostTxEqDfe=hosttxeqdfe)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'


- **UPDATE By ID**

::

	import sys
	import os
	from flexswitchV2 import FlexSwitch

	if __name__ == '__main__':
		switchIP := "192.168.56.101"
		swtch = FlexSwitch (switchIP, 8080)  # Instantiate object to talk to flexSwitch
		response, error = swtch.updateDWDMModuleClntIntfById(ObjectId=objectidAdminState=adminstate, EnableIntSerdesNWLoopback=enableintserdesnwloopback, HostRxSerializerTap0Gain=hostrxserializertap0gain, HostRxSerializerTap2Gain=hostrxserializertap2gain, HostTxEqCtle=hosttxeqctle, RXFECDecDisable=rxfecdecdisable, EnableHostLoopback=enablehostloopback, HostRxSerializerTap1Gain=hostrxserializertap1gain, HostRxSerializerTap2Delay=hostrxserializertap2delay, HostTxEqLfCtle=hosttxeqlfctle, TxPRBSPattern=txprbspattern, NwLaneTributaryToClntIntfMap=nwlanetributarytoclntintfmap, RxPRBSPattern=rxprbspattern, TXFECDecDisable=txfecdecdisable, EnableRxPRBS=enablerxprbs, EnableTxPRBSChecker=enabletxprbschecker, HostRxSerializerTap0Delay=hostrxserializertap0delay, HostTxEqDfe=hosttxeqdfe)

		if error != None: #Error not being None implies there is some problem
			print error
		else :
			print 'Success'
