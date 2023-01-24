# BDevManager2
A business development manager library

BDevManager2  is a A business development manager library designed to make prospecting, calling leads, saving notes, and developing new opportunities for your business...simple.

    1. gather 1000 leads from Linkedin
    2. order your leads in Excel and tag the top 100 prospects
    3. plan your week to call 10 at a time
    4. use this library to capture BANT (budget, Authority, Need, Timeline)
    5. put your results in to a system of record by the end of each day (use a CRM)
    6. call me if you need help closing business and making revenue:) 
    7. repeat tell you to make all the money you need to be free:)


Step 1 create a main.py file in your python project.
Step 2 create a sales_leads.csv file with all of your leads (up to 1000)
Step 3 add the following to your main.py file:

``` 
   from bdm_eng import LeadList, Top100ProspectLeads, Top10TargetsForTheWeek, TodayTarget, TodaysActivity, BANT, GameLoop


    leads = LeadList("sales_leads.csv")
    top_leads = Top100ProspectLeads()
    top_leads.add_leads(leads.process_leads())
    top_10_targets = Top10TargetsForTheWeek()
    top_10_targets.add_leads(top_leads.get_leads())
    today_target = TodayTarget(top_10_targets.get_leads())
    todays_activity = TodaysActivity()
    bant = BANT()
    game_loop = GameLoop(today_target, todays_activity, bant)
    game_loop.start()
```
Step 4 install the libery by using: "pip3 install BDevManager2"
Step 5 run program: "python3 main.py"


When you run the program you will see a promote asking for user import on call notes:)

    Current target:  ['1', '<lead1 name>', '<lead1 email>', '<lead1 role>', '<lead1 phonenumber>', '<lead1 business>', '<lead1 title>']
    
    Enter 'e' to edit the target, 's' to save and move to the next target, or 'q' to quit:

when you use the edit command you will see:
    Please enter budget notes:
        testdata
    Please enter authority notes:
        testdata
    Please enter needs notes:
        testdata
    Please enter timeline notes:
        testdata

This libary helps you quickly capture your daily notes as you do business development task (calling new customers to build leads!)

after you enter BANT you will see the saved output:

    [{'lead': ['1', '<lead1 name>', '<lead1 email>', '<lead1 role>', '<lead1 phonenumber>', '<lead1 business>', '<lead1 title>'], 'notes': {'budget_notes': 'testdata', 'authority_notes': 'testdata', 'needs_notes': 'testdata', 'timeline_notes': 'testdata'}}]

then you will see the next lead in the dataset! its a Game Loop! this is the way! we can now define our leads for the day in a CSV file, and loop through the data easily, all as we save notes:) this process can scale out no mater the business or CRM being used by BDM's.

Lastly, lets look at the final "daily Completed task list":

     [{'lead': ['1', '<lead1 name>', '<lead1 email>', '<lead1 role>', '<lead1 phonenumber>', '<lead1 business>', '<lead1 title>'], 'notes': {'budget_notes': 'testdata', 'authority_notes': 'testdata', 'needs_notes': 'testdata', 'timeline_notes': 'testdata'}},
     {'lead': ['2', '<lead1 name>', '<lead1 email>', '<lead1 role>', '<lead1 phonenumber>', '<lead1 business>', '<lead1 title>'], 'notes': {'budget_notes': 'testdata', 'authority_notes': 'testdata', 'needs_notes': 'testdata', 'timeline_notes': 'testdata'}},
     {'lead': ['3', '<lead1 name>', '<lead1 email>', '<lead1 role>', '<lead1 phonenumber>', '<lead1 business>', '<lead1 title>'], 'notes': {'budget_notes': 'testdata', 'authority_notes': 'testdata', 'needs_notes': 'testdata', 'timeline_notes': 'testdata'}}
     ]....

now we can work as hard and as long as we want and have a runing list of completed task! go get that money! - The BlackFox
