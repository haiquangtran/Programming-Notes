# SQL and Databases

## Deadlocks
- Cycle locks
  - Occurs when process A locks table B and process B locks table A, they both hold the locks for those tables, and now process A wants to access table A, and process B wants to access process B but they can't because they are both locked. Stalemate scenario. 
  - 1 process has to be terminated
- **How SQL Server handles deadlocks**
  - Lock monitor looks for deadlocks every 5 seconds. When detected, it chooses one of the transactions to be the victim and terminates it. The terminated transaction gets rolledback, and releases all it's resources.
  - SQL Server chooses its victim based on Deadlock_priority (which you can set), or if the priorities are the same, then it will choose the lowest cost (least resources) transaction and roll it back. 
- **Minimize deadlocks**
  - Hold locks as short as possible
  - Access resources in the same order
  - Limit lock escalation by using hints such as ROWLOCK etc
  - Use READ COMMITTED SNAPSHOT ISOLATION or SNAPSHOT ISOLATION etc.

## Locks
- Shared lock:
  - Used for select
  - Enables other sessions to select operations but prevents updates
  - read-only operations
  - this lock type, when imposed, will reserve a page or row to be available only for reading, which means that any other transaction will be prevented to modify the locked record as long as the lock is active. However, a shared lock can be imposed by several transactions at the same time over the same page or row and in that way several transactions can share the ability for data reading since the reading process itself will not affect anyhow the actual page or row data. In addition, a shared lock will allow write operations, but no DDL changes will be allowed.
- Exclusive lock:
  - Used for DML operations
  - Prevents others from accessing the resource
  - Operations such as INSERT
  - Ensures multiple updates cannot be made to the same resource at the same time
- Update lock:
  - Preliminary stage for exclusive lock.
  - Used by server when filtering records to be modified.
  - Prevents other update locks
  - A solution to the cycle deadlock problem
- Conversion/Intent lock:
  - Used for establishing a lock hierarchy
  - Types of intent locks are:
	- Intent shared (IS)
	- Intent exclusive (IX)
	- Shared with intent exclusive (SIX)


