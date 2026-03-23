# WebstaurantStore Outlet Product Pages – JMeter Performance Test

## Overview
This project contains a performance test executed using Apache JMeter to evaluate the responsiveness and stability of WebstaurantStore outlet product pages.

The test simulates user traffic by sending requests to randomly selected outlet product pages at a controlled rate.

---

## Test Objective
- Execute load test at a maximum of **5 requests per minute (RPM)**
- Run the test for **15 minutes**
- Use **randomized sampling** of outlet product pages
- Analyze performance metrics and system behavior under steady load

---

## Test Design

### Configuration
- Tool: Apache JMeter
- Threads: 1 user
- Duration: 900 seconds (15 minutes)
- Throughput: 5 RPM using Constant Throughput Timer

### Workflow
- Outlet page (`/outlet.html`) is requested once
- Product links are extracted using a Regular Expression Extractor
- A random product page is selected per iteration using a JSR223 PreProcessor
- HTTP requests are sent to the selected product pages

### Randomization Approach
- All product links are extracted (`productLinks_*`)
- A Groovy script selects a random product URL for each iteration
- This ensures realistic and varied traffic across multiple product pages

---

## Metrics Explained
- **Average Response Time**: Mean time taken to process requests
- **Minimum / Maximum Response Time**: Fastest and slowest responses observed
- **Standard Deviation**: Variability in response times
- **Throughput**: Requests processed per minute
- **Error %**: Percentage of failed requests
- **Received KB/sec**: Amount of data received from the server

---

## Performance Assessment
- The test ran successfully for the full duration
- No errors were observed during execution
- Throughput remained consistent at approximately 5 requests per minute
- Response times were stable with acceptable variation across requests
- The system handled the load without any noticeable degradation

This indicates that the outlet product pages can efficiently handle steady low-volume traffic.

---

## How to Run

1. Install Apache JMeter
2. Open command prompt / terminal
3. Navigate to the project directory
4. Run the following command:

```
jmeter -n -t webstaurant_test.jmx -l results.jtl -e -o report
```

5. Open the generated report:
```
report/index.html
```

---

## Project Structure
```
webstaurant_test.jmx
results.jtl
report/
  └── index.html
README.md
```

---

## Conclusion
The test confirms that WebstaurantStore outlet product pages maintain stable performance under controlled traffic conditions with randomized access patterns.

---

**Author:** Spandana Pokla
