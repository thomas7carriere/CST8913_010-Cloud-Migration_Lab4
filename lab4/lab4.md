<h1>Lab 4 - CST8913_Cloud_Migration</h1>

**1)**
   <ul><li>1.1) Digital Estate refers to all the digital assets of an individual or organization. Some examples of these assets include infrastructure (ex: servers, VMs), applications, data (ex: databases). </li>
   <li>1.2) Knowing the digital estate matters of an orginazation before migrating to the cloud is important because it shows what systems exist and how they depend on each other. </li>
   <li>1.3)<ul><li>Downtime when systems stop working because they rely on other servers that weren’t migrated</li>
        <li>Data loss from moving data systems without proper planning. An example being moving a database without having proper backups.</li>
       <li>Higher costs due to migrating unnecessary or oversized resources</li></ul></ul>

**2)**
   <ul><li>2.1) Azure Migrate is an appliance run locally in the on-prem environment in order to indentify workloads in use, dependencies between said workloads, and workload optimization in order to help optimize migration to Azure services.</li>
  <li>2.2) <ul><li>Machine, disk, and network interface (NIC) metadata</li>
       <li>Installed applications, roles, and features</li>
       <li>Performance data such as CPU and memory utilization, disk IOPS, and throughput</li></ul>
   <li>2.3) The workloads identified would be the Web server workload, the Application server workload, the SQL server workload, the Active Directory server workload, and the File server workload.</li></ul>

**3)**
  <ul><li>3.1) The Web Server is dependant on the Application Server, in order to communicate requests and their responses. The Application Server is likely dependant on the SQL Server for retrieval of stored data. The Application Server may be dependant on the File Server if it requires file access. All servers depend on Active Directory for authentication and secure access.</li>
  <li>3.2) By analyzing where dependencies exist, a migration plan can migrate dependent services together, avoiding outages caused by missing required services.</li>
  <li>3.3) Given the dependencies described in 3.1, one possible migration group could be the Web Server, the Application Server, and Active Directory (*assuming the Application Server is not dependant on the File Server).</li></ul>
  
**4)**
 <table>
  <tr>
    <th>Server</th>
    <th>Azure Readiness</th>
    <th>Justification</th>
  </tr>
  <tr>
    <td>WEB-01</td>
    <td>Ready</td>
    <td>The application server is running on a current operating system. A lift-and-shift approach can be taken.</td>
  </tr>
  <tr>
    <td>APP-01</td>
    <td>Conditionally Ready</td>
    <td>Windows Server 2016 is no longer receiving feature updates. Consider upgrading the OS before migration.</td>
  </tr>
  <tr>
    <td>DB-01</td>
    <td>Conditionally Ready</td>
    <td>Windows Server 2016 is no longer receiving feature updates. OS upgrade and cost analysis for migrating the database workload should be considered.</td>
  </tr>
  <tr>
    <td>DC-01</td>
    <td>Conditionally Ready</td>
    <td>Critical to all services and responsible for authentication. Presents a higher security risk, requiring extra care during migration.</td>
  </tr>
  <tr>
    <td>FILE-01</td>
    <td>Not Ready</td>
    <td>Windows Server 2012 is a legacy OS and is no longer supported by Microsoft, meaning no security or feature updates.</td>
  </tr>
</table>

**5)**
 <ul><li>5.1) Once marked as Azure Ready, Azure's server asessment tool can recommend sizing of Azure VMs and disk types based on-prem resources, as well as their related costs. This can be done with or without performance metrics of the resources, but ideally with them to improve optimizations. Database sku's can also be recommend, as well as their respective pricing tiers. </li>
  <li>5.2)</li><ul><li> Performance-based sizing takes into account the performance history of the on-prem services in order to recommend Azure solutions that will meet the clients needs without wasting resources by over-provisioning.</li>
   <li>As-is sizing only considers the on-prem hardware to generate recommedations, which may prove inefficient if the resources were initially over-provisioned. This could incur unecessary costs.</li></ul></ul>
