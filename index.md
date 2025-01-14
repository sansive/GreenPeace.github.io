---
layout: page
title: GreenPeace
subtitle: Faced with the climate emergency, speeches are not enough. 
output: html_document
cover-img: /assets/green-headlines.png
use-site-title: true
---

Dear Jennifer Morgan,

We want to thank you for letting us take on the challenge of better understanding the climate change landscape in the news. We believe that this data-driven approach can complement Greenpeace’s existing, more qualitative, methods and provide you with a coherent understanding of how the climate change discourse has evolved within the news. After three months of extensive research, we have reached the point where our findings will bring a tangible improvement to Greenpeace’s core mission: <core mission>.

## Goal
We want to create a productive awareness campaign about Climate Change. Thanks to the “Quotebank" database and open accessible data, our goal is to understand how the Climate Change topic has been spreaded through society in the last 5 years. In other words, when do people talk about it, who and on which platform? 

This article should serve as a head start for people searching how to target a Climate Change awareness campaign.


## Research Questions
During this article we will answer to the following questions:
* What were the topics and events that triggered conversation about Climate Change?
* Who are the main personalities driving the Climate Change topic?
* Are there media spreading the Climate Change subject? Is Climate Change "IN"?

## How we did it
We built our dataset from Quotebank, an open corpus of 178 million quotations attributed to the speakers who uttered them, extracted from 162 million English news articles published between 2008 and 2020. Additionally, we filtered the dataset and took only Climate Change related quotes.

We wanted to have as much data as possible to have an accurate analysis. The final Climate Change database is composed of: 


       Quotes                            Speakers                            Domains  
       260'924                            178'716                             7'782 


{: .box-note}
**Side Note:** There is a linear relationship between quotes and articles in online newspapers. Thus if we interchange quotes and articles, don't be surprised.
       
#### Let’s check now what the data has to say... 

<center> <h1>Is conversion about Climate Change constant over time?</h1> </center>

### Frecuency of Climate Change Quotes 
Let's start really brodly by analysing the evolution of climate change quotes in the last 5 years. 

<div class="flourish-embed flourish-chart" data-src="visualisation/8162290"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
 **Figure 1:** Number of quotes about Climate Change over time.  
       
The majors local and global peaks observed on the graph are the following: 

* November 2015 : According to WikiTimeline "Pope Francis encourages bishops from around the world to sign an appeal to world leaders, meeting in Paris next month, for crucial climate change talks." 
* Juin 2017 : Accordint to WikiTimeline the 1st of June "United States withdrawal from the Paris Agreement"
* Juin 2019:  Accordint to WikiTimeline "The House of Representatives of the Netherlands passes the final bill of the climate agreement. The goal of the accord is to have the level of greenhouse gasses in the atmosphere in 2030 the same as the level of greenhouse gasses in the atmosphere in 1990."
* September 2019:  According to WikiTimeline "Millions of young people take to the streets and numerous businesses worldwide go on strike days before the UN Climate Summit, demanding that further action be taken to confront climate change." 
       
Can we trust our guts? Let's find out. 
      
### Main Topics of Climate Change 
 
{: .box-note}
**Side Note:** Thanks to LDA we are aible to determine different topics in Climate Change Quotes! 
 
<div class="flourish-embed flourish-hierarchy" data-src="visualisation/8156209"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
 **Figure 2:** Topics generated by LDA algorithme with constraint: 30 topics to find.
       
What we observe? 
       
By understanding the issues that are intrinsic to climate change, we will be able to see which issues have been raised at which time.
       
### Topic Trough time

HEAT MAP
**Figure 3:** Topics generated by LDA algorithme with constraint: 30 topics to find. 
       
This could already give us a hint of topics observe in the peaks. 
       
### Is there an increasing tendency on Climate Change quotes frequency? 
       
When performing a linear trend curve, we observe a minimal increase of quotes per month, not statistically at all. 

       


<center> <h1>Who talks about Climate Change? </h1> </center>

Let’s now look into people that are most quoted in relation to Climate Change from the past 5 years.
_Are the most quoted people for Climate Change talk **only** about Climate Change?_

<div class="flourish-embed flourish-cards" data-src="visualisation/8165651"><script src="https://public.flourish.studio/resources/embed.js"></script></div> 
 **Figure 4:** Top most quoted speaker. 

It seems that is not the case, but still it is a hot topic! Indeed, in adverage a third of speakers' quotes are about Climate Change. 

*Do you see a trend between most quoted speakers?* 
       
You want to say that Politics speakes more about Climate change, right? 
But if we observe Occupations of most quoted speakers about Climate Chnage over top occupation of most quoted speakers we have the following graph: 
<div class="flourish-embed flourish-hierarchy" data-src="visualisation/8163210"><script src="https://public.flourish.studio/resources/embed.js"></script></div>

