# CoronaVirus Bot for India (Covid19)

![corona-screenrecord](https://user-images.githubusercontent.com/39980643/77245941-a894f180-6c48-11ea-820d-7573e03e8cca.gif)

## Features
- Sit back and relax - the coronavirus updates will come to you.
- Get Slack notifications (picture below)
  -  New Corona Virus cases happening in India
  -  How many Indian nationals have Corona Virus per State?
  -  How many deaths happened per State?
  -  The new States entering the corona zone like Chattisgarh
- Too many updates? Subscribe only to the states that you want.
- Its reliable - the source of data is official Government site ([here](https://mohfw.gov.in/))
- Its ROBUST! 
  - What if script fails? What if the Govt website changes format?
  - You get Slack notifications about the exceptions too.
  - You have log files (check `bot.log`) too, to evaluate what went wrong
- Don't like a feature? Change it! Raise a Pull Request too 😉


## Installation
- You need Python
- You need a Slack account + Slack Webhook to send slack notifications to your account
- Install dependencies by running
```bash
pip install tabulate
pip install requests
pip install beautifulsoup4
```
- Clone this repo and create auth.py
```bash
git clone https://github.com/shadowdevcode/corona-bot/
cd corona-bot
touch auth.py
```
- Write your Slack Webhook into auth.py
```python
DEFAULT_SLACK_WEBHOOK = 'https://hooks.slack.com/services/<your custome webhook url>'
```
- Setup the cron job to receive updates whenever something changes
```bash
crontab -e # opens an editor like vim or nano
# now write the following to run the bot every 5 mins
*/5 * * * * cd $PATH_TO_CLONE_DIR; python3 corona_bot.py --states 'haryana,maharashtra'
# to receive updates for all states, ignore the --states flag
```
