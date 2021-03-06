---
id: finishing-touches
title: Finishing touches
---

Try it out:

- Change your REPL to say "test6" instead of "test1" and then re-run the request by hitting the play button.

  ![assets/gettingstarted/Screen_Shot_2020-02-11_at_11.04.01_AM.png](assets/gettingstarted/Screen_Shot_2020-02-11_at_11.04.01_AM.png)

- A new trace dot will appear on the HTTP Post `/test` handler. It shows "test3" in the body of the request.

  ![assets/gettingstarted/Screen_Shot_2020-02-11_at_11.04.07_AM.png](assets/gettingstarted/Screen_Shot_2020-02-11_at_11.04.07_AM.png)

- Click on the datastore you will see the record added to the database.

  ![assets/gettingstarted/Screen_Shot_2020-02-11_at_11.04.12_AM.png](assets/gettingstarted/Screen_Shot_2020-02-11_at_11.04.12_AM.png)

- Create a REPL to do `db::getAll` for DailyReports. You'll be able to see the Daily Reports so far (probably just one). If you re-run your CRON by hitting "replay" and if it's the same day it should overwrite your report with a new one including your new request! You will need to re-run the REPL to see the update.

![assets/gettingstarted/reportREPL.png](assets/gettingstarted/reportREPL.png)

Congratulations! You now have your first Dark application: an API that stores requests into a datastore, and create a daily report of those requests.
