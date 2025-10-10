1. Bus Topology
Location: /topologies/bus/
Characteristics:

Layout: Single central cable (backbone) with all devices connected directly

Data Transmission: Broadcast-based; all devices see all traffic

Fault Tolerance: Single point of failure - if backbone fails, entire network fails

Performance: Performance degrades with more devices due to collisions

Cost: Low implementation cost

Scalability: Difficult to scale; limited by cable length and number of connections

Typical Use: Small networks, legacy systems

2. Mesh Topology
Location: /topologies/mesh/
Characteristics:

Layout: Every device connected to every other device

Data Transmission: Multiple paths available; point-to-point connections

Fault Tolerance: High redundancy; multiple paths ensure connectivity

Performance: Excellent performance with dedicated paths

Cost: High implementation cost (many cables and ports)

Scalability: Difficult and expensive to scale

Types:

Full Mesh: Every device connected to all others

Partial Mesh: Some devices have multiple connections

Typical Use: Critical infrastructure, backbone networks

3. Star Topology
Location: /topologies/star/
Characteristics:

Layout: All devices connected to a central hub/switch

Data Transmission: Centralized through hub/switch

Fault Tolerance: Single point of failure (central device); easy device isolation

Performance: Good; no collisions in switched environment

Cost: Moderate (requires central device)

Scalability: Easy to scale; add devices to central switch

Typical Use: Most modern LANs, office networks

4. Ring Topology
Location: /topologies/ring/
Characteristics:

Layout: Devices connected in circular fashion

Data Transmission: Unidirectional or bidirectional token passing

Fault Tolerance: Single point of failure (if one device fails, entire ring may fail)

Performance: Predictable performance; no collisions

Cost: Moderate

Scalability: Difficult to scale; adding devices disrupts ring

Types:

Single Ring: Data travels in one direction

Dual Ring: Redundant ring for fault tolerance

Typical Use: Token Ring networks, FDDI

5. Extended Star Topology
Location: /topologies/extended-star/
Characteristics:

Layout: Multiple star topologies connected together

Data Transmission: Hierarchical data flow through multiple switches

Fault Tolerance: Better than simple star; can isolate segments

Performance: Good with proper hierarchy design

Cost: Higher than simple star (more switches required)

Scalability: Excellent; easy to add more stars

Typical Use: Large enterprise networks, campus networks

