Accessible through the system section of the dashboard, jobs are ways of automating certain processes available to concrete5. These jobs can be run from the dashboard, or easily cronned and run from the server at specified intervals.

## Creating Your Own Job

Creating your own job is as simple as creating a new class in the Job format, and adding it to the application/jobs/ directory in your local web root. This job will then appear on the Jobs page in your site's dashboard, can then be installed and run easily.

### Create the File

In your local application/jobs/ directory, create a file in the typical concrete5 handle format. (all lowercase, with underscores separating spaces. e.g. "job_handle.php")

### Create a class in this file

Within this file, take the name of your file (minus .php) and camelcase it, and use that as your job's class name, while extending the \Concrete\Core\Job\Job class.

```
class JobHandle extends \Concrete\Core\Job\Job
```

### Specify the Job name and description

Within this file, define the method getJobName() and getJobDescription(), with each returning the relevant piece of information about the job.

### Define the run() function

Inside a run() function of your Job, define whatever programming logic you wish to execute when the Job is run.

### Setup error handling and output

Within your run() method, handle errors by using the throw() method and native PHP exception support. Any exceptions that occur within your job will cease the job from running and be reported to the administrator when they next visit the Jobs page in the dashboard.

If you would like to return custom output for the status of your job, simply return a string from your run() method.

### Installing a Job with a Package

Addon developers may install Jobs with their packages. To do this, simply include the job file in a jobs/ directory within the package, and execute the following code from within your package's install() command:

```
Job::installByPackage('job_handle', $pkg);
```

Any jobs installed in this way will automatically be removed if your package is uninstalled.

## Full Job Example

```
File is: /packages/package_name/jobs/job_handle.php

<?php
namespace Concrete\Package\PackageName\Job;

class JobHandle extends \Concrete\Core\Job\Job
{

    public function getJobName()
    {
        return t("Job Name");
    }

    public function getJobDescription()
    {
        return t("Job Description");
    }

    public function run()
    {
        //do the functions of the job
    }
}
```