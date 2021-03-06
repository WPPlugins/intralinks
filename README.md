# Intralinks

At Automattic we use lots of internal WordPress sites to do everything from manage projects to announce new hires to talk about video games.  Among all of those sites, we have lots of internals links.  I wanted to use those links to help people (me) find related conversations faster.  Thus, Intralinks was born.

Intralinks shows the links between posts within a WordPress site or network.  When you're reading one post, Intralinks can show you the other posts that have linked there.

### What the hell does that mean?

Let's try an example.  Let's say you're reading a post called "Google 2nd Quarter Earnings".  But it's already Q4, and in the meantime Q3 earnings have been posted and linked back to the Q2 post (maybe to update the status of some project).  Intralinks would show you, while readin the Q2 post, that the Q3 post had linked to it.

## Some Technical Background

### Multisite or not

This was built with the idea of multisite in mind, but will work just fine in single site.  What really matters is a set of content that has relevant links within it.  Think of Intralinks as representing the graph (as in edges and nodes) of your content.

### WordPress.com

I originally wrote this to run on WordPress.com with an ElasticSearch index and data stored in Memcached.  I adapted it to use normal database queries and Mark Jaquith's excellent WP TLC Transients plugin.