Sleep Score helps to track and rate user sleep. In the application, we will `fetch` data from the **API**, server will send the sleep data list like this:  
```JSON  
[
  {
    "totalTime": "50",
    "totalSleepTime": "40",
    "timeAwake": "10",
    "timeRem": "30",
    "timeLight": "0",
    "timeDeep": "10",
    "percentAwake": "20",
    "percentRem": "60",
    "percentLight": "0",
    "percentDeep": "20",
    "scoreApnea": "9",
    "scoreSnoring": "9",
    "scoreHr": "9",
    "scoreRem": "12",
    "scoreDeep": "9",
    "scoreSleepTime": "4",
    "scoreBtc": "9",
    "scoreRoomTemp": "0",
    "perfectScore": "80",
    "percentScore": "76",
    "worstScore1": "10",
    "worstScore2": "7",
    "totalApnea": "0",
    "totalSnoring": "0",
    "totalSnoringPerHour": "0",
    "avgHr": "67",
    "avgRr": "10",
    "btcMax": "0",
    "btcMin": "0",
    "avgRoomTemp": "32",
    "sleepStageArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "bedArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "hrArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "rrArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "snoringArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "apneaArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "btcArr": [
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "roomTempArr": [
      "33",
      "32",
      "32",
      "32",
      "32"
    ],
    "vitalSignalArr": [
      "100",
      "0",
      "0",
      "0",
      "0"
    ],
    "unixTimeArr": [
      "1648975114",
      "1648976754",
      "1648978154",
      "1648981154",
      "1648983034"
    ]
  },
  {
    "totalTime": "80",
    "totalSleepTime": "70",
    "timeAwake": "10",
    "timeRem": "30",
    "timeLight": "30",
    "timeDeep": "10",
    "percentAwake": "13",
    "percentRem": "38",
    "percentLight": "38",
    "percentDeep": "13",
    "scoreApnea": "9",
    "scoreSnoring": "9",
    "scoreHr": "9",
    "scoreRem": "12",
    "scoreDeep": "7",
    "scoreSleepTime": "4",
    "scoreBtc": "9",
    "scoreRoomTemp": "1",
    "perfectScore": "80",
    "percentScore": "75",
    "worstScore1": "10",
    "worstScore2": "7",
    "totalApnea": "0",
    "totalSnoring": "0",
    "totalSnoringPerHour": "0",
    "avgHr": "66",
    "avgRr": "10",
    "btcMax": "0",
    "btcMin": "0",
    "avgRoomTemp": "31",
    "sleepStageArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "bedArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "hrArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "rrArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "snoringArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "apneaArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "btcArr": [
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0",
      "0"
    ],
    "roomTempArr": [
      "31",
      "31",
      "31",
      "31",
      "31",
      "31",
      "31",
      "31"
    ],
    "vitalSignalArr": [
      "100",
      "0",
      "0",
      "0",
      "0"
    ],
    "unixTimeArr": [
      "1648861755",
      "1648863995",
      "1648866435",
      "1648868515",
      "1648869715",
      "1648870555",
      "1648872555",
      "1648874915"
    ]
  }
]
``` 
In the app, we will map the Sleep Data List with the History Data based on `Date`. In the JSON, there has a value that name `unixTimeArr` contains an array of user sleep times. We take the first element of that array and map it to History list.  
The sleep data will show like this:  
![Sleep Data Example](https://i.ibb.co/pWYMhg8/sleep-data-example.png)  
Details for Sleep Data:  
**Total Score**: equal to `percentScore` from the JSON value. Map the rating (Concerned, fair, good, very good, and excellent) based on the rating bar below it.  
**Sleep Stages**:  
- *REM sleep*: equal to `percentRem`  
- *Deep sleep*: equal to `percentDeep`  
- *Light sleep*: equal to `percentLight`  
- *Awake*: equal to `percentAwake`  
The **Preferred** value, it is the hard code value. That don't need to parse any value to that.
