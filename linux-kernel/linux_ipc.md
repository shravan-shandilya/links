IPC is divided into
1. Communnication: Exchanging data
2. Synchronisation: Co-ordination between different processes
3. Signals: Can be both communication mechanism and synchronising mechanism

Communication:
  * Byte oriented: writer writes as many bytes,reader read as many bytes
  * Messages: writer writes a message and reader reads it (no partial data transfers,no double reads)
  * Psuedo terminals
