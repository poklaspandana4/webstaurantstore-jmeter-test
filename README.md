WebstaurantStore Outlet Product Pages – JMeter Performance Test

Overview
This project presents a performance test conducted using Apache JMeter to evaluate the responsiveness and stability of WebstaurantStore Outlet product pages.
The test simulates user traffic by sending requests to randomly selected outlet product pages at a controlled rate.

Test Objective
•	Execute load test at maximum 5 requests per minute (RPM)
•	Duration: 15 minutes
•	Use randomized sampling of outlet product pages
•	Analyze performance metrics and system behavior under steady load

Test Design
Configuration
•	Tool: Apache JMeter
•	Threads: 1 user
•	Duration: 900 seconds (15 minutes)
•	Throughput: 5 RPM using Constant Throughput Timer
Workflow
•	Outlet page (/outlet.html) is requested once
•	Product links are extracted using Regular Expression Extractor
•	Random product page is selected per iteration using JSR223 PreProcessor
•	HTTP requests are sent to selected product pages
Randomization Approach
•	Extracted all product links (productLinks_*)
•	Used Groovy script to randomly select a product URL each iteration
•	Ensures realistic traffic simulation across multiple product pages


Metrics Explained
•	Average Response Time: Mean time taken to process requests
•	Minimum / Maximum: Fastest and slowest responses observed
•	Standard Deviation: Variability in response times
•	Throughput: Requests processed per minute
•	Error %: Percentage of failed requests
•	Received KB/sec: Data received from server

Performance Assessment
The system handled the configured load successfully.
•	No errors were observed during execution
•	Throughput remained consistent at ~5 requests per minute
•	Response times were stable with acceptable variability
•	The application demonstrated reliable performance under steady low-load conditions
This indicates that outlet product pages can efficiently handle sustained traffic at the tested rate.

How to Run
1.	Install Apache JMeter
2.	Open command prompt
3.	Navigate to project directory
4.	Run: jmeter -n -t webstaurant_test.jmx -l results.jtl -e -o report
5.	Open: report/index.html

Project Structure
├ webstaurant_test.jmx
├ results.jtl
├ report/
  └── index.html
└── README.md


Conclusion
The test confirms that WebstaurantStore outlet product pages maintain stable performance under controlled traffic conditions with randomized access patterns.

Author
Spandana Pokla