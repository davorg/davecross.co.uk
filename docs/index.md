---
layout: home
author_profile: true
title: "Dave Cross"
---

![Dave Cross](/img/dc-cartoon.png)

Hi, I'm [@davorg](https://links.davecross.co.uk/) on most social media, where my bio
describes me as:

> Geek, Fintech, SEO, Lefty. Feminist, Atheist. Skeptic. Rationalist. Secularist. Humanist. Republican (UK Meaning!). Londoner. Music lover. Writer. Genealogist.

... which probably about covers it.

Mostly, I make things from software. I've been a freelancer developer since 1995, but I recently gave that up
to concentrate on my own projects.

I've made things like
[Apollo 11 at 50](https://twitter.com/apollo11at50)
(which tweeted the Apollo 11 mission status in real time, fifty years after
the mission),
 [Line of Succession](https://lineofsuccession.co.uk/)
(which shows a snapshot of the line of succession to the British throne on
any date since 1820)
and
[TwittElection](https://twittelection.co.uk/)
(which automatically constructed Twitter lists for the candidates in
each constituency in UK general elections - until Elon Musk's changes
to the Twitter API made it too expensive to run). If you're interested,
you can [read more about those projects](/projects/) and others.

My programming language of choice is Perl and I blog about it at
[Perl Hacks](https://perlhacks.com/). I'm
[a frequent speaker](https://talks.davecross.co.uk/)
at conferences about Perl and other open source technologies.

Recently, I wrote
[a guide to getting a website that's useful for your business](https://websiteguide.davecross.co.uk/).
It's aimed at small business owners and shows them the kinds of questions
they should be asking website companies in order to avoid paying too much
for a website that doesn't work for them.

I've written [a few books](/books/).

Outside of work (and if I'm not working on one of my personal projects), I'll
be [at a gig](https://songkick.com/users/davorg), 
[watching a film](https://letterboxd.com/realdavorg) or researching my family tree.

### Some recent writing

<div id="feed_here"></div>

<script>
  document.addEventListener("DOMContentLoaded", async () => {
    const feedContainer = document.getElementById("feed_here");

    try {
      const response = await fetch("https://davorg.theplanetarium.org/feeds.json");
      const data = await response.json();

      const ul = document.createElement("ul");
      ul.classList.add("list-unstyled"); // Bootstrap class for unstyled lists

      data.forEach(item => {
        const li = document.createElement("li");
        li.classList.add("mb-3"); // Add margin between list items

        // Create the main link
        const mainLink = document.createElement("a");
        mainLink.href = item.link;
        mainLink.textContent = item.title;
        mainLink.style.display = "block"; // Equivalent to "d-block"
        mainLink.style.fontWeight = "bold"; // Equivalent to "fw-bold"
        mainLink.style.marginBottom = "0.5em"; // Equivalent to "mb-1"
        li.appendChild(mainLink);

        // Add a line break between the title and the button
        li.appendChild(document.createElement("br"));

        // Create the small button with a link
        const button = document.createElement("a");
        button.href = item.source_url;
        button.textContent = item.source_name;
        button.style.display = "inline-block"; // Make it look like a button
        button.style.padding = "0.1em 0.25em"; // Smaller padding for a smaller button
        button.style.marginLeft = "0em"; // Add space between the title and the button
        button.style.border = "1px solid #007acc"; // Example color
        button.style.borderRadius = "4px";
        button.style.fontSize = "0.6em"; // Smaller font size
        button.style.color = "#007acc";
        button.style.textDecoration = "none";
        button.style.backgroundColor = "transparent";
        button.style.cursor = "pointer";
        button.addEventListener("mouseover", () => {
          button.style.backgroundColor = "#007acc";
          button.style.color = "#fff";
        });
        button.addEventListener("mouseout", () => {
          button.style.backgroundColor = "transparent";
          button.style.color = "#007acc";
        });
        li.appendChild(button);
        ul.appendChild(li);
      });

      feedContainer.appendChild(ul);
    } catch (error) {
      console.error("Error fetching or parsing the feed data:", error);
      feedContainer.textContent = "Failed to load recent writing.";
    }
  });
</script>



