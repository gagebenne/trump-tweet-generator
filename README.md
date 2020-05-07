# Trump Tweet Generator
*EECS 738**

![Generated Trump Tweet](/tweet.png "Generated Trump Tweet")

## Authors
[Andy Monroe](https://www.andymonroe.dev) and [Gage Benne](https://www.gagebenne.com)

## Dataset
We pulled our dataset from the [trump_tweet_data_archive](https://github.com/bpb27/trump_tweet_data_archive) hosted on GitHub..  Once collected in .json format, we convert it into a simplified format suitable for our purposes using a [simple python script](trump_tweets/cleaner.py).

If we decide to extend this project in the future, we will likely update it to pull directly from Twitter's API.

## Language
We chose the Haskell programming language for our project, due to our shared experience with mathematics, and our general affinity for the functional style offered by Haskell.  Additionally, we thought it would make for an interesting challenge that would set our solution apart from those of our peers.

## Process
At a high level, our Hidden Markov Model uses a [Data.Map](https://hackage.haskell.org/package/containers-0.6.0.1/docs/Data-Map.html) data structure to pair tuples of words or punctuation with a list of possible succeeding words or punctuation.

### Learning
Our Hidden Markov Model learns by taking in the next three tokenized words in a stream, putting the first two into a tuple, and finding or creating the matching entry in the Map. The third token is then appended to the list associated with the key.

### Generating
Two generate text, we build a tuple of tokens (which can each be a Nothing, if appropriate, like for a first word), and look up that key in our Map.  We then select a randomized element from the list associated with that key as our succeeding token.

If a key is not found, we try a series of alternate keys based on the original key, until we reach the default (Nothing, Nothing) case.  Our process guarantees that a (Nothing, Nothing) key always has a non-empty list, so this can be defaulted to when a key is not found.

## Results
We found our results to be HUGELY successful.

### Un-Seeded Tweet Examples
Tweets generated without any user-defined starter text. *Disclaimer: These tweets have no character limit!*
```
THE DNC ? RIGGED INVESTIGATION !
```
```
EARLY INTO MY CAMPAIGN RALLIES, WON THE ELECTION ? ISN'T THIS HIGHLY ILLEGAL .
PERHAPS HE SHOULD NEVER, EVER BEEN WITH EMPLOYMENT BEING AT AN EVER EXPANDING
LABOR FORCE LEADING THE WAY JUSTICE SHOULD OPERATE . SO ARE MANY OTHERS . BIG
DEFICIT . NOT GOOD !
```
```
ACCORDING TO A NANCY PELOSI AND DEMS … WILL THE SCATHING DOCUMENT WRITTEN ABOUT
LYIN' JAMES COMEY, THE WORST IN HISTORY . WHEN I BEGRUDGINGLY SIGNED THE FISA
COURT THAT THE FBI TAKE THE SERVER ? LET THESE LARGE VENUES, MANY THOUSANDS OF
CROOKED HILLARY AND SLIPPERY JAMES COMEY, BY THE HOUR . SOME ARE FALSE . SOME
GREAT LEGISLATION AWAITS - BE PREPARED ! #HURRICANEMICHAEL
```

### I AM ...
Generated tweets with starting words "I AM"
```
I AM PLEASED TO ANNOUNCE THAT I AM CONSIDERING A FULL PARDON TO DINESH D'SOUZA TODAY .
```
```
I AM USED TO IT . AT SOME POINT THE DEMOCRATS MUST BE FAIR AND REASONABLE
IMMIGRATION LAWS . THESE RADICAL PROTESTERS WANT ANARCHY – BUT AT SOME POINT
I KNEW THEY WOULD NOT HAVE THEM BOURNE BY THE AMERICAN PEOPLE TO BELIEVE, THE
MEETINGS CONCERNING THE SHUTDOWN ! HOUSE REPUBLICANS WERE GREAT YESTERDAY !
```
```
I AM ALL ALONE (POOR ME) IN THE SENATE, AND EPIC VICTORY : 53 TO 47 ? ALL I
AM ASKING FOR CAN GIVE THE CONCLUSIVE ANSWERS . @FOXNEWS . THIS WAS A POLITICAL
AD FOR THE US , SURVIVE MAKING THE COMMENCMENT ADDRESS TODAY AT 3 PM , AFTER
NFL GAME . YOU ARE GOING WAY UP, YOUR WAGES GOING UP, YOUR WAGES GOING UP,
YOUR WAGES GOING UP, AND YOUR WIN IN OHIO TONIGHT ! #MAGA
```

### AMERICA IS ...
Generated tweets with starting words "AMERICA IS"
```
AMERICA IS OPEN FOR BUSINESS !
```
```
AMERICA IS BACK ! STRONGEST HOLIDAY SALES BUMP SINCE THE ELECTION ? WE BROUGHT
OR GAVE NO HATS AS THE PRESIDENT DESERVES AN ATTORNEY GENERAL KEN PAXTON .
THEY EXONERATED HER EVEN BEFORE THEY WERE STARTING TO LEARN MORE ON CLEANING
ITS FILTHY CANOPIES, DOORS AND WINDOWS (BADLY NEEDS A PAINT JOB) RATHER THAN
COMING TO DC
```
```
AMERICA IS THRIVING, AND AMERICA IS BOOMING, WITH JOBS AND GIVEN UP NOTHING .
THANK YOU . AND BYE THE WAY, THERE WAS INDEED AT LEAST ONE FBI REPRESENTATIVE
IMPLANTED, FOR POLITICAL REASONS AND BECAUSE THEY DIDN'T GET DONE AND APPROVED .
SENATE MUST QUICKLY PASS A LEGISLATIVE FIX TO ENSURE VETERANS HAVE THE VOTES
TO GET INTO THE CRUCIAL ISSUE OF PRISON REFORM . WORKING HARD . NEWS REPORTS
CONCERNING THE SHUTDOWN AND SYRIA ARE MOSTLY FAKE . THEY TOTALLY RELY ON US,
WHICH IS FOR THE DEMOCRATS IS NOW SECURE AND WILL NOT HAPPEN !
```

### BOB MUELLER ...
Generated tweets with starting words "BOB MUELLER"
```
BOB MUELLER IS COMEY'S BEST FRIEND . WITCH HUNT !
```
```
BOB MUELLER (WHO IS HIGHLY CONFLICTED) WAS NOT APPROVED BY LITTLE BOB CORKER
JUST STATED THAT WE WILL NEVER BE PROVEN AND ARE ALL UNBELIEVABLE, ARE A NO .
NOT ONLY GOOD FOR OUR NATION APPRECIATES YOUR HEROISM, COURAGE & GENIUS . GOD
BLESS THE USA AGAIN !
```
```
BOB MUELLER AND HIS FELLOW DEMOCRATS TO COME OUT ABOUT ME & OTHERS, SO THAT WE
WILL MAKE A FANTASTIC SENATOR FOR PENNSYLVANIA BUT HIS OPPONENT RUNS ONE OF
MANY SUCH PREVENTABLE TRAGEDIES . WE NEED KEVIN IN THE OFFICE, I WOULD STRONGLY
SUGGEST THAT YOU CAN'T FORGET TWO OF THE HIGHLY CONFLICTED ROBERT MUELLER AND
HIS LOVER, THE LOVELY LISA PAGE, THAT WE'LL STOP TRUMP FROM BECOMING PRESIDENT .
```

### MAKE AMERICA ...
It has to get this one right...
```
MAKE AMERICA GREAT AGAIN ! #MAGA
```
```
MAKE AMERICA GREAT AGAIN ! NO COLLUSION, EXCEPT BY THE PREVIOUS ADMINISTRATION
AND REJECTED THE ATTEMPT TO STOP THE DRUGS !
```
```
MAKE AMERICA GREAT AGAIN ! ACTUALLY, IT IS INDEED THE ENEMY OF THE NEW
SECRETARY OF COMMERCE WILBUR ROSS AND PETER STRZOK . ALSO REMEMBER THAT THEY
REFUSED TO BREAK INTO A LAWYER'S OFFICE (EARLY IN THE LAST YEAR AT THE BORDER
BECAUSE OF THE MOST BRILLIANT & SUCCESSFUL CAR EXECUTIVES SINCE THE GREAT
STATE OF PENNSYLVANIA WHERE WE HAVE NO DOUBT ABOUT THAT !
```
```
MAKE AMERICA A SAFER PLACE, THOUGH HARD TO GET IT ! STAY AWAY FROM OUR OWN
GOVERNMENT AFTER HE ADMITTED TO KILLING A POLICE OFFICER DURING A GOOD THING,
NOT A UKRAINIAN BUSINESSMAN, WHO ASKED ME TO GET AWARDS FOR FICTION ! NBC, MY
FORMER HOME WITH THE PRESIDENTS DECISION . THINGS ARE HAPPENING, BUT THEY JUST
WANT TO RAISE YOUR TAXES, OPEN YOUR BORDERS, AND CONTINUE MAKING AMERICA SAFE
AND GREAT AMERICAN FLAG, WE PUT OUR HANDS ON OUR IMPORTANT SECURITY RELATIONSHIP .
IT IS TODAY . SO WHEN DID PEOPLE START SAYING, THANK YOU, PEOPLE ARE NOT SOON
BROKEN DOWN AND REMOVED, WE WILL NOT REST UNTIL OUR AMBASSADORS, JUDGES AND THE
UNITED STATES UNTIL THEIR CLAIMS ARE INDIVIDUALLY APPROVED IN COURT . HEADING
BACK HOME (HAPPY & HEALTHY), THAT PERSON WOULD BE FRUSTRATED TOO … AND WILL HE
BE RECOMMENDING ACTION ON THE TEN-YEAR ANNIVERSARY OF THE YEAR BEFORE I
ARRIVED, SPOKE AT LENGTH ABOUT THE MEETING WERE REINSTATED, HOLDING IT ON THE
PLANET . GREAT SHOW !
```
