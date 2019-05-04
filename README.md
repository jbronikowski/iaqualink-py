# Asynchronous library for Jandy iAqualink

Mainly created for use with Home Assistant.

Usage:
```python
>>> async with AqualinkClient('xxx@example.com', 'password') as c:
...     s = await c.get_systems()
...     print(s)
...     d = await list(s.values())[0].get_devices()
...     print(d)
... 
{'QVP3YX4NERHV': AqualinkPoolSystem(name='Pool' serial='XXX' data={'id': 1234, 'serial_number': 'XXX', 'created_at': '2017-09-23T01:00:08.000Z', 'updated_at': '2017-09-23T01:00:08.000Z', 'name': 'Pool', 'device_type': 'iaqua', 'owner_id': None, 'updating': False, 'firmware_version': None, 'target_firmware_version': None, 'update_firmware_start_at': None, 'last_activity_at': None})}
{'spa_temp': AqualinkSensor(name='spa_temp' data={'name': 'spa_temp', 'state': '100'}), 'pool_temp': AqualinkSensor(name='pool_temp' data={'name': 'pool_temp', 'state': ''}), 'air_temp': AqualinkSensor(name='air_temp' data={'name': 'air_temp', 'state': '76'}), 'spa_set_point': AqualinkThermostat(name='spa_set_point' data={'name': 'spa_set_point', 'state': '102'}), 'pool_set_point': AqualinkThermostat(name='pool_set_point' data={'name': 'pool_set_point', 'state': '84'}), 'cover_pool': AqualinkSensor(name='cover_pool' data={'name': 'cover_pool', 'state': ''}), 'freeze_protection': AqualinkBinarySensor(name='freeze_protection' data={'name': 'freeze_protection', 'state': '0'}), 'spa_pump': AqualinkPump(name='spa_pump' data={'name': 'spa_pump', 'state': '1'}), 'pool_pump': AqualinkPump(name='pool_pump' data={'name': 'pool_pump', 'state': '1'}), 'spa_heater': AqualinkHeater(name='spa_heater' data={'name': 'spa_heater', 'state': '0'}), 'pool_heater': AqualinkHeater(name='pool_heater' data={'name': 'pool_heater', 'state': '0'}), 'solar_heater': AqualinkHeater(name='solar_heater' data={'name': 'solar_heater', 'state': '1'}), 'spa_salinity': AqualinkSensor(name='spa_salinity' data={'name': 'spa_salinity', 'state': ''}), 'pool_salinity': AqualinkSensor(name='pool_salinity' data={'name': 'pool_salinity', 'state': ''}), 'orp': AqualinkSensor(name='orp' data={'name': 'orp', 'state': ''}), 'ph': AqualinkSensor(name='ph' data={'name': 'ph', 'state': ''}), 'aux_1': AqualinkAuxToggle(name='aux_1' data={'aux': '1', 'name': 'aux_1', 'state': '0', 'label': 'CLEANER', 'icon': 'aux_1_0.png', 'type': '0', 'subtype': '0'}), 'aux_2': AqualinkLightToggle(name='aux_2' data={'aux': '2', 'name': 'aux_2', 'state': '0', 'label': 'SPA LIGHT', 'icon': 'aux_1_0.png', 'type': '0', 'subtype': '0'}), 'aux_3': AqualinkLightToggle(name='aux_3' data={'aux': '3', 'name': 'aux_3', 'state': '0', 'label': 'POOL LIGHT', 'icon': 'aux_1_0.png', 'type': '0', 'subtype': '0'}), 'aux_4': AqualinkAuxToggle(name='aux_4' data={'aux': '4', 'name': 'aux_4', 'state': '0', 'label': 'AIR BLOWER', 'icon': 'aux_1_0.png', 'type': '0', 'subtype': '0'}), 'aux_5': AqualinkAuxToggle(name='aux_5' data={'aux': '5', 'name': 'aux_5', 'state': '0', 'label': 'SHEER DSCNT', 'icon': 'aux_1_0.png', 'type': '0', 'subtype': '0'})}
```