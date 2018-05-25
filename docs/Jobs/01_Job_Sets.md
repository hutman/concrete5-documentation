Jobs can be separated into sets in order to run different jobs at different times using a Cron.

### $jobSet = Concrete\Core\Job\Set::getByID($id);

Get the job set by the job set ID.

### $jobSet = Concrete\Core\Job\Set::getByName($name);

Get the job set by the job set Name.

### $defaultSet = Concrete\Core\Job\Set::getDefault();

Get the Default job set.

### $jobSet->getJobSetID();

Get the job set id

### $jobSet->getJobSetName();

Get the job set name

### $jobSet->getPackageID();

Get the job set package id

### $jobSet->getJobSetDisplayName();

Get the job set display name

### $jobList = $jobSet->getList();

Get the list of jobs in this job set.