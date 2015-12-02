---

title: "Get Single Job"
weight: 30

menu:
  main:
    name: "Get"
    identifier: "rest-api-job-get"
    parent: "rest-api-job"
    pre: "GET `/job/{id}`"

---


Retrieves a single job according to the `Job` interface in the engine.


# Method

GET `/job/{id}`


# Parameters

## Path Parameters

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>id</td>
    <td>The id of the job to be retrieved.</td>
  </tr>
</table>


# Result

A JSON object corresponding to the Job interface in the engine.
Its properties are as follows:

<table class="table table-striped">
  <tr>
    <th>Name</th>
    <th>Value</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>id</td>
    <td>String</td>
    <td>The id of the job.</td>
  </tr>
  <tr>
    <td>jobDefinitionId</td>
    <td>String</td>
    <td>The id of the associated job definition.</td>
  </tr>
  <tr>
    <td>dueDate</td>
    <td>String</td>
    <td>The date on which this job is supposed to be processed.</td>
  </tr>
  <tr>
    <td>processInstanceId</td>
    <td>String</td>
    <td>The id of the process instance which execution created the job.</td>
  </tr>
  <tr>
    <td>executionId</td>
    <td>String</td>
    <td>The specific execution id on which the job was created.</td>
  </tr>
  <tr>
    <td>processDefinitionId</td>
    <td>String</td>
    <td>The id of the process definition which this job belongs to.</td>
  </tr>
  <tr>
    <td>processDefinitionKey</td>
    <td>String</td>
    <td>The key of the process definition which this job belongs to.</td>
  </tr>
  <tr>
    <td>retries</td>
    <td>Number</td>
    <td>The number of retries this job has left.</td>
  </tr>
  <tr>
    <td>exceptionMessage</td>
    <td>String</td>
    <td>The message of the exception that occurred, the last time the job was executed. Is null when no exception occurred.</td>
  </tr>
  <tr>
    <td>suspended</td>
    <td>Boolean</td>
    <td>A flag indicating whether the job is suspended or not.</td>
  </tr>
  <tr>
    <td>priority</td>
    <td>Number</td>
    <td>The job's priority for execution.</td>
  </tr>
</table>


# Response Codes

<table class="table table-striped">
  <tr>
    <th>Code</th>
    <th>Media type</th>
    <th>Description</th>
  </tr>
  <tr>
    <td>200</td>
    <td>application/json</td>
    <td>Request successful.</td>
  </tr>
  <tr>
    <td>404</td>
    <td>application/json</td>
    <td>Job with given id does not exist. See the <a href="{{< relref "reference/rest/overview/index.md#error-handling" >}}">Introduction</a> for the error response format.</td>
  </tr>
</table>


# Example

## Request

GET `/job/aJobId`

## Response

    {
      "id": "aJobId",
      "dueDate": "2013-07-17T17:00:00",
      "processInstanceId": "aProcessInstanceId",
      "executionId": "anExecutionId",
      "retries": 0,
      "exceptionMessage": "An exception Message",
      "suspended": false,
      "priority": 10
    }