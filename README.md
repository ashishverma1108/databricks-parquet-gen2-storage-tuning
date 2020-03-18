# databricks-parquet-gen2-storage-tuning
Personal notes to performance tune parquet I/O from adls gen2 and processing using databricks

### 1. Identify correct cluster type
#####   - Leverage storage optimized clusters for solving massive spills
### 2. Identify correct cluster size
#####   - Increase worker memomry, another way to address spilled data
### 3. Identify correct block size
### 4. Use correct function and parameters to write parquet
#####   'mode("overwrite")' doesn't seem most optimized
### 5. Improve partitioning approach
#####   - identify size of the partition
#####   - Choose an appropriate column for repartitioning.. this column should be unifromaly distriute records/tasks among workers
#####   - Ensure records/tasks are uniformaly distributed accross workers
### 6. Try out of the box optimization techniques
#####   - 'OPTIMIZE' command
#####   - ZORDER partitioning
