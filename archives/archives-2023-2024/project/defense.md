# Defense

Teams will have 2 periods to prepare (from 08:00 to 09:35) on the day of the defense.

### Time schedule

| Slot          | Activities            | DevOpsTeam                              |
| ------------- | --------------------- | --------------------------------------- |
| 08.00 - 09.35 | Final setup           | All                                     |
| 09.35         | Shutdown docker hosts | All                                     |
| 10.00 - 10.40 | Defense               | <p>Mac-os<br>Megatron</p>               |
| 10.50 - 11.50 | Defense               | <p>Linux<br>Les-jaquiers<br>Wintard</p> |

{% hint style="info" %}
While the teams are not defending, they begin their end-of-year work (archiving documents, and cleaning up the classroom, keyboards, and screens).
{% endhint %}

### Criteria to pass during the defense

#### Prerequisites

During the entire procedure, we ensure that network components such as the SSH server, reverse proxy, security rules and the entire infrastructure hosting the private network are operational and unaltered.

All api client requests are made from outside the integration infrastructure, using the reverse proxy (not an ssh tunnel).

### Scenarios - Nominal cases

#### Start up

| Given                                                  | When                            | Then                      |
| ------------------------------------------------------ | ------------------------------- | ------------------------- |
| <p>The docker host has just </p><p>been restarted.</p> | A get "all" query is performed. | The api gateway responds. |

#### Put route validation

| Given                      | When                    | Then                                                                                                 |
| -------------------------- | ----------------------- | ---------------------------------------------------------------------------------------------------- |
| Infra in normal operation. | Performing a put query. | The PUT method replaces all current representations of the target resource with the request payload. |

#### Post route validation

| Given                      | When                     | Then                                                                                                                        |
| -------------------------- | ------------------------ | --------------------------------------------------------------------------------------------------------------------------- |
| Infra in normal operation. | Performing a post query. | The POST method submits an entity to the specified resource, often causing a change in state or side effects on the server. |

#### Delete route validation

| Given                      | When                                            | Then                                              |
| -------------------------- | ----------------------------------------------- | ------------------------------------------------- |
| Infra in normal operation. | Performing a delete query on existing resource. | The DELETE method deletes the specified resource. |

### Scenarios - Exception handling - normal operation

| Given                      | When                                                | Then                                            |
| -------------------------- | --------------------------------------------------- | ----------------------------------------------- |
| Infra in normal operation. | Performing a get "all" query on non-existent route. | A code and an appropriate message are returned. |

| Given                      | When                                          | Then                                            |
| -------------------------- | --------------------------------------------- | ----------------------------------------------- |
| Infra in normal operation. | Perform a delete request on an absent object. | A code and an appropriate message are returned. |

### Scenarios - Exception handling - abnormal operation

| Given                                                                                  | When                          | Then                                            |
| -------------------------------------------------------------------------------------- | ----------------------------- | ----------------------------------------------- |
| The infrared operates normally except for the db micro service, which is switched off. | Performing a get "all" query. | A code and an appropriate message are returned. |

{% hint style="info" %}
Do not forget to restart the db microservice
{% endhint %}

| Given                      | When                                     | Then                                       |
| -------------------------- | ---------------------------------------- | ------------------------------------------ |
| Infra in normal operation. | Any http-verb microservice is restarted. | The state of the database is not impacted. |
