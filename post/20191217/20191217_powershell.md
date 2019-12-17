curl -ContentType "application/json" -Method POST -Uri http://localhost:2200/auth/login -Body '{"id":"", "login_type":"GUEST"}'
curl -ContentType "application/json" -Method POST -Uri http://localhost:2200/usergame/playinfo -Body '{"session_id":"0a25866880e441da9ceae4a1dbeeb1fc", "seq_title":1}'
curl -ContentType "application/json" -Method POST -Uri http://localhost:2200/usergame/chapter_start -Body '{"session_id":"0a25866880e441da9ceae4a1dbeeb1fc", "seq_title":1, "seq_chapter":1}'

curl -ContentType "application/json" -Method POST -Uri http://localhost:2200/usergame/choice -Body '{"session_id":"0a25866880e441da9ceae4a1dbeeb1fc", "seq_title":1, "seq_chapter":1, "type":"SAVE", "choice":"Day7StoryScenario_1_2", "base_choice":"Day7StoryScenario_1_1", "is_core":"N"}'

