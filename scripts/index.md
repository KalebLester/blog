# Automagic content downloading from Reddit, Twitter, and YouTube.

[Gallery-DL](https://github.com/mikf/gallery-dl) is a command line utility that allows downloading from a multitude of websites. I am will be using it to download all my liked posts on Twitter.

Script:
```markdown
gallery-dl 
--cookies "C:\Users\{name}\Documents\scripts\Cookies\twitter.txt"
-d "D:\"
-f "{content[0:64]|filename:R /_/}.{extension}"
--download-archive "D:\Twitter\downloaded_log.txt" 
--write-log "D:\Twitter\log\log.txt" 
--sleep 1.0-2.0 
--mtime-from-date 
-v
https://twitter.com/{username}/likes
```
Copy friendly format:
```
gallery-dl --cookies "C:\Users\{name}\Documents\scripts\Cookies\twitter.txt" -d "D:\" -f "{content[0:64]|filename:R /_/}.{extension}" --download-archive "D:\Twitter\downloaded_log.txt" --write-log "D:\Twitter\log\log.txt" --sleep 1.0-2.0 --mtime-from-date -v https://twitter.com/{username}/likes
```
Each line represents a different command line argument.
1. gallery-dl
   - The name of the program
3. --cookies "C:\Users\{name}\Documents\scripts\Cookies\twitter.txt"
   - Tells the program where our browser cookies are so that the program can view your liked posts. The reason we have to use cookies instead of regular authentication (username + password) is because the goal of the script is to run automatically in the background. With regular authentication, I would have to input a 2fa code every time. You can obtain your cookies for a specific site via the extension [EditThisCookie](https://chrome.google.com/webstore/detail/editthiscookie/fngmhnnpilhplaeedifhccceomclgfbg) for Chrome. The location of the cookies file does not matter as long as the script has read access to it.
