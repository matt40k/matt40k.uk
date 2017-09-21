---
title: Automating WordPress maintenance
author: matt
type: post
date: 2017-03-09T20:44:50+00:00
url: /2017/03/automating-wordpress-maintenance/
categories:
  - Blog
tags:
  - Automation
  - WordPress

---
<a href="https://wordpress.org/" target="_blank" rel="nofollow">WordPress</a> is an amazing blogging platform. However it does require a fair amount of love. Despite <a href="https://www.mythic-beasts.com/" target="_blank" rel="nofollow">Mythic Beasts</a> managing a large portion of my stack (hardware, OS, Apache, PHP, MySQL) and <a href="https://wordpress.org/" target="_blank" rel="nofollow">WordPress</a> having <a href="https://codex.wordpress.org/Configuring_Automatic_Background_Updates" target="_blank" rel="nofollow">automatic background updates</a> I still find myself logging in and finding pending updates for <a href="https://wordpress.org/" target="_blank" rel="nofollow">WordPress</a>.

The solution was <a href="http://wp-cli.org/" target="_blank" rel="nofollow">WP-CLI</a>. With the shell add-on, I SSH onto my account, then

<div class="gist-oembed" data-gist="matt40k/8efec92c6568a4f363be595568366970.json?file=setup">
</div>

What the above script does is download WP-CLI, grant it execute permission, then downloads my script and again, gives it execute permission.

Then its question of create a cron job using crontab, this can be done by running crontab -e then doing something like: (this runs the script every 15mins and redirects the output to a log file that gets overwrite each time it runs*)

<div class="gist-oembed" data-gist="matt40k/8efec92c6568a4f363be595568366970.json?file=crontab">
</div>

> Note:
> 
> > overwrites the file. >> Appends. I&#8217;ve not used append as I don&#8217;t want to deal with it growing and really I only want the last run details. Still your mileage may vary.

Below is the final script that executes WP-CLI

<div class="gist-oembed" data-gist="matt40k/8efec92c6568a4f363be595568366970.json?file=wp_update.sh">
</div>

&nbsp;
