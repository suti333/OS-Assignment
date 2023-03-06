## Starve-Free Readers-Writers Problem Solution:

In the case of traditional Readers-Writers Problem, we use two semaphores: mutex and wrt. The mutex semaphore is used to update the readcount variable, which denotes the number of readers currently reading the database. Only the first reader has to acquire the wrt mutex to enter the critical section whereas all writers have to access it in order to do so. The last reader signals the wrt semaphore after completing reading. Therefore, it creates a situation where writers starve indefinitely when ininite readers queue up to get into the critical section.

In the case of Starve-Free Readers-Writers Problem, we introduce a new semaphore named enter. All readers and writers have to acquire this semaphore before entering in the critical region with equal priority. Thus if a writer arrives in between two readers, the writer will get a fair chance to acquire the enter mutex and enter the critical region, provided no reader is busy there. Thus, in this case, neither readers nor writers starve.

The pseudocode for the above implementation can be found in Starve_Free_Readers_Writers_Solution.txt
