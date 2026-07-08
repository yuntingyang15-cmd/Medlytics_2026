# Github Reference

## Setting up your fork

```
# Clone your fork
git clone https://github.com/[YOUR USERNAME]/Week[NUMBER]_Public

# Make sure you're in the right directory
cd Week[NUMBER]_Public

# Now add the upstream
git remote add upstream https://github.com/BeaverWorksMedlytics2020/Week[NUMBER]_Public

# Check that your upstream's set up correcty
git remote -v

# You should see something like this where your origin is linked to your fork (as seen by your username) and upstream is set to the original class repository (as seen by BeaverWorksMedlytics2020)
origin  https://github.com/emilygtan/Week1_Public.git (fetch)
origin  https://github.com/emilygtan/Week1_Public.git (push)
upstream        https://github.com/BeaverWorksMedlytics2020/Week1_Public (fetch)
upstream        https://github.com/BeaverWorksMedlytics2020/Week1_Public (push)
```

## Keeping your fork up to date

```
git pull

git fetch upstream

git checkout master

git commit -m "[YOUR COMMIT MESSAGE HERE]"

git merge upstream/master master

git push origin master
```

## Debugging common errors
---
If your terminal happens to open up to the following message at the top,

```
Merge branch 'master' of [link of remote repository]
# Please enter the commit message for your changes. Lines starting
# with '#' will be ignored, and an empty message aborts the commit.
#
#
#
```

then you can either first edit that default commit message on the first line or leave it as it is, but then you want to
1. Hit the `esc` key to exit insert mode
2. Type `:wq`
	- `:` enters command mode
	- `w` is for write (save)
	- `q` is for quit
3. Hit the enter key to save the commit message and exit

---
If you notice after running the commands for fetching updates and pushing that your fork still does not have the new files for the day...

1. Check if your origin and upstream are correct by running `git remote -v`
2. If upstream is set to your fork instead of the class repository you can fix that by running
	```
	# Remove the current upstream
	git remote rm upstream
	# Add the correct upstream
	git remote add upstream https://github.com/BeaverWorksMedlytics2020/Week[NUMBER]_Public
	```
3. Double check to make sure you're all set by running `git remote -v` again, reference the forking section to see what your origin and upstream should look like.
4. Now you should be able to start running the commands for keeping your fork up to date again starting with `git fetch upstream` etc.
