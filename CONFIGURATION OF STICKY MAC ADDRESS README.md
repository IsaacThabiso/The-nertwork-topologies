Sticky MAC Address is a port security feature that dynamically learns and "sticks" MAC addresses to a switch port, then automatically converts them to static secure MAC addresses in the running configuration.

⚙️ Characteristics & Behavior
1. Dynamic Learning
Initial Learning: Dynamically learns MAC addresses from connected devices

Persistence: "Sticks" learned addresses to the port configuration

Automatic Conversion: Converts dynamic MAC entries to static secure MAC addresses

2. Configuration Persistence
Running Config: Saved in running configuration immediately

Startup Config: Requires copy running-config startup-config to survive reload

MAC Table: Appears in both MAC address table and port security table

3. Aging Characteristics
Default Behavior: No aging by default (addresses remain permanently)

Configurable Aging: Can enable aging with specific timeout

Aging Types:

Absolute: Removes after exact time period

Inactivity: Removes only if no traffic from MAC address
 Violation Actions
1. Protect
Action: Drops packets from unauthorized MACs

Notification: No log messages or SNMP traps

Port Status: remains up

2. Restrict
Action: Drops packets + generates log messages/SNMP traps

Notification: Security violation counter increments

Port Status: remains up

3. Shutdown (Default)
Action: Shuts down port (err-disabled state)

Notification: Log messages + SNMP traps

Recovery: Requires manual intervention or err-disable recovery