Politics are not significant quoted about only Climate Change!     

Ok, this wasn't faire, what about gender? Is there a gender that is quoting more climate change? 
<div class="flourish-embed flourish-chart" data-src="visualisation/8165365"><script src="https://public.flourish.studio/resources/embed.js"></script></div>
**Figure 5:** Top occupations among speakers. 
       
Yes, it seems than Man are more quoted, but it is also the case in the overall dataset, surprised? I don't think so? 
Ok, this wasn't faire, what about Nationality? 
       
       
And Religion?       
       

       


Ok, so in conclusion if you are a politic with this and this age nationality and , be sure that you will be hearded. 

<center> <h1>What are the medias that publish the most Climate Change related topic?</h1> </center>

#### Connecting speakers and sites in an **al-gore-itmic embedding**.
       
Understanding climate change related quotes requires uncovering both the speakers and where the quote takes place. We develop a high-fidelity embedding of news sources where similarity is measured by commonality in who the site quotes. **Two sites are then close if they share a lot of speakers, and far away if they have little similarity in the speakers**. Simply put, this embedding is created through a latent semantic analysis (PCA on the tf-idf matrix), where the documents are sites and words are speakers. 

The embedding is capable of effectively clustering news sites into coherent groups. The clusters are both based on topical similarity (fashion, sports, climate, news, and finance) and geographic proximity, which are captured in the KMeans clustering we do on the space. Here we include a small video of the embedding, but the full embedding can be played around with [here]('https://projector.tensorflow.org/?config=https://gist.githubusercontent.com/vminvsky/45b24d87668ee39c42ed431e2a510696/raw/a89a3cb6d46d9baf7ae5c6001ee07613f1c94353/quotebank_embedding). 

<a href="https://gifyu.com/image/SSN8w"><img src="https://s10.gifyu.com/images/embedding_video.gif" alt="embedding_video.gif" border="0" /></a>

Now Jennifer, at this point you may be wondering, "what the global warming does an embedding have to do with climate change?" It is better to show you than tell you why we used this representation. Below we include a few analyses that the embedding permitted us to conduct, that would not have been possible without it. 

#### Developing climate topic vectors
After embedding each of the news sites, we turn to the embedding of concepts to track the similarity between the sites and concepts. A concept embedding is an attempt to vectorize linguistic concepts in the speaker embedding. The concepts we aimed to embed were climate change, and various climate change subtopics found from LDA. Each concept is calculated as the weighted average of the communities that share climate change related quotes. 

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th>Website</th>
      <th>domain</th>
      <th>climate_projection</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>295</th>
      <td>yaleclimateconnections.org</td>
      <td>0.890519</td>
    </tr>
    <tr>
      <th>303</th>
      <td>climatecentral.org</td>
      <td>0.884039</td>
    </tr>
    <tr>
      <th>345</th>
      <td>mongabay.com</td>
      <td>0.830271</td>
    </tr>
    <tr>
      <th>318</th>
      <td>greenbiz.com</td>
      <td>0.830028</td>
    </tr>
    <tr>
      <th>300</th>
      <td>desmogblog.com</td>
      <td>0.829195</td>
    </tr>
    <tr>
      <th>239</th>
      <td>treehugger.com</td>
      <td>0.807636</td>
    </tr>
    <tr>
      <th>325</th>
      <td>blueandgreentomorrow.com</td>
      <td>0.804560</td>
    </tr>
    <tr>
      <th>323</th>
      <td>carbonbrief.org</td>
      <td>0.802666</td>
    </tr>
    <tr>
      <th>284</th>
      <td>theenergycollective.com</td>
      <td>0.800073</td>
    </tr>
    <tr>
      <th>278</th>
      <td>theclimategroup.org</td>
      <td>0.791573</td>
    </tr>
  </tbody>
</table>

### GS SCORE

One question we’re often tasked with at Greenpeace is to understand which issues related to climate change we need to focus on. Do we find a very specialized issue that will be sympathetic to a specific audience? Or should we try to be more general to rally larger support? Before we can even do this, however, we are required to **understand which issues are generally discussed, and which issues are highly specific**. To do this, we find the average cosine similarity to the center of mass for each topic in our embedding, and then find the average cosine similarity for all shares of the topic. A topic is widely shared if it is invoked in a lot of wide-ranging communities, and it is locally shared if it occurs in a very specific area of the embedding.  
       
       
       

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gs_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>society</th>
      <td>0.149831</td>
    </tr>
    <tr>
      <th>concern</th>
      <td>0.153984</td>
    </tr>
    <tr>
      <th>reduction</th>
      <td>0.155351</td>
    </tr>
    <tr>
      <th>power/footprint</th>
      <td>0.164052</td>
    </tr>
    <tr>
      <th>biodiversity</th>
      <td>0.167376</td>
    </tr>
  </tbody>
</table>
       
       
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>gs_score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>eurozone</th>
      <td>0.328310</td>
    </tr>
    <tr>
      <th>models</th>
      <td>0.316398</td>
    </tr>
    <tr>
      <th>tax/trade</th>
      <td>0.314999</td>
    </tr>
    <tr>
      <th>trump</th>
      <td>0.312403</td>
    </tr>
    <tr>
      <th>science</th>
      <td>0.276532</td>
    </tr>
  </tbody>
</table>

### Projecting concept vectors
Now that we know how general and specialist the topics are, we focused in on which sites care about which issues. When publishing or sharing our developments with specific news sites we need to know which audiences from which sites care about which aspects of climate change. This will allow us to focus in our information dissemination efforts to maximize the benefit the reader of the news site gets from our findings. We don’t want to speak the language of the reader, not in gibberish that’s likely to go over their head. 

Since each concept vector is projected in the same space as the actual newspapers, we can calculate the cosine similarity between the two vectors to measure alignment between the news site and the topic. Our findings align with what one would intuitively expect from this. When climate change is invoked, business sites are more likely to speak about trade and taxes, whereas international organizations like the UN focus on development and rising sea levels. 

However, one finding that surprised is the role that Trump played in driving climate change discussion across many news sites. While himself a known climate denier, Trump’s outbursts themselves dramatically increased the number of discussions that took place surrounding climate change. We find that HuffPost and Fox News are far more aligned to Trump’s topic, than other pressing climate concerns like the global south and environmental impacts. Further analysis is needed to understand whether this new form of discussion is beneficial, but if the maxim “all publicity is good publicity”, then increased exposure to climate change discussion, regardless of origin will help our cause. Below we feature a visual that includes the issue alignment on several key issues for seven sites.  


{% include plots/news_interests.html %}

### Connecting partisan scores to climate change issues
To begin, we quantify the difference between the climate change discussion and all quotes more broadly. This will shine a light on the context in which climate change quotes occur. We find that climate change related quotes are more likely to occur in newspapers on the left than the right, and that the far right is also has a propensity of bringing up climate change. 
       

<img src="/assets/plots/difference_plot.png" alt="difference plot" width="800" style="float:right"/>

       
Duncan Watts’ famous finding that while both the left and the right consume science, the science they consume differs, raises an important question in our analysis. While both the left and the right may talk about climate change (the left more), does the type of conversation about climate change differ between the groups. If so, this will let us better target the individual news, or alternatively, speak the language of the audience. 
To understand when the left and the right bring up climate change comments, we are required to analyze the textual level, falling back to our favourite LDA. Below we present a series of histograms of how different climate change topics differ along partisan lines. We find that when the right invokes climate change, it is most often brought up in the context of business, trade, or tax. In contrast, the left tends to focus more on development, rising sea levels, and temperature. 

       
<img src="/assets/plots/topic_distribution.png" alt="topic distribution" width="800" style="float:right"/>


### Polarization
Statically, left leaning newspaper sites tend to speak about climate change more than right leaning sites. This result, while not surprising, does add to the increasing evidence we here at Greenpeace have found about the role politics plays in forming the views of the people. To better understand this dynamic we studied how different sites have used climate change in their discussions over time to answer the question of if climate change discussion has been polarized over the years. Ever since 2015, left-leaning news sites have been responsible for most of the discussion surrounding climate change, whereas the far-right sites quote an increasingly small portion of speakers who talk about climate change. The proportions have remained surprisingly static over time, with the left dominating the discussion. This is good news to us since it supports the argument that the discussion surrounding climate change is not becoming polarized. And, in fact, the centre sites are increasingly representing the discussion surrounding climate change. 

{% include plots/polarization.html %}


<center> <h1>Conclusion and Implication</h1> </center>

{: .box-note}
**Side Note:** If you encounter climate skeptics in your way, you will find useful arguments [here](https://350.org/fr/).  
       
In this report we presented our analysis of climate change in the media. We find that climate change discussion has been remained fairly static over the last five years, seeing a minor rise in the end of 2019 into 2020. Key events like the Paris Agreement and Trump’s language drive public discussion around the topic, and the frequency of quotes increases dramatically. 
PROVIDE A CONCLUSION ON PEOPLE IF IT OCCURS
Finally, we developed an embedding technique to deepen our understanding of climate change in the news. This embedding technique provided us a new lens for studying climate change in the news, where each site was represented as a point in a high-dimensional vector space with two sites close together if they share a lot of the same speakers. This embedding was used to augment our understanding of the topics that were discussed and study how sites formed distinct clusters.
