<h1>Lab 4 - CST8913_Cloud_Migration</h1>

**1)**
   <ol><li>1)Digital Estate refers to all the digital assets of an individual or organization. Some examples of these assets include infrastructure (ex: servers, VMs), applications, data (ex: databases). </li>
   <li>2)Knowing the digital estate matters of an orginazation before migrating to the cloud is important because it shows what systems exist and how they depend on each other. </li>
   <li>3)<ul><li>Downtime when systems stop working because they rely on other servers that weren’t migrated</li>
        <li>Data loss from moving data systems without proper planning. An example being moving a database without having proper backups.</li>
       <li>Higher costs due to migrating unnecessary or oversized resources</li></ul></ol>

**2)**
   <ol><li>1) - Azure Migrate is an appliance run locally in the on-prem environment in order to indentify workloads in use, dependencies between said workloads, and workload optimization in order to help optimize migration to Azure services.</li>
  <li>2) <ul><li>- Machine, disk, and network interface (NIC) metadata</li>
       <li>- Installed applications, roles, and features</li>
       <li>- Performance data such as CPU and memory utilization, disk IOPS, and throughput</li></ul>
   <li>3) - The workloads identified would be the Web server workload, the Application server workload, the SQL server workload, the Active Directory server workload, and the File server workload.</li></ol>

**3)**
  <ol><li>1)The Web Server is dependant on the Application Server, in order to communicate requests and their responses. The Application Server is likely dependant on the SQL Server for retrieval of stored data. The Application Server may be dependant on the File Server if it requires file access. All servers depend on Active Directory for authentication and secure access.</li>
  <li>2)By analyzing where dependencies exist, a migration plan can migrate dependent services together, avoiding outages caused by missing required services.</li>
  <li>3)Given the dependencies described in 3.1, one possible migration group could be the Web Server, the Application Server, and Active Directory (*assuming the Application Server is not dependant on the File Server).</li></ol>
  
4)
  **Server**  	**Azure Readiness**	                        **Justification**
  WEB-01	  Ready 	                                The application server is running on a current operating system. A "lift and shift" approach can be taken.
  APP-01  	Conditionally Ready                     Windows 16 Server is no longer receiving feature updates. Consider if the OS should be updated.
  DB-01	    Conditionally Ready                     Windows 16 Server is no longer receiving feature updates. Consider if the OS should be updated. Cost analysis of moving the database workload to the cloud should be considered.
  DC-01    	Conditionally Ready                     Crucial to the operations of all services. Provides the largest security risk as is responsible for authentication. Extra care should be taken while migrating.
  FILE-01	  Not Ready	                              As pointed out in the lab handout, Windows Server 2012 is a legacy OS and is not supported by Microsoft (no updates). 

5)
