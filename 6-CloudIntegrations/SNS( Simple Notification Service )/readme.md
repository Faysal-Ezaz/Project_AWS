<h1><b>SNS</b>: Simple Notification Service</h1>
This is the second AWS service that helps us decouple our messages.  

In SNS, we use the <b>Pub/Sub</b> type of integration: 
<ul>
  <li>In PUB/SUB, we have an <b>SNS topic.</b> </li>
  <li>The <b>Buying service</b> will send the message to the <i>SNS topic.</i></li>
  <li>This SNS topic is smart enough to send notification via: 
    <ol>
      <li><b>Email</b></li>
      <li><b>Fraud Service</b></li>
      <li><b>Shipping Service</b> and</li>
      <li><b>SQS Queue</b></li>
    </ol>
  </li>
  <li>We can send directly into an http/https endpoints.</li>
  <li><b>Notification, Publish, Subscribers</b> are the keywords that refer to AWS SNS in the CP exam.</li>
</ul>  

SQS-HandsOn.md is the file where the hands on is stored. 
