# Amazon Connect Integration Points<a name="integrationpoints"></a>

## Amazon Connect Streams<a name="streams"></a>
A browser-based contact center integration API, available on [Git](https://github.com/aws/amazon-connect-streams)\. 

The Amazon Connect Streams API \(Streams\) gives you the power to integrate your existing web applications with Amazon Connect\. The Streams API lets you embed the Contact Control Panel \(CCP\) UI components into your page, and\/or handle agent and contact state events directly, giving you the power to control agent and contact state through an object oriented, event driven interface\. You can use the built in interface, or build your own from scratch: Streams gives you the choice\.
+ When using the Streams API, you need to [whitelist](https://github.com/awsdocs/amazon-connect-admin-guide/blob/master/doc_source/app-integration.md) your domain URL\.

## Data Streaming<a name="datastreaming"></a>
You can export Contact Trace Records (\CTRs\) and agent events from Amazon Connect in order to perform analysis on your data\. This utilizes [Amazon Kinesis](https://aws.amazon.com/documentation/kinesis/)\. Data streaming is not enabled by default when you create an instance. To enable data streaming for your instance, see [Configuring Your Amazon Connect Instance](https://github.com/awsdocs/amazon-connect-admin-guide/blob/master/doc_source/amazon-connect-instances.md#data-streaming).

### Contact Trace Records \(CTRs\)<a name="ctr"></a>
+ Use an existing, manually provisioned Amazon Kinesis Stream or Amazon Kinesis Firehose\.
+ Launch the [Data Streaming](https://aws.amazon.com/quickstart/connect/data-streaming/) Quick Start, or include this with your CloudFormation template as a [nested template](cloudformation.md#topics)\.

### Agent Events<a name="agentevents"></a>
+ Use your existing Amazon Kinesis Stream from the list below, or create a new one\.
+ Amazon Connect agent event streams are Amazon Kinesis data streams that provide you with near real-time reporting of agent activity within your Amazon Connect instance\. The events published to the stream include agent login, agent logout, agent answers a call, and agent status change\.
+ [Enable](https://github.com/awsdocs/amazon-connect-admin-guide/blob/master/doc_source/agent-event-streams.md) agent event data streaming\.

## Call Recordings & Historical Reports<a name="s3sdk"></a>
Amazon Connect will store call recordings as well as historical reports in Amazon S3. These can be integrated by leveraging the [Amazon S3 API](https://docs.aws.amazon.com/AmazonS3/latest/API/Welcome.html)\.

## Live Media Streaming<a name="livemediastreaming"></a>
Amazon Connect will provide access to customer audio in realtime using Amazon Kinesis Video Streams libraries, where it can be consumed and provide voice bio-metric authentication or other use cases. By default Live Media Streaming is not enabled when you create an instance.  To enable live media streaming, see [Enable Live Media Streaming](https://github.com/awsdocs/amazon-connect-admin-guide/blob/master/doc_source/enable-live-media-streams.md)\.

