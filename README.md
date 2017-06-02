# MeterMaid
MeterMaid facilitates the movement of PLC data into Maximo Meters via the Maximo REST API
It currently only supports CLX tags, via the pylogix library

/i             interactive mode
/dumpconfig    dumps content of YAML config to screen
/gettags       attempts to load tags from PLC's defined in config
/getmeters     attempts to load meter readings from tags defined in conig
/getmaxass     attempts to load asset information from maximo based on tag names
/postmeters    attempts to post meter readings from PLC's to maximo
/updateconfig  changes to config will be volatile unless this flag is set

Regardless of argument order, program will always process in the order shown above

Multiple flags can be set to chain functions together. For example, the following
command line will get the current meter readings from the tags in the config,
post them to maximo, and save the config to disk.

    python MeterMaid.py  /postmeters /getmeters /updateconfig
