Hello,  
This is a mini Project where I use AWS ELB and AWS ASG to create a highly scalable server.  

<h2>The concept behind this project is as follows:</h2>  
<ol>
  <li>Initially we create two EC2 instances.</li>
  <ul>
    <li>These two instances will act as the two servers.</li>
  </ul>  
  
  <li>We then setup the Application Load Balancer.</li>  
  <ul>
    <li>The ALB helps distribute the load between the servers.</li>  
    <li>The ALP is responsible for the health checkup of the instances.</li>
  </ul>  
  
  <li>We then setup Auto Scaling Group</li>  
  <ul>
    <li>This allows us to maintain a fixed no of instance at all times, increases/decreases the no of instances as and when required.</li>  
    <li>Creates new instances in real-time, if the previous instances are unhealthy.</li>
  </ul>
</ol>
