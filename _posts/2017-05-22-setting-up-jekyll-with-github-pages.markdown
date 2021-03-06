<h2> Intro: </h2>
Well, that was painful, for a newbie... but then again, no pain...no gain! Cheesy lines aside, Jekyll is not as intuitive as it might seem from a beginners perspective. The documentation is heavy on jargon and there are multiple resources on both GitHub Pages and Jekyll, which have differing setup procedures and can be overwhelming. In fact, looking back on the other side it was incredibly easy, but you can easily get overwhelmed with all the information. They do point to a great resource in Jonathan McGlone's <a href= "http://jmcglone.com/guides/github-pages/"> Creating and Hosting a Personal Site on GitHub </a>. Although a great resource that really allows you to personalize your page, you can bypass this tutorial to get a simple blog up and running in a matter of minutes using this quick setup guide that I have written below with the help of documentation from GitHub Pages, Jekyll, and McGlone's tutorial. 

<h2> Setting Up GitHub Pages: </h2>
GitHub nails it with simplicity when they explain <a href="https://pages.github.com"> how to create a GitHub page </a>. My personal experience is that GitHub tries to take the perspective of someone who has absolutely no experience and they will guide you along the path. Highly recommend following the link to setup your page and meet me back here for the Jekyll setup.

<h2> Setting Up Jekyll: </h2>
When it comes to the Jekyll documentation there is a lot of additonal info that I would say a beginner need not look at for the sake of your own sanity. I still recommend looking at the documentation once you feel comfortable, because there are some great tools to curate your blog. So, to bypass the documentation follow the following steps:

Step 1: 
You need to make sure you have the following on your computer: <a href="https://jekyllrb.com/docs/installation/"> Ruby 2.0 or greater, RubyGems, GCC, and Make </a>.

Step 2: 
Now in the terminal you want to install Jekyll and Bundler Gems using the following command: gem install jekyll bundler

Step 3: 
You'll need to locate where you cloned your repository from GitHub and traverse into that directory using the command line. Once inside the cloned repository folder you want to enter the following command to create a new Jekyll site: jekyll new myblog

You can choose any name for the directory that will hold your jekyll files by changing the "myblog" portion to anything you want. 

Step 4: 
After you have entered the command in Step 3, Jekyll will populate the directory for you with necessary files. In contrast, McGlone's tutorial makes a majority of these folders one by one. It is a bit tedious, but it will really give you a strong understanding of how important it is in Jekyll to have all your directories in the correct order with correct names. Now, the only thing you have to do is traverse into your "myblog" directory.

Step 5: 
Once in the "myblog" directory, you can enter the following command to preview your new blog: bundle exec jekyll serve

After entering the command you can open up a web browser and enter the server address given to you in the command line.

<h2> Where To Go From Here? </h2>
Well, first things first you can open config.yml in your "myblog" directory and you can make some basic changes, such as your email, twitter handle, or title of your blog. It will be clear where you can make these changes given the setup of the document. Stay tuned to my next post on .... you guessed it POSTING!