# Check the format available
youtube-dl.exe -F https://www.youtube.com/watch?v=DH2EDCCzgEY

# Download udemy 
youtube-dl -g https://www.udemy.com/job-ready-web-developer/learn/ -o "%(playlist_title)s/%(chapter_number)s-%(chapter)s/%(playlist_index)s-%(title)s.%(ext)s" -u <email> -p <password> > links.txt
wget --content-disposition -i links.txt [--no-check-certificate]