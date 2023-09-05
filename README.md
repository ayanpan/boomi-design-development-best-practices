# Boomi Best Practices
Below are some of the best practces which can be followed while designing and building a Process or other component in Boomi iPaaS.

:point_right: Name the Process and its related components as per the Naming Conventions document.

:point_right: Use the Connectors from the # Connections folder.

:point_right: Reuse the components wherever possible.

:point_right: Limit the usage of multiple Connector Call Lookups as much as possible. 

:point_right: Write Display Name in the Shapes, especially when there are multiple Shapes of similar nature. This will help identifying the flow when debugging the process in Process Reporting → Process State. 

:point_right: If the process is complex, it's recommended to write the Step Number (like 01, 02,...) in the Display Name, along with the above point.

:point_right: Use JavaScript/Groovy only when it's not possible to create the business logic using the out-of-box features. Write notes in JavaScript/Groovy code for easier understanding.

:point_right: For scripting, create a component (Process Script or Map Script) instead of "in-line" scripting, in both Data Process shapes and Map components.

:point_right: Prioritise Javascript for lightweight conditional logic and Groovy (2.4) for more complex requirements (leveraging classes).

:point_right: When using Groovy in custom scripts, use Groovy 2.4 and not Groovy 1.5 (now unsupported).

:point_right: Write notes in the process using Add Notes whenever there's a complex logic.

:point_right: Arrange the Shapes (using the Arrange button) in the Build canvas, so that the Process looks tidy.

:point_right: Set the Extensions for all the required components.

:point_right: Use Try/Catch Shape for error handling and retry wherever required. It's best to use at least 1 Try/Catch Shape in the Process and put a common error handling mechanism.

:point_right: Use the Parallel Processing feature of Flow Control Shape judiciously considering the data volume and runtime capacities.

:point_right: Use the Run each document individually feature of Flow Control Shape only when it's absolutely required.

:point_right: Use Add Description button to write a short description (preferably less than 100 words) on what the Process is doing.

:point_right: Use a Decision shape for simple/single routing decisions over a Business Rules shape.

:point_right: Check if multiple Decision Shapes can be replaced with a single Business Rules or Route Shape.

:point_right: If the number of Shapes in a Process is more, then consider grouping certain Shapes in a sub-process(es) wherever possible/practical.

:point_right: Avoid adding components in the root folder, or someone else's project/POC folder. Put your components in the appropriate folder itself. 

:point_right: Remove unused components from the main project folder, either by deleting them or by moving them to your POC folder.

:point_right: Set Tracking Fields in the process.

:point_right: Retain ability to "re-run" documents by avoiding "No Data" Start shapes in processes, wherever possible.

:point_right: When using Dynamic Process Properties, avoid enabling the "Persist this property" option unless necessary as this makes the process stateful and use additional I/O.

:point_right: In Exception Shape, avoid using “Current Data” as parameter within the message. Also, avoid using “Current Date/Time” and/or “Execution Id” as parameters within the message, as these are already captured by the system.

:point_right: In Notify Shape, avoid using “Current Data” as parameter within the message.

:point_right: Do not use an Exception shape and a Notify (Error) shape together, as this is redundant.

:point_right: Consolidate Set Property shapes when possible, by setting multiple properties at once.

:point_right: When opening a component or configuration with intention to only view the same, then don't click the "OK" or "Save" button when exiting them, instead use the "Cancel" or "X" button to exit them. This will ensure that you aren't accidentally saving any component/configuration.
Plan for Load Testing preferably in the QA MS Cloud environment for the integrations where high data volume is expected.
Use Process Mode as Low Latency or Bridge for the real-time (API based) integrations involving high data volume.
