---
title: Complaint-Driven Development
author: Sathya
type: post
date: 2014-02-20T06:40:24+00:00
url: /2014/02/20/complaint-driven-development/
categories:
  - Linked
tags:
  - IFTTT
  - "sathyabhat's blurblog"

---
<table style="border: 1px solid #E0E0E0; margin: 0; padding: 0; background-color: #F0F0F0" valign="top" align="left" cellpadding="0" width="100%">
  <tr>
    <td rowspan="2" style="padding: 6px;width: 36px;white-space:nowrap" width="36" valign="top">
      <img src="http://ift.tt/1eVbecN" style="width: 36px; height: 36px; border-radius: 4px;" />
    </td>
    
    <td width="100%" style="padding-top: 6px;">
      <b><br /> sathyabhat<br /> <a href="http://ift.tt/1mv4fBg">shared this story</a><br /> from <img src="http://ift.tt/1aejH8B" style="vertical-align: middle;width:16px;height:16px;" /> Coding Horror:</b>
    </td>
  </tr>
  
  <tr>
    <td>
      "Hey, remember all those brilliant ideas you had based on all that painstaking, detailed research you did in step 1? Turns out once you put them in front of actual honest-to-god real world users they were all … completely … wrong"</p> 
      
      <p>
        hehe, epic stuff. </td> </tr> </table> 
        
        <hr style="clear: both; margin: 0 0 24px;" />
        
        <p>
          If I haven&#8217;t blogged much in the last year, it&#8217;s because we&#8217;ve been busy building that <a href="http://ift.tt/14CiXKw">civilized discourse construction kit thing</a> I talked about.
        </p>
        
        <p>
          <a href="http://ift.tt/14CiXKw"><img alt="Civilized-discourse-construction-kit-inc" height="210" src="http://ift.tt/1h0Nozw" title="Civilized-discourse-construction-kit-inc" width="720" /></a>
        </p>
        
        <p>
          (Yes, that&#8217;s actually the name of the company. This is what happens when you put me in charge of naming things. <a href="http://ift.tt/1jNBNsv">Pinball machines</a>, people, what&#8217;s the difference? I&#8217;ve apologized to <a href="http://ift.tt/XGIeSn">Bill Budge</a> already.)
        </p>
        
        <p>
          So if you, like my investors, are wondering why this process took <a href="http://ift.tt/1dNKFGb">a whole entire year</a>, I should explain <b>how I build things</b>, or at least, how we built Stack Overflow and <a class="zem_slink" href="http://ift.tt/gBCjKc" rel="homepage" target="_blank" title="Stack Exchange Network">Stack Exchange</a> and now <a href="http://ift.tt/XKLo4G">Discourse</a>:
        </p>
        
        <ol>
          <li>
            Do a ton of detailed research on everything out there in your space. The successes: what are they getting wrong? The failures: what did they get right? Nobody should know more about the history of your area than you do. Have a story that makes sense, something you believe in, and more importantly, a story you can get others to believe in.
          </li>
          <li>
            Based on this research, assemble a team and build the minimum viable product that does something useful. If you need seed funding, this is the time to get it, so I hope you&#8217;re pretty good at all that stuff in step 1, and maybe famous too, and ideally already successful as well, otherwise you are screwed.
          </li>
          <li>
            Have your team and yourself start using that minimum viable product, every day, all day long. This is way more than mere software development: <i>it&#8217;s your whole life</i>. If you aren&#8217;t living in the software you&#8217;re building, each day, every day, all day … things are inevitably going to end in tears for everyone involved. And honestly, if I have to explain this to you, guess what? You&#8217;re screwed.
          </li>
          <li>
            Launch a brief closed beta and get feedback from your Special Internet Friends™ on what you&#8217;ve built so far. I know what you&#8217;re thinking: <i>Friends! Damn it! I knew those things would be useful to me at some point!</i> Listen to all their feedback with an open mind, no matter how dumb it probably is. Identify and fix everything major that comes up. Your product will still be terrible, but it&#8217;ll be slightly marginally <i>less</i> terrible, and you&#8217;ll now be slightly marginally less screwed than you otherwise would. (This is what we business experts call a &#8220;competitive advantange&#8221;. Look it up.)
          </li>
          <li>
            Rapidly get to a public launch. <a href="http://ift.tt/Y4Bo5Q">It will suck, but you will ship it anyway.</a> Don&#8217;t screw up the basic logistics of the launch. You know what I&#8217;m talking about because you&#8217;ve seen those sad launches. Don&#8217;t be those companies. Don&#8217;t be those teams. Don&#8217;t worry, you&#8217;ll have ample time to screw everything up royally in the next step.
          </li>
          <li>
            Hey, remember all those brilliant ideas you had based on all that painstaking, detailed research you did in step 1? Turns out once you put them in front of actual honest-to-god real world users they were <i>all … completely … wrong</i>. Now spend the next year doing nothing but fixing all your idiotic screwups and stupid mistakes.
          </li>
          <li>
            ???
          </li>
          <li>
            Profit!
          </li>
        </ol>
        
        <p>
          I never said it was a <i>good</i> plan for building software, but hey. Y&#8217;know. <a href="http://ift.tt/13oDjry">It&#8217;s a plan</a>.
        </p>
        
        <p>
          <img alt="I-love-it-when-a-plan-comes-wait" height="396" src="http://ift.tt/1h0NoPY" title="I-love-it-when-a-plan-comes-wait" width="528" />
        </p>
        
        <p>
          Each one of those steps is worthy of a blog entry in its own right, but it&#8217;s step six that I want to focus on today because in my opinion that&#8217;s the most critical part of this whole so-called &#8220;plan&#8221;. I like to refer to this phase as <b>complaint driven development</b>:
        </p>
        
        <ul>
          <li>
            Get your software in front of as many real users as you can.
          </li>
          <li>
            Listen to all the things they complain about. It will be… a lot.
          </li>
          <li>
            Identify and fix the top 3 things people keep repeatedly complaining about.
          </li>
          <li>
            Do it again.
          </li>
        </ul>
        
        <p>
          Now, we have a bit of an unfair advantage here because <a href="http://ift.tt/12lv9fV">Discourse is discussion software</a>. We host the discussions about all the things that are wrong with Discourse … on Discourse itself. But that&#8217;s also why we built an open source discussion platform in the first place – my deeply held belief that <b>actually listening to your customers should matter to your business</b>.
        </p>
        
        <p>
          Provided you&#8217;re equipped to listen to your customers, complaint driven development isn&#8217;t that difficult. Until you get deep into a multi-year design, you&#8217;re dealing with <b>fairly obvious, easy to fix complaints from users</b>. You just have to be out there listening. As Steve Krug says in <a href="http://ift.tt/1h0NoQ0">Don&#8217;t Make Me Think</a>:
        </p>
        
        <blockquote>
          <p>
            You don&#8217;t need to find all the problems. In fact, you&#8217;ll <i>never</i> find all of the problems in anything you test. And it wouldn&#8217;t help if you did, because of this fact:
          </p>
          
          <blockquote>
            <p>
              <i>You can find more problems in half a day than you can fix in a month.</i>
            </p>
          </blockquote>
          
          <p>
            You&#8217;ll always find more problems than you have the resources to fix, so it&#8217;s very important that you focus on fixing the most serious ones first. And three users are very likely to encounter many of the most significant problems related to the tasks that you&#8217;re testing.
          </p>
        </blockquote>
        
        <p>
          For example, we launched Discourse with a requirement that all topic titles and bodies be above a certain minimum character length, because we believe that extremely short posts and particularly titles aren&#8217;t conducive to actual conversation. Philosophically, this is an important default for us, because it strongly relates to our core mission of building software that helps cultivate meaningful conversation on the Internet.
        </p>
        
        <p>
          Unfortunately, users <i>hated</i> it:
        </p>
        
        <blockquote>
          <p>
            I think it&#8217;s especially annoying that there&#8217;s no indicator of how many characters that you have to type. You only have whether or not the &#8220;Reply&#8221; button is greyed out or not, and not all users will realize that it&#8217;s greyed out at first. Even then, if you click on the reply button it can bounce back on you if your post was mostly white-space. It&#8217;s annoying as hell.
          </p>
        </blockquote>
        
        <p>
          This was one of the consistently strongest bits of early feedback we got. So in the first 7 days after launch we quickly added a real time character count to the bottom right of the editor.
        </p>
        
        <p>
          <img alt="Discourse-character-count-1" height="186" src="http://ift.tt/1h0NlDT" title="Discourse-character-count-1" width="605" />
        </p>
        
        <p>
          I thought that&#8217;d help. It didn&#8217;t. The complaints about our terrible, awful, onerous default title and body length restrictions kept pouring in. So we experimented with ways to make these requirements clearer, by using a red border, or a red background on the fields.
        </p>
        
        <p>
          <img alt="Discourse-character-count-2" height="176" src="http://ift.tt/1h0NoQ2" title="Discourse-character-count-2" width="639" />
        </p>
        
        <p>
          <img alt="Discourse-character-count-3" height="176" src="http://ift.tt/1jNBPk1" title="Discourse-character-count-3" width="628" />
        </p>
        
        <p>
          We deployed all of the above and more. Complaints did not abate one bit. Now this is a configuration setting, if you want the minimum title and body length to be 1 character in your community, it&#8217;s trivially settable via a web browser in about 15 seconds. Frankly I started getting really sick of hearing all the complaints about the setting.
        </p>
        
        <p>
          So we finally deployed the nuclear option: <b>bouncy error dialogs right next to the field</b> as soon as they lose focus.
        </p>
        
        <p>
          <img alt="Discourse-character-count-4" height="172" src="http://ift.tt/1h0NlDX" title="Discourse-character-count-4" width="610" />
        </p>
        
        <p>
          Since that change, I haven&#8217;t heard word one about our terrible, onerous, awful default body and title character limit policies. Not one. Single. Complaint.
        </p>
        
        <p>
          So <i>that&#8217;s</i> the sort of thing we&#8217;ve been doing post launch, each day, every week, for the last year. <b>It took us a full year of complaint driven development to get to software worth using.</b> And even though we are now <a href="http://ift.tt/1aY2nLL">cautiously accepting customers</a>, we&#8217;re still practicing complaint driven development every day, just perhaps weighted a bit more heavily towards the people actually paying us money.
        </p>
        
        <p>
          It&#8217;s true that <a href="http://ift.tt/wStMrE">gathering feedback from your community can be hard work</a>. And 90% of the feedback you&#8217;ll get will be terrible for a whole host of reasons. It&#8217;s a lot easier to imagine some heroic expert swooping in and magically blessing you with the correct answer. Well, <a href="http://ift.tt/XKLo4u">good luck with that fantasy</a>. The only thing I&#8217;ve ever seen work is <b>getting down deep and dirty in the trenches with your users, communicating with them and cultivating relationships</b>. That&#8217;s how you suss out the rare 10% of community feedback that is amazing and transformative. <i>That&#8217;s</i> how you build a community that gives a damn about what you&#8217;re doing &ndash; by caring enough to truly listen to them and making changes they care about.
        </p>
        
        <table>
          <tr>
            <td class="welovecodinghorror">
              [advertisement] <a href="http://ift.tt/i370tl" rel="nofollow">Stack Overflow Careers</a> matches the best developers (you!) with the best employers. You can search our <a href="http://ift.tt/vQpNiV" rel="nofollow">job listings</a> or <a href="http://ift.tt/t6KurI" rel="nofollow">create a profile</a> and even let employers find you.
            </td>
          </tr>
        </table>
        
        <p>
          via sathyabhat&#8217;s blurblog http://ift.tt/1h0NtTQ
        </p>
        
        <div class="sharedaddy sd-sharing-enabled">
          <div class="robots-nocontent sd-block sd-social sd-social-icon-text sd-sharing">
            <h3 class="sd-title">
              Share this:
            </h3>
            
            <div class="sd-content">
              <ul>
                <li class="share-pocket">
                  <a rel="nofollow noopener noreferrer" data-shared="" class="share-pocket sd-button share-icon" href="https://sathyasays.com/2014/02/20/complaint-driven-development/?share=pocket" target="_blank" title="Click to share on Pocket"><span>Pocket</span></a>
                </li>
                <li class="share-twitter">
                  <a rel="nofollow noopener noreferrer" data-shared="sharing-twitter-1237" class="share-twitter sd-button share-icon" href="https://sathyasays.com/2014/02/20/complaint-driven-development/?share=twitter" target="_blank" title="Click to share on Twitter"><span>Twitter</span></a>
                </li>
                <li class="share-facebook">
                  <a rel="nofollow noopener noreferrer" data-shared="sharing-facebook-1237" class="share-facebook sd-button share-icon" href="https://sathyasays.com/2014/02/20/complaint-driven-development/?share=facebook" target="_blank" title="Click to share on Facebook"><span>Facebook</span></a>
                </li>
                <li class="share-linkedin">
                  <a rel="nofollow noopener noreferrer" data-shared="sharing-linkedin-1237" class="share-linkedin sd-button share-icon" href="https://sathyasays.com/2014/02/20/complaint-driven-development/?share=linkedin" target="_blank" title="Click to share on LinkedIn"><span>LinkedIn</span></a>
                </li>
                <li class="share-email">
                  <a rel="nofollow noopener noreferrer" data-shared="" class="share-email sd-button share-icon" href="https://sathyasays.com/2014/02/20/complaint-driven-development/?share=email" target="_blank" title="Click to email this to a friend"><span>Email</span></a>
                </li>
                <li class="share-end">
                </li>
              </ul>
            </div>
          </div>
        </div>