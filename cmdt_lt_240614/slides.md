% title: Lecture capture with Google Hangouts
% subtitle: and how I learned to love the sound of my own voice
% author: Killian O'Brien
% author: Mathematics
% author: tinyurl.com/kob-24-06-14
% thankyou: Thanks everyone!
% thankyou_details: And especially these people: Jon S., Colin, Nick, Peter, Darren
% contact: <span>email</span> <a href="mailto:k.m.obrien@mmu.ac.uk">k.m.obrien@mmu.ac.uk</a>
% contact: <span>twitter</span> <a href="https://twitter.com/killianobrien">@killianobrien</a>
% favicon: http://www2.mmu.ac.uk/media/mmuacuk/style-assets/images/favicon.ico

---
title: Example recording
subtitle: Talking through some notes
class: nobackground

<iframe height=450px src="http://www.youtube.com/embed/qvdYGdOL52A#t=40m0s" frameborder="0" allowfullscreen></iframe>

---
title: Example recording
subtitle: Writing some code
class:

<iframe height=450px src="http://www.youtube.com/embed/ewQK_S30KVY#t=33m30s" frameborder="0" allowfullscreen></iframe>

---
title: What the students see
build_lists: false

- Got to a [Moodle area](http://moodle.mmu.ac.uk/course/view.php?id=34993)
- Link from there to a Google+ page
- On the G+ page there is a chronological list of the lectures as Hangout recordings with extra info posted in comments below
    - dropbox links to scanned visualizer pages
    - weblinks to online code snippets
    - ...

---
title: What are Google Hangouts?

- Hangouts (Google) $\approx$ Skype (Microsoft)

Google help guides on 

- [Google+](https://support.google.com/plus/?hl=en-GB#topic=3049731)
- [Google+ pages](https://support.google.com/plus/?hl=en-GB#topic=3049731)
- [Google Hangout on Air](https://support.google.com/plus/answer/2553119?hl=en-GB)


---
title: The lecturer
build_lists: true

- Enter the lecture room
- other steps *emphasize no encoding steps and robustness of recording*

---
title: Minutes watched
subtitle: 6G4Z3001 Mathematics Fundamentals, Level 4, ~110 students
class: img-top-center

<img src=figures/maths_fundamentals_minutes_watched.PNG>

2048 minutes (UK 1558, USA 274)

<footer class="source"> data source: youtube analytics </footer>

---
title: Minutes watched
subtitle: 6G5Z3001 Mathematical Methods, Level 5, ~100 students
class: img-top-center

<img src=figures/analytical_methods_minutes_watched.PNG>

991 minutes (UK 602, USA 133)

<footer class="source"> data source: youtube analytics </footer>

---
title: Minutes watched
subtitle: 6G5Z3006 Number Theory & Cryptography, Level 5, ~40 students
class: img-top-center

<img src=figures/maths_fundamentals_minutes_watched.PNG>

2957 minutes (UK 678, IRL 609, USA 738)

<footer class="source"> data source: youtube analytics </footer>

---
title:
class: fill nobackground

<img src=figures/happy_students.jpg />

<aside class="gdbar"><h1>Student feedback</h1></aside>

<footer class="source"> image source: stolen from the internet </footer>

---
title:
class: fill nobackground

<img style="vertical-align: middle" src=figures/monty_mob.jpg />

<aside class="gdbar"><h1>Student feedback</h1></aside>

<footer class="source"> image source: stolen from the internet </footer>

---
title: Segue slide
subtitle: I can haz subtitlz?
class: segue dark nobackground

---
title: Maybe some code?

press 'h' to highlight an important section (that is highlighted
with &lt;b&gt;...&lt;/b&gt; tags)

<pre class="prettyprint" data-lang="javascript">
function isSmall() {
  return window.matchMedia("(min-device-width: ???)").matches;
}

<b>function hasTouch() {
  return Modernizr.touch;
}</b>

function detectFormFactor() {
  var device = DESKTOP;
  if (hasTouch()) {
    device = isSmall() ? PHONE : TABLET;
  }
  return device;
}
</pre>

