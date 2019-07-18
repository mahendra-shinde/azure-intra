## Fork Git repository
https://github.com/Azure-Samples/applicationinsights-web-sample1

1. Create new Web Application in Azure
        Platform : Windows
        Service Plan: S1
        Runtime Environment: Node 8.5

2. Click on "Browse" button to test website.

3. Goto "Deployment Center" > Choose "GitHub" > Authorize / Continue

4. Choose GitHub Organization (Your GitHub Account).
5. Choose Repository "applicationinsights-web-sample1"
6. Choose "master" branch
7. Next > Choose "Build Service" > Finish
8. Click on "Browse" button to test newly deployed website.
9. Add "/test.html" in URL (At addressbar) to view test page.
10. Goto Web App > Application Insights > View Application Insights Data
    Select & Copy "Instrumentation Key"
11. Goto your GitHub Repository > edit file "test.html"
    On line #9, find following statement:
         instrumentationKey:"INSTRUMENTATION_KEY"
    Now, replace "INSTRUMENTATION_KEY" with Key copied from provious step.
    The result should be:
         instrumentationKey:"fafe41af-b477-42a7-95c4-becc5d96f9b6"

    NOTE: Java, DotNet & Python Application can Auto-Detect Instrumentation Key
          from App Service Configuration.

12.  goto deployment center to view the recent deployment
