# Postman collection integration using Jenkins and visualization using Newman reporter


![Postman](https://miro.medium.com/max/1400/1*9gyOFOn482a5XKULrnS1-w.png)

It’s been a long time since I wrote my last article.
Better late than never. I am back with one more article
where we discuss how can we execute postman collection
in CLI, how to integrate postman collection to Jenkins
and also discuss how can we create one nicely displayed
HTML report with the collection results. So let’s start
our journey without wasting much time.

There are different ways to run your postman collection.
One way is to run the collection directly from the
postman UI and another way is using the Newman tool.


Newman is a command line tool to run your postman
collections. Newman allows user to run the postman
collections directly through command line interface.
Newman is built on Node.js. So to download the Newman,
users should have Node.js installed on their machine.
Once Node.js is installed, users can download the Newman
with below command.

```bash
# Newman Installation
npm install -g newman
```

Newman provides different ways to run the postman
collection. Refer following for the same:
1) Userscan export the collection as JSON file and later Newman can use that file as argument to run the collection
2) Users can get the collection URL from postman and later Newman can use that URL as argument to run the collection

Refer below GIFs to export the collection and get the collection URL:

![Exporting Collection](https://miro.medium.com/v2/resize:fit:640/1*aRqQYQH5mUc9VdaR2BLLkQ.gif)

![Getting Collection URL](https://miro.medium.com/v2/resize:fit:640/1*l-I_UpBRTi-10DItq6wuIA.gif)


## Newman Usage

Execute below command to use exported JSON to run the collection:

```bash
newman run mycollection.json
```

Execute below command to use public URL to run the collection:

```bash
newman run https://www.postman.com/collections/cb208e7e64056f5294e5
```

Output after the command execution will have PASS/FAIL
status for each API request. It will have the summary
table of the execution result. Refer below screenshot
for the output sample:

![Sample Output](https://miro.medium.com/v2/resize:fit:2880/1*fcglMPLTkXQrndgTghRcSw.png)

![Sample Output](https://miro.medium.com/v2/resize:fit:2880/1*X3JkCruS9DL9SPpJL5NPjw.png)

Your collection might contain environment variables. To
run Newman with the environment, users can export the
environment from postman and later use that exported
environment file with -e flag.

Refer below command:
    
```bash
newman run https://www.postman.com/collections/cb208e7e64056f5294e5  -e environment.json
```
Refer below GIF to export the environment:

![Exporting Environment](https://miro.medium.com/v2/resize:fit:640/1*YehkX3pHxpACoYVYi7dWcw.gif)

Refer more options at [learn postman](https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/)

Till now we discussed on how can we run postman
collection using Newman. Now, we will discuss how can we
integrate the postman collection with Jenkins.
Traditionally we get the console output in table view.
Results in a good HTML report is always a better option
than console output. Found one node library which does
that pretty well. It is called newman-reporter-htmlextra
which is also built on Node.js. If node is already
installed on your machine, you can download the library
using below command:


## HTMLextra Report Installation

```bash
npm install -g newman-reporter-htmlextra
```

Once the library is installed, you can use that library
to generate reports. You can use -r flag with the
htmlextra as argument with newman command to generate
the report.

## HTMLextra Report Usage

```bash
newman run collection.json -r htmlextra
```

ote: Report will be generated in the directory from where you have executed the command.

Sample report will look like below screenshot.

![Sample Report](https://miro.medium.com/v2/resize:fit:700/1*rHYEQjnY_v_DHDKzuJ_q2Q.png)

Refer [newman-reporter-htmlextra](https://www.npmjs.com/package/newman-reporter-htmlextra) to know more options and other details of the library.

## Jenkins Job Setup

We will configure Jenkins job with 2 simple steps. Refer below steps for the same:
1) Add the build step with execute shell option. Enter newman command that we want to be executed to run postman collection.
    
    ```bash
    newman run collection.json -r htmlextra — reporter-htmlextra-export “newman/report.html”
    ```
Note: Report will generate under newman/report.html.

2) Next step is post-build actions. We will add Publish HTML reports post-build actions to publish HTML reports that your build generates to the job and build pages.

Refer below GIF to configure the whole Jenkins job.

![Jenkins Job Setup](https://imgur.com/or2Wukz)
