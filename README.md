# Dataset for paper "Experimental evaluation: can humans recognize social media bots?"

We changed the dataset title for the blind review requirements. We will resubmit this dataset in an unanonymised form after the paper review. 

### VKTT2021

<p align="center">
  <img src="https://github.com/RAIDdatasets/VK_dataset/blob/main/readme_img/TT_logo_new.png?raw=true" alt="vk_logo" width="300" />
</p>

Datasets resulted from an experiment where users tried recognising bots (**VK**ontakte **T**uring **T**est).

Includes 2 files: *answers.csv* with results of the experiment and *areHumansCanDetectBots.ipynb* with processing the results.

**answers.csv** include the following fields:

| # | column       | column description             |
| ------------- | ---------- | -------------------------------- |
|1| time | timestamp of the annotator answer
|2| role | the role of annotator that reflects bot detection scenario (see. list below)
|3| annotator_id | Telegram id of annotator
|4| analysed_account_id | VKontakte id of analysed account
|5| answer | the label of the annotator. It can be USER, BOT, or IDN (i don't know)
|6| ground_truth_label | real label
|7| bot_quality | the quality of analysed bot account (NaN for real users), see dataset MKVK2021 (for MARSHRUTKA bot-trader - the quality was replaced with LIVE)

To each annotator, we give a role. 
Roles can be:
1. BOTS+RANDOM - 50% of accounts are MKVK2021 bots and 50% are real users. Real users are randomly selected among all VKontakte accounts. Reflects scenario when annotator tries to detect bot among random accounts.  
2. BOTS+GROUPS_SHIFTED - 50% of accounts are MKVK2021 bots and 50% are real-users. Real users are randomly selected among MKVK2021 real-users accounts. Reflects scenario when annotator tries to detect bot among accounts with homophily from a large community.
3. BOTS+STUDENTS - 50% of accounts are MKVK2021 bots and 50% are real-users. Real users are randomly selected among verified student accounts of one University. Reflects a scenario when the annotator tries to detect a bot among accounts with strong homophily from a small community.
4. BOTS_ONLY - 100% of accounts are MKVK2021 bots.

**areHumansCanDetectBots.ipynb** include code for result processing:
1. Test hypotheses that humans can detect bots with different qualities in different scenarios.
2. Calculating confidence intervals that describe the human ability to detect bots of different qualities in different scenarios.
3. Calculating hypothetical classifier efficiency measures that describe how classification efficiency decreased when using human-annotated datasets for supervised ML bot detection. 



### VK2021

<p align="center">
  <img src="https://github.com/RAIDdatasets/VK_dataset/blob/main/readme_img/VK_logo.png?raw=true" alt="vk_logo" width="200" />
</p>

VK2021 folder contains datasets with bots and real-users from VKontakte social network. 

It includes 2 CSV files: bots.csv and users.csv

**bots.csv**

Bots were collected directly from bot-traders by purchasing method (is a ground-truth bot label).
Bots also include bot-trader labels and quality labels.

The quality was evaluated with the expert method based on the description of bot-trader offer:
1. Low quality (LOW) means that bots from this company are probably auto-generated accounts that are controlled by software. <br/>
2. Medium quality (MID) means that bots are user-like bots controlled by software.  <br/>
3. High quality (HIGH) means that bots are probably controlled by humans or users from an exchange platform (bot-trader pays real-users to perform malicious actions for money).

The bot-trader label:
1. OLENI and PARIK - classical bot shops.
2. MARSHRUTKA - bot exchange platform where one pays real-users for malicious actions (fake reviews, etc.).

| name of bot-trader that provide bots | Quality |
| --------------------------------- | ------- |
| PARIK                             | LOW     |
| PARIK                             | MID     |
| PARIK                             | HIGH    |
| OLENI                             | LOW     |
| OLENI                             | MID     |
| OLENI                             | HIGH    |
| MARSHRUTKA                        | LOW     |
| MARSHRUTKA                        | HIGH    |

**user.csv** file – contains random real-users that pose some activity from 10 communities. Communities description:

| Name of community | Type       | Description of group             |
| ------------- | ---------- | -------------------------------- |
| BIGFEST       | festival   | cartoon festival                 |
| HCAKBARS      | sport      | hockey club fun community        |
| LENTACH       | mass media | Russian news                     |
| MCELROY       | blog       | re-playing of funny videos       |
| MHL           | sport      | youth hockey                     |
| SEVCABEL      | commerce   | creative space                   |
| TNULL         | developers | software development memes       |
| TPROGER       | developers | software development             |
| VARENNE       | mass media | Belarus news                     |
| VELO          | activists  | development of bicycle transport |

