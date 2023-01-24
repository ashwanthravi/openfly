### High level system architecture

The overall system needs to be reactive -> it is asynchronous and will update instantly when new data is available

- The functionality shoould be exchangeable and reusable
- Asynchronous communication
- system can deal with varying workload

https://www.reactivemanifesto.org/glossary

Reactive systems are :

1. Responsive - the system reacts in a timely manner
2. Resilient - system stays responsive in the face of failure. This is achieved by replication, containment, isolation and delegation
3. Elastic - the system stays responsive under varying workload
4. Message driven - Asynchronous messaging to establish boundary between components that ensures loose coupling, isolation and location transparency. This boundary also provides the means to delegate failures as messages.

### Overview

Flight stack -> estimation and flight control system

middleware -> provides internal/external communications and hardware integration

### Flight Stack

- Position and Altitude Estimator = calculates vehicle state
- Navigator
- Position Controller
- Attitude & Rate Controller
- RC input
- Mixer = takes force commands and tranlates them into motor commands, ensures limits are not exceeded
  (This translation is specific for a vehicle type and depends on various factors, such as the motor arrangements with respect to the center of gravity, or the vehicle's rotational inertia.

### Middleware

- device drivers for sensors
- communication with external world (GCS, companion computer)
- message bus
- simulation layer

### Runtime Environment

POSIX-API (Linux)
Real-time scheduling eg. FIFO
inter-module communication is based on shared memory
