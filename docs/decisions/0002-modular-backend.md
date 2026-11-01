# ADR-0002: Modular Monolith Architecture for the Backend
This ADR elaborates the Modular Monolith decision from ADR-0001.
See ADR-0001 for the initial architecture decisions.

## Status
>Accepted

## Context
If we account for possible future improvements in advance, we can avoid
potential issues in the future. To this end, we use a modular structure
for the backend.

## Modules
### Identity
>This module is responsible for user authentication and authorization.
#### Includes
- Registration of users (in the future).
- Authorization.
- Session termination.
- API access control.
- User session management.
- Roles and access rights.

### Inventory
>This module is responsible for information about which devices are in the network.
#### Includes
##### Hosts/Nodes
- Adding devices.
- Updating devices.
- Removing devices.
- IP and hostname.
- Type of device.
- Description and tags.
##### Agents
- Registering agents.
- Token grants.
- Receiving heartbeats.
- Agent version monitoring.
- Agent revocation.
##### Containers
- List of detected Docker containers.
- Names and images.
- Status.
- Server binding.
#### Alternatives
- Creating separate modules for agents and containers. Rejected as unnecessary for the MVP.

### Monitoring
>This module is responsible for receiving, processing and providing information about infrastructure status.
#### Includes
- Receiving server metrics.
- Receiving Docker container metrics.
- Receiving metrics history.
- Preparing data for charts.
- Defining performance indicators.
- Working with threshold values and monitoring rules.

### Topology
>This module is responsible for connections between devices on the visual map.
#### Includes
- Adding connections between devices.
- Removing connections.
- Updating connections.
- Preserving the arrangement of elements on the visual map.
- Providing data for visualization.

### Diagnostics - the main feature module
>This module is responsible for checking availability and status of network services.
#### Includes
- ICMP checks.
- TCP checks.
- DNS checks.
- HTTP/HTTPS checks.
- Configuring check frequency.
- Starting checks.
- Saving results.
- History of diagnostics.

### Incidents
>This module is responsible for the registration and processing of incidents.
#### Includes
- Receiving events.
- Checking whether a similar open incident exists.
- Creating a new incident or update an existing one.
- Saving history.
- Processing confirmations.
- Closing an incident after recovery.

### Notifications
>This module is responsible for sending notifications to users via Telegram.
#### Includes
- Configuring the Telegram bot.
- Configuring recipients.
- Sending notifications.
- Handling sending errors.
- Retry attempts.
- Notification delivery history.

## How Modules Interact
Identity -> Inventory/Monitoring/Topology/Diagnostics/Incidents <-> Notifications
>Arrows show request dependencies. <-> means bidirectional interaction with Notifications