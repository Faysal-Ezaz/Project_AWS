<h1>AWS SQS hands-on</h1>  
<ol>
  <li>We go to AWS Console and Search for SQS</li>
  <li>Under SQS, we get the Topic Name, Enter topic name (<b>demo sns</b>). </li>

  <li>The <i>Create Topics</i> tab opens up, and we need to do the following.
    <ul>
      <li>For SNS we will leave all the other options on default.</li>
      <li>Then we click on <b>"Create Topic"</b>.</li>
    </ul>
  </li>

  <li> Then we come back to the main menu with our newly created (demo-sns) topic open. Then we have to do the following: 
    <ul>
      <li>Under demo-sns 'topic', click on Create Subscriptions:
        <ul>
          <li>For Topic ARN we are not required to do anything.</li>
          <li>Under Protocol, we have to choose an endpoint. i,e, it is the target.</li>
          <li>Then we enter the mail, email sservice was chosen as the target service.</li>
          <li>Then we click on create Subscription.</li>
          <li>A mail will be sent to the mail id, open it up and click on confirm subscription.</li>
        </ul>
      </li>
      <li>Practice sending message to the SNS topic: 
        <ul>
          <li>Click on "Publish message"</li>
          <li>Under Subject, name as "Demo Subject Line"</li>
          <li>Under message body,
            <ul>
              <li>"Identical payload" for all delivery for protocols.</li>
              <li>Enter message "Hello World" in terms of payload.</li>
              <li>Click on 'Publish Message'.</li>
            </ul>
          </li>
          <li>All the subscribers have received the message.</li>
        </ul>
      </li>
    </ul>
  </li>
  <li>To delete all the services:
    <ul>
      <li>We directly go to topics and select the one that we need to delete.</li>
      <li>Then, we open dashboard, click on the Subscriptions and delete the Subscription. 
    </ul>
  </li>
</ol>
