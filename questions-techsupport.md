## Howdy!
test
Welcome, we're so excited to have you here! The purpose of this gist is to get to know you a bit better and understand your communication style when talking with our users. Please read through and let us know at any point if you have any questions!

## Answer the test tickets
Below you'll find several faux support tickets. Names and identifying information have been changed, but otherwise these support requests are pretty faithful. We've also written some information that should give you an idea of how we go about answering the questions we get. 

## GitHub support tenets: a tl;dr

### Logic + empathy
It's a satisfying balance to bring both analytical skills to a problem, but also remember to respond to a user with care.

### Transparency + honesty
We put effort into writing up [post-mortem blog posts about What Went Wrong](https://github.com/blog/1397-recent-code-search-outages). The balance here is to show enough transparency so users feel respected, but in the case where things are horribly wrong, not share so much that we overwhelm them. 

[Here's an example of a support request](https://gist.github.com/3e89df1f7c0e7d6d5737). It may be easier to say something vague and not-technically-untrue like "there was a small problem and we fixed it". It means we don't have to cop to a mistake on our end. Our users are in the tech world, and are used to figuring out problems. We have found we're much better off telling them what's up, and why.

### Surprise + delight
We have an awesome user base, who generally think we're pretty great. We've put a lot of social effort into drinkups, conference talks and blog posts that wow people and create fans of our company and the products we [ship](http://shipitsquirrel.github.io/images/ship%20it%20squirrel.png).

We follow the [Terms of Service](https://help.github.com/articles/github-terms-of-service), and go above and beyond when it's appropriate. We have the ability to refund as much as we want, and to offer coupons as often as we want. We use this judiciously, as you can turn a surprise into disappointment if wielded badly. You can go back to logic+empathy to consider if what you'd like to do will actually delight the user.

Often, our users may just need information quickly and clearly, without being goofy. We have to know how to respond in the way that best matches how the user is feeling.

### GitHub voice

To explain it casually, we try to exude something that sounds like the person:

* is a real human
* is invested in things going well for you (we care)
* is really smart, but kind (not egotistical)
* and maybe kind of funny (good robot test)
* or at least interesting (and also not actually a robot)
* is not businessy
* could be found in a hoodie, blaring music, slouching in a bean bag chair

### Humble brag
Here's what someone wrote about us, [in a longer piece about moving their company to GitHub](http://redotheweb.com/2012/05/20/switching-our-corporate-version-control-system-to-github.html):
>This leads me to the Customer Service itself. The GitHub staff I’ve been in contact with is extremely helpful, efficient, and comprehensive of our specific requirements. Most important: you deal with real people with real names, not with an anonymous service. When a member of the support staff takes your case (which happens in minutes, even for us Europeans), you get in touch with this person each time you interact on the case. And their CRM tools seem good enough so that your customer history is quickly available to all the support staff. I must say that I didn’t expect such a good customer service from a company with a reputation of automating everything they can, but they really take customer relationship seriously.

### An FYI on how we work
Most of the support team is remote, so we use a group chat room and a support app to work together. We also use GitHub -- it's where the code is stored, where we log bugs, and where we collaborate on new ideas. We don't tend to email or call each other, though we'll videochat every once in a while to catch up. Mostly we hang out in the support chat room to communicate.

***********************************

## Support tickets

### Ticket #1: Rejected pull request from fork 

>To start, I have to say I LOVE GITHUB. You guys rock. I was at your 4th birthday party, thanks for the cupcake and booze!

>Anyway, here's my problem. I sent a pull request to technoweenie, and he rejected it because my master branch is out of sync. What can I do fix this?

>Help me supportocat, you're my only hope!

>/.Steve

Hint: You'll want to address their question, and you could add an explanation of topic branches as a better workflow.

### Ticket #1 response:



### Ticket #2: Syncing internal server and GitHub?

>Hi GitHub! My company has an internal Git server used for deployments. We have an internal Git server and use GitHub. For workflow purposes, how do I sync my repository to GitHub and and the internal Git server?
>
>Thanks,
>vmg

Hint: One common option is Git remotes. There are others!


### Ticket #2 response:



### Ticket #3:  API

>Hi GitHub!
>
>Can you show me how to make an authenticated API request?
>
>Thanks!
>newerthanyou

#### Notes:
Demonstrate a simple request to https://api.github.com/user  
https://developer.github.com/v3/users/#get-the-authenticated-user  
https://developer.github.com/v3/ (Notes on Authentication)


### Ticket #3 response:

### Ticket #4: Unhappy about forking

>JamesTK here, I have another question.

>One of my dev collaborator forked my private repo without explicit permission to do so... is that typical? I am surprised that the system did not notify me if it was okay to grant the fork permission. Is there a way to setup permissions of this sort? Also, other than asking the collaborator to delete the forked repo, can I actually delete it?

>Thanks, jamestk

#### Notes:
You've checked the account in our admin view, he only has one personal repository (jamestk/tribbles), which has one collaborator. Any documentation you may need is available on [help.github.com](https://help.github.com).

### Ticket #4 response: 




### Ticket #5 Need to get my account back

> Hi, my name is Jorge,  
>  
> I'm the CTO of JorgeLLC. Last year, an now ex colleague, Fabian Freebird registered a github organization in name of our company. Mr Freebird has left the company in December 2012 and disappeared. The the github organization is still registered on his account. So i would like to ask if you could transfer the organization to my account jorge2010.
>
>With kind regards,  
>Jorge

#### Notes:

* Looking at our admin view, JorgeLLC is an organization account with one owner -- freebird72
* Looking at the security history of the organization, the user jorge2010 was never a member
* Furthermore, the organization has never had another owner

GitHub does not change ownership of an account (nor will we transfer code) without a court order. This is for security reasons, to protect a legitimate owner from someone scamming their way into becoming the account owner. Also, it protects us from getting in the middle of a fight that we can't settle. We generally suggest two parties work it out themselves, since this results in faster resolution than going to court.

### Ticket #5 response:

