+++
title = "R-Code"
weight = 20
draft = false
+++

{{< figure class="image main" src="/images/pic02.jpg" >}}

<p>Before anything you need to retrieve your data, for example.</p>

<p> SELECT playerID,sum(HR) AS career_HR ,sum(SO) AS career_SO FROM Batting GROUP BY playerID HAVING sum(HR)</p>

<p>save as a result</p>

<p>We start our plotting of the data by entering this code, using the initial ggplot(), then adding with a + sign.</p>

<p> ggplot()+ <p/>
  <p>geom_point(data=result,aes(x=career_SO,y=career_HR),size=3,color=red)+</p>
  
  <p>ggtitle("career strikeouts vs homeruns for great hitter")+</p>
    
  <p>xlab("carrer strikeouts")+ylab("career homeruns")</p>

