+++
title = " R Data Visualizing"
weight = 20
draft = false
+++


{{< figure class="image main" src="/images/pic02.jpg" >}}

## Intro

<p>Before anything you need to retrieve your data, for example.</p>

<p> SELECT playerID,sum(HR) AS career_HR ,sum(SO) AS career_SO FROM Batting GROUP BY playerID HAVING sum(HR)</p>

<p>save as a result</p>

<p>We start our plotting of the data by entering this code, using the initial ggplot(), then adding with a + sign.</p>

<p> ggplot()+ <p/>
  <p>geom_point(data=result,aes(x=career_SO,y=career_HR),size=3,color=red)+</p>
  
  <p>ggtitle("career strikeouts vs homeruns for great hitter")+</p>
    
  <p>xlab("carrer strikeouts")+ylab("career homeruns")</p>


## Histograms

Search for the data you want to plot and store as a result. 

 query<-"SELECT weight
 FROM Master"

 result<-sqldf(query)
      
Now format the graph with data drawn from result. Bins are the number of individual results. 

 ggplot()+
   geom_histogram(data=result,aes(x=weight),color="blue",fill="white",bins=50)
   +ggtitle("Body-weight distribution for Baseball players")
   
## Time Series

Pull data to be charted against time. Example, Babe Ruth homeruns.


 query<-"SELECT yearID,HR
 FROM Batting
 WHERE playerID='ruthba01'"

 result<-sqldf(query)

Points can be connected by adding a line, hence the geom_line command. Otherwise it's the same as scatterplot.

 ggplot()+
   geom_point(data=result,aes(x=yearID,y=HR))+
   geom_line(data=result,aes(x=yearID,y=HR))+
   ggtitle("Ruths Homeruns")+
   xlab("Year")+
   ylab("Homeruns")


    
    
    