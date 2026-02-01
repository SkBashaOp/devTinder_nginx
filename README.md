Nginx Config File path and Frontend Build to NGINX Folder 
short for change owner.
Linux files have:
an owner (user)
a group
This command changes both.

-R (recursive)
Means:
“Apply this change to this folder AND everything inside it”
So it affects:
/var/www/devtinder
all subfolders
all files (HTML, JS, images, etc.)

www-data:www-data
This part is:
user : group
www-data

This is the default Linux user that:
Nginx
Apache
run as.
So you’re saying:
“Make Nginx the owner of these files.”
/var/www/devtinder
This is your website root directory.
What this achieves (VERY IMPORTANT)
Before:

Files might be owned by ubuntu
Nginx runs as www-data
Result:
❌ Permission denied
❌ Blank page
❌ 403 Forbidden

After:
Nginx owns the files

Nginx can:

read frontend files
serve JS/CSS
proxy API requests
✅ Everything works smoothly

Your backend source code can still be owned by ubuntu
Only public web files need www-data
