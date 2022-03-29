<p align="center" style="background-color:"><img src="../assets/logo.jpeg"  width="400"></p><p align="center"><h2 style="color: #193967; text-align: center">
    Distributed Systems
</h2></p>
<p align="center"><h4 style="color: #193967; text-align: center">
    Kabelo Masemola < kabelo.masemola@sambe.co.za>
</h4></p>

### What are distributed systems
A distributed system, also known as distributed computing, is a system with multiple components located on different machines that communicate and coordinate actions in order to appear as a single coherent system to the end-user.

### Overview
The machines that are a part of a distributed system may be computers, physical servers, virtual machines, containers, or any other node that can connect to the network, have local memory, and communicate by passing messages.

There are two general ways that distributed systems function:
1.Each machine works toward a common goal and the end-user views results as one cohesive unit.
2. Each machine has its own end-user and the distributed system facilitates sharing resources or communication services.

Although distributed systems can sometimes be obscure, they usually have three primary characteristics: all components run concurrently, there is no global clock, and all components fail independently of each other.

### Benefits and challenges of distributed systems
- **Horizontal Scalability** —Since computing happens independently on each node, it is easy and generally inexpensive to add additional nodes and functionality as necessary.
- **Reliability** —Most distributed systems are fault-tolerant as they can be made up of hundreds of nodes that work together. The system generally doesn’t experience any disruptions if a single machine fails.
- **Performance** —Distributed systems are extremely efficient because work loads can be broken up and sent to multiple machines.


However, distributed systems are not without challenges. Complex architectural design, construction, and debugging processes that are required to create an effective distributed system can be overwhelming.

Three more challenges you may encounter include:

- **Scheduling** —A distributed system has to decide which jobs need to run, when they should run, and where they should run. Schedulers ultimately have limitations, leading to underutilized hardware and unpredictable runtimes.
- **Latency** —The more widely your system is distributed, the more latency you can experience with communications. This often leads to teams making tradeoffs between availability, consistency, and latency.
- **Observability** —Gathering, processing, presenting, and monitoring hardware usage metrics for large clusters is a significant challenge.
