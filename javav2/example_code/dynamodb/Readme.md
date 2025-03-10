# Amazon DynamoDB Java code examples

This README discusses how to run and test the Java code examples for Amazon DynamoDB.

## Running the Amazon DynamoDB Java files

**IMPORTANT**

The Java examples perform AWS operations for the account and AWS Region for which you've specified credentials, and you might incur AWS service charges by running them. See the [AWS Pricing page](https://aws.amazon.com/pricing/) for details about the charges you can expect for a given service and operation.   

Some of these examples perform *destructive* operations on AWS resources, such as deleting a table. **Be very careful** when running an operation that deletes or modifies AWS resources in your account. It's best to create separate test-only resources when experimenting with these examples.

To run these examples, you can setup your development environment to use Apache Maven or Gradle to configure and build AWS SDK for Java projects. For more information, 
see [Get started with the AWS SDK for Java 2.x](https://docs.aws.amazon.com/sdk-for-java/latest/developer-guide/get-started.html). 

You will find these examples: 

- **CreateTable** - Demonstrates how to create an Amazon DynamoDB table.
- **CreateTableCompositeKey** - Demonstrates how to create an Amazon DynamoDB table with a composite key.
- **DeleteItem** - Demonstrates how to delete an item from an Amazon DynamoDB table.
- **DeleteTable** - Demonstrates how to delete an Amazon DynamoDB table.
- **DescribeTable** - Demonstrates how to retrieve information about an Amazon DynamoDB table.
- **EnhancedBatchWriteItems** - Demonstrates how to insert many items into an Amazon DynamoDB table by using the enhanced client.
- **EnhancedGetItem.** - Demonstrates how to retrieve an item from an Amazon DynamoDB table by using the enhanced client.
- **DynamoDBScanItems** - Demonstrates how to return items from an Amazon DynamoDB table.
- **EnhancedModifyItem** - Demonstrates how to modify an item located in an Amazon DynamoDB table by using the enhanced client.
- **EnhancedPutItem** - Demonstrates how to put an item into an Amazon DynamoDB table by using the enhanced client.
- **EnhancedQueryRecords** - Demonstrates how to query an Amazon DynamoDB table by using the enhanced client.
- **EnhancedQueryRecordsWithFilter** - Demonstrates how to query an Amazon DynamoDB table with a filter and by using the enhanced client.
- **EnhancedQueryRecordsWithSortKey** - Demonstrates how to query a table with a sort key.
- **EnhancedScanRecords** - Demonstrates how to scan an Amazon DynamoDB table by using the enhanced client.
- **GetItem** - Demonstrates how to retrieve an item from an Amazon DynamoDB table.
- **ListTables** - Demonstrates how to list all Amazon DynamoDB tables.
- **PutItem** - Demonstrates how to place an item into an Amazon DynamoDB table.
- **Query** - Demonstrates how to query an Amazon DynamoDB table.
- **Scenario** - Demonstrates how to perform various Amazon DynamoDB operations.
- **UpdateItem** - Demonstrates how to update a value located in an Amazon DynamoDB table.
- **UpdateTable** - Demonstrates how to update an Amazon DynamoDB table.


 ## Testing the DynamoDB Java files

You can test the Java code examples for Amazon DynamoDB by running a test file named **DynamoDBTest**. This file uses JUnit 5 to run the JUnit tests and is located in the **src/test/java** folder. For more information, see [https://junit.org/junit5/](https://junit.org/junit5/).

You can run the JUnit tests from a Java IDE, such as IntelliJ, or from the command line by using Maven. As each test is run, you can view messages that inform you if the various tests succeed or fail. For example, the following message informs you that Test 3 passed.

	Test 3 passed

**WARNING**: _Running these JUnit tests manipulates real Amazon DynamoDB resources and might incur charges on your account._

 ### Properties file
Before running the Amazon DynamoDB JUnit tests, you must define values in the **config.properties** file located in the **resources** folder. This file contains values that are required to run the JUnit tests. For example, you define a table name used for various tests. If you do not define all values, the JUnit tests fail.

Define these values to successfully run the JUnit tests:

- **tableName** - The name of an Amazon DynamoDB table. For example, **Music3**.
- **fileName** - The path to the JSON document that contains movie data that you can download from the Amazon DynamoDB Developer Guide.
- **enhancedTableName** - the name of the DynamoDB table used with the enhanced client. For example, **Customer**.
- **key** – The name of a key to use. For example, **Artist**.
- **enhancedTableKey** the  name of a key to use for the enhanced client tests. For example, **Id**.
- **keyValue** – The key value. For example, **Famous Band**.
- **albumTitle** – An album title to use. For example, **AlbumTitle**.
- **AlbumTitleValue** – An album title value. For example, **Songs About Life**.
- **Awards** – A value for a column. For example, **Awards**.
- **AwardVal** – The value for the Awards column. For example, **10**.
- **SongTitle** – A value for another column. For example, **SongTitle**.
- **SongTitleVal** – The value for the SongTitle column. For example, **Happy Summer Day**.

### Command line
To run the JUnit tests from the command line, you can use the following command.

		mvn test

You will see output from the JUnit tests, as shown here.

	[INFO] -------------------------------------------------------
	[INFO]  T E S T S
	[INFO] -------------------------------------------------------
	[INFO] Running DynamoDBTest
	Running Amazon DynamoDB   Test 1
	Running Amazon DynamoDB  Test 2
	...
	Done!
	[INFO] Results:
	[INFO]
	[INFO] Tests run: 13, Failures: 0, Errors: 0, Skipped: 0
	[INFO]
	INFO] --------------------------------------------
	[INFO] BUILD SUCCESS
	[INFO]--------------------------------------------
	[INFO] Total time:  12.003 s
	[INFO] Finished at: 2020-02-10T14:25:08-05:00
	[INFO] --------------------------------------------

### Unsuccessful tests

If you do not define the correct values in the properties file, your JUnit tests are not successful. You will see an error message such as the following. You need to double-check the values that you set in the properties file and run the tests again.

	[INFO]
	[INFO] --------------------------------------
	[INFO] BUILD FAILURE
	[INFO] --------------------------------------
	[INFO] Total time:  19.038 s
	[INFO] Finished at: 2020-02-10T14:41:51-05:00
	[INFO] ---------------------------------------
	[ERROR] Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:2.22.1:test (default-test) on project S3J2Project:  There are test failures.
	[ERROR];
