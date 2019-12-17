# Oracle-Tutorial-9---How-to-disable-archive-log-mode
Oracle Tutorial 9 - How to disable archive log mode


Steps: ---
1. Log in as OS user, oracle and enter the following commands:

$ export ORACLE_SID=orcl
where orcl is the name of the database

In windows open cmd pront and login with following commands.

$ sqlplus /nolog
SQL> connect / as sysdba
Connected.

To enable ARCHIVELOG mode status, enter the following SQL commands:

Lets check the archive log is enable or not.
SQL> archive log list;
Database log mode              Archive Mode
Automatic archival             Enabled
Archive destination            USE_DB_RECOVERY_FILE_DEST
Oldest online log sequence     29
Next log sequence to archive   31
Current log sequence           31

arhivelog is enabled here. Run the below command.

SQL> Shutdown
Database closed.
Database dismounted.
ORACLE instance shut down.

SQL> Startup mount
ORACLE instance started.

Total System Global Area 3390558208 bytes
Fixed Size                  2180464 bytes
Variable Size            1996491408 bytes
Database Buffers         1375731712 bytes
Redo Buffers               16154624 bytes
Database mounted.

SQL> Alter database noarchivelog;
Database altered.

SQL> alter database open;


To check the ARCHIVELOG mode status, enter the following SQL command:
SQL> archive log list;

Database log mode              No Archive Mode
Automatic archival             Disabled
Archive destination            USE_DB_RECOVERY_FILE_DEST
Oldest online log sequence     30
Current log sequence           32

Now you can see the archive log is Disabled here.


Video URL : https://chittranjanmahto.blogspot.com/2019/09/oracle-tutorial-9-how-to-disable.html
