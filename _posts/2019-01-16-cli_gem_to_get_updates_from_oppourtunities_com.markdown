---
layout: post
title:      "CLI Gem to get updates from oppourtunities.com"
date:       2019-01-16 20:40:42 +0000
permalink:  cli_gem_to_get_updates_from_oppourtunities_com
---

## Project Description 
For my first Ruby project, I worked on a CLI Gem that can read new updates from http://oppourtunities.com. 

This website is an Nigeria based non-profit organization. Founded in 2016 creates perfect bridge between opportunity provider and seekers thereby enabling youths get free, easy and instant access to all life changing opportunities. The forum wants to expose young people to the opportunities available across the continent and globe as well. Through the forum, many young people have been able to get their bearing thereby enabling them pursue their dreams through fully / partial funded scholarship, conference, grants and other opportunities. The forum was created in line with Sustainable Development Goal 4 (Quality Education) and 8 (Good Jobs and Economic Growth for a prosperous society. An organizational member of Sustainable Development Solution Network (SDSN) http://sdsnyouth.org/member-organizations/ 			

My gem completes a very simple task: when user types `new-opportunities` in their terminal, the gem will return a list of new scholarship and fellowship opportunities. For example, it'll show: 
```
1. 1. 2019 Tech ME Women ICTpreneurs Nigeria Training for Young Women in Lagos.
2. 2019 Aga Khan Foundation International Scholarship Programme.
```

For the second level, the gen will take an index number as an input, and display the deadline to apply, as well as the post date. For example, it'll show 

```
2019 Aga Khan Foundation International Scholarship Programme
Deadline: Deadline: March 31, 2019.
Posted on: January 11, 2019
```

On the third level, the user will have the option to know more about the project, or get the url so they can go to the webpage to learn more. For example, 
when users type in `more`, the gem will return 
```
Voices for Diagnosis is an annual prize, launched in 2018, to recognize individuals and organizations that implement innovative approaches to improve access to and create demand for timely, cost-effective diagnostic solutions for infectious diseases in low- and middle-income countries (LMICs). The prize is adjudicated and supported by the Diagnostics Ambassadors, an informal network of thought leaders from diverse disciplines who help champion the important role played by diagnostics in global health.
```

when users type in `url`, the gem will return `http://oppourtunities.com/2019-voices-for-diagnosis-community-prize/`



## nokogiri 
The gem is made possible by nokogiri. To start scraping, the first thing is to know what's included in an opportunity

### information is included for an opportunity
#### First level
- an opportunity has an index number
- an opportunity has a name

#### Second level
- an opportunity has a name
- an opportunity has a deadline
- an opportunity has a posted date

#### Third level
- an opportunity has an URL
- an opportunity has a description

With this list, we can go into the source page http://oppourtunities.com/updates/ to scrpae with nokogiri. 


## CLI 
The CLI logic of the gem follows the three layers of operation, in addition, the gem allow users to exit at any time of the interaction. Therefore, `while input != 'exit'` is used at the outter level of all loops to ensure this. 

