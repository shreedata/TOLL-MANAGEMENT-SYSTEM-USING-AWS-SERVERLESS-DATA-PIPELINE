# TOLL-MANAGEMENT-SYSTEM-USING-AWS-SERVERLESS-DATA-PIPELINE
This project addresses the limitations of monolithic toll systems by designing a serverless, cloud-native AWS platform that processes live transactions and delivers automated, near-real-time analytics for actionable insights.

To overcome the challenges of inefficient and manual toll collection, this project proposes
a Toll Management System using AWS Serverless Data Pipeline that leverages cloud
computing and event-driven architecture for automated, scalable, and cost-effective toll
processing. Instead of relying on traditional on-premise servers or manual operations, the
system uses fully managed AWS services such as API Gateway, Lambda, and
DynamoDB to perform toll operations in real time. This approach ensures faster response
times, reduced infrastructure costs, and minimal maintenance while maintaining data
integrity and reliability.
The system is developed using Node.js for the backend, with AWS Lambda functions
handling CRUD operations for vehicle data and toll deductions. Vehicle details and balances
are stored securely in DynamoDB, and all updates are captured through DynamoDB
Streams, which automatically trigger analytics processing in another Lambda function.
Processed toll transaction data is then stored in an Amazon S3 Data Lake, providing a clean
and structured dataset for further analysis.
A static web-based frontend is hosted on Amazon S3 and connected to the backend
through API Gateway. Users can register vehicles, view balances, and perform toll
deductions seamlessly through the interface. Additionally, the stored data in S3 can be
queried using AWS Athena or visualised in Amazon QuickSight to generate insightful
analytics dashboards showing vehicle traffic, toll collections, and usage trends. This
serverless solution effectively combines automation, scalability, and real-time analytics to
modernise toll management and enhance operational efficiency.

METHODOLOGY

The development of the Toll Management System using AWS Serverless Data Pipeline
follows a systematic, cloud-based approach. The process begins with setting up a
DynamoDB table to store vehicle information such as ID, number, type, and balance, along
with a Global Secondary Index (GSI) for quick lookups. Sample data is inserted to
simulate toll operations, ensuring a ready environment for testing and validation.
Next, AWS Lambda functions are developed to handle all backend logic. The main
function, vehicles-api, performs CRUD operations for vehicle registration, retrieval,
updates, and deletions. This function is integrated with API Gateway, which exposes
RESTful endpoints for frontend communication. Every balance update in DynamoDB
triggers a DynamoDB Stream, invoking a secondary Lambda function, process-tollstream,
that processes transaction data and stores structured JSON files in an S3 Data Lake
for analytics.
The frontend is a static website hosted on Amazon S3, connected to the backend through
the API Gateway. It allows users to register vehicles, deduct tolls, and view real-time
status updates. The analytics data stored in S3 can be further explored using AWS Athena
or visualized in Amazon QuickSight to display toll trends and vehicle statistics. This
methodology demonstrates an event-driven, fully serverless architecture that ensures
automation, scalability, and real-time toll data analysis.

RESULT

The Toll Management System using AWS Serverless Data Pipeline successfully
automates the entire toll collection and processing workflow with high efficiency and
reliability. By leveraging AWS Lambda, API Gateway, and DynamoDB, the system
performs vehicle registration, toll deduction, and data updates in real time without the need
for traditional servers. Testing confirmed seamless interaction between all components—
vehicle data was accurately stored in DynamoDB, transactions triggered stream events
instantly, and processed analytics were successfully stored in the S3 Data Lake. The system
demonstrated quick response times, consistent data integrity, and reliable performance
across multiple operations.
The frontend interface, hosted on Amazon S3, allows users to register vehicles, view
balances, and perform toll deductions easily through API integration. Each action triggers
the backend pipeline, providing real-time feedback on transaction success and updated
vehicle balances. The event-driven workflow ensures that every toll deduction automatically
generates structured analytics data, enabling effective monitoring of traffic and toll
collection trends.
Overall, the project validates the effectiveness of a serverless, event-driven architecture
for modern toll management. It demonstrates how AWS services can be integrated to
achieve automation, scalability, and cost efficiency while maintaining real-time analytics
capabilities. These results confirm that cloud-based solutions can significantly enhance
operational transparency and pave the way for future intelligent transportation systems.
