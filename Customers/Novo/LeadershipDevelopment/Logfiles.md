Logfiles are manually updated and send to Novo using secure link send in mail

SQL Query

`SELECT  [Id]`
      `,[Timestamp]`
      `,[Action]`
      `,[Property]`
      `,[Payload]`
      `,[UserId]`
  `FROM [dbo].[LogEntries]`
   `where [Timestamp] > '2025-03-31 23:00:20.2012171'`