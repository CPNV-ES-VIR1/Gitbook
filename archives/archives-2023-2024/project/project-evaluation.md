# Project evaluation

## Intention

This page is dedicated to the presentation of the project evaluation criteria. It's a “little survival guide” to be used just before delivery, to check that your deliverable is complete.

Please also read the delivery terms and conditions, which are an integral part of the evaluation.

## Evaluation criteria

### Integration environment (AWS)

| Description                                                  | Specifications                                                                                    |
| ------------------------------------------------------------ | ------------------------------------------------------------------------------------------------- |
| Micro-services attainability                                 | <ul><li>HTTP:8080</li><li>Only ms-api-gateway can be reached from the DMZ.</li></ul>              |
| Every route in the “api-rest-spring” project is functional.  | <ul><li>GET</li><li>PUT</li><li>(PATCH is not included)</li><li>POST</li><li>DELETE</li></ul>     |
| The gateway api handles a call pointing to an unknown route. | <p>A simple html page mentions “backend not found”.</p><p>The HTTP error code is appropriate.</p> |

### Repository



| Description        | Specifications                                                                                                                                                                                                                                                                                                   |
| ------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Mono repo approach | <ul><li><p>Each microservice is located in a separate directory.</p><ul><li>ms-api-gateway</li><li>ms-&#x3C;httpVerbe></li><li>ms-db</li></ul></li><li>Only code related to the microservice is present (separated by http verb).</li><li>A specific docker file is integrated into each microservice.</li></ul> |
| Docker practices   | <ul><li>Images and containers should be as light as possible.</li><li>Use volumes when it makes sense (data/log).</li></ul>                                                                                                                                                                                      |
| Readme             | <ul><li><a href="https://github.com/NGY-TEMPLATE/MASTER-README">Based on this template</a>.</li><li>All chapters have been correctly updated.</li></ul>                                                                                                                                                          |
| Wiki               | <ul><li>Steps 1 to 5 are carefully completed and ready to use.</li></ul>                                                                                                                                                                                                                                         |

## Delivery method

* The repository is up to date (code/issues/wiki).
* The integration instance is configured.
* A message (discord) is sent to the teacher to confirm delivery.

{% hint style="info" %}
Deadline: Friday 14-06-2024 / 6.00 pm
{% endhint %}
