# Here's the code
In this section you will see abox with code in C#
```csharp
[Test("VerifyIncludeExclude", Id = "258428")]
       public void VerifyIncludeExclude()
       {
           Job tempJob = new Job(agentName, GetJobName(), Enums.JobType.SqlServer)
           {
               Destination = "Evault", FilestoInclude = @"+Default\Testdb", Description = "temporary job", JobType = Enums.JobType.SqlServer, Encryption = "None"
           };
           ComputerPage.ExpandAgent(driver, agentName);
           jobsPage.GotoJobType(driver, agentName, tempJob.JobType);
           jobsPage.CreateJobTest(driver, settings, tempJob, context);
           JobsPage.SelectJobAction(driver, tempJob, JobsPage.JobAction.Edit);
           JobsPage.ConnectTo(driver, Enums.JobType.SqlServer);
           tempJob.FilestoInclude = @"Default\Testdb";
           jobsPage.IncludeExlude(driver, settings, tempJob, context);

           jobsPage.DeleteJob(driver, tempJob);
       }
       ```


After the code block I'll just add random line
