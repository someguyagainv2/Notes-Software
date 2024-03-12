# Notes-Software
This is a description of my notes software and how it was made the timeline what lead up what's the purpose. Other information.

<h1> The Starting Point </h1>

I started working on this project on 12/03/2024 (DD/MM/YEAR) I started this project as I wanted to move from basic python software to more open enviroment in this case .NET C# Software making for prior knowledge I have done work in C# not a lot I did pass an introduction course for it but it did not include graphical aspects inside of said course this was more for general knowledge get you basics so I was diving into the deep end for C#. I have prior knowledge in SQL before this and had tampered around quite a lot beforehand I'm also fully aware of issues what may arise from SQL for example SQL Injections one of common OWASP Vulnerabilities I accounted for this as I do CTF's capture the flag on hackthebox a online website to learn ethical hacking.

<h1> What's The Point? </h1>

I made this repo and this software to show proof of knowledge and where motivation can take you in terms of things, I also want to show this to my college tutors as programming is huge passion of mine and want to show that <b> I truly care </b> there's many people which will do a course for the sake of a degree what they can throw down on a CV but I want this to show effort I'm willing to put in to master the skill's I have worked on fondly for 7 Years. I don't have the best vocabulary or grammar skills so some of this will be poorly worded and I'm fully accepting of this and want to use this as working off point to become better at write-up's and other skills such as software development.

<h1> Skills I Wish To Develop </h1>

<ul>
  <li>My scripting proficiency</li>
  <li>Problem solving</li>
  <li>Motivation</li>
</ul>

<h1> Timeline </h1>

<b> Started on 12/03/2024 </b>

```
12/03/2024 15:59 BST
Introduction

Software production started to clarify the Github was not made at this concurrent time the first thing
I began to work on was thelogin page keeping an ease colour on the person's eye's so I targeted colour
scheme of grey to dark-grey, lighter grey for fore-colour and dark-grey for background-colours.
```
<img src=/images/login_1.PNG>

```
12/03/2024 16:07 BST
Font Changing

I began to realize that some font's just didn't match with the theme I was going for I wanted more sharper
and not distorted font this could be just me but I just felt like it didn't match my current theme I was
going for.

To take action on this issue I started browsing font's which appealed more easily and which one's didn't
look out of place this was quite an issue to deal with. I came to the conclusion of Yu Gothic UI also I
increased the font sizes on some objects this was because their current size didn't fit to well in
addition to this I changed the font's format from bold back to regular as that caused some not good
formatting what I didn't expect would make a major change.
```

```
12/03/2024 17:30 BST
Problem solving

There's 2 main things of U.I what needs main attention one of those is the login button and the
forgot password button. Breaking this down into sub problems brings us to being able to find services
what allow us to send short codes to verify this is them we can use service such as infobip.com to
send small phone texts or phone calls to send a code through to the individual if they have there
phone number verified.

2nd the login button can be tackled by using sql what's a C# module we can use to connect the server
up to our code this is very documented in
https://learn.microsoft.com/en-us/azure/azure-sql/database/connect-query-dotnet-core?view=azuresql
That provides how to set up connection paramaters and other essential information we need, we can
configure this at the start of the applications boot.
```
```
12/03/2024 21:16 BST
Programming the basics

With my U.I I created a flat form border style this essentially removed the option to exit and
minimize along with dragging so the application could no longer be dragged. To fix this issue
when making C# .NET software it uses the namespace System.Windows.Forms using this we can read
a documentation what list's methods, properties, functions and more we was able to gather to exit
the program we need to use the function Application.Exit(); this can be found below.

https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.application.exit?view=windowsdesktop-8.0

Next up is minimize option sadly there's no option to minimize however after noticing there was a
property for "WindowState" which displays current way the application is displayed after a quick test
we could conclude that using the code WindowState = FormWindowState.Minimized; will minimize the
application.

Next on the list is dragging cause everyone want's a dragable interface, with this my first thought
is to grab mouse's position to then move application as such. We could get mouse position using a
function known as you guessed it, MousePosition this has 2 co-ordinates the X and Y Axiz. Using this
I read more into forms and saw a "SetDesktopLocation" function this is where I then saw it took a X and a Y
Axiz using this information I wanted mouse to move to center of top bar once clicked to drag so to do this
we get the width of the form divide it by 2 this gives us the center point and take of 10 from Y axiz.

Using this information to progress. On visual studio there's an event tab image will be provided below
it's in the property listing this event tab allows you to add certain event's to the application such as
MouseUp, MouseDown this was gold mine as it means we can create a bool variable at the start of the code,
we then set bool variable to true when mouse is down and false when mouse is up. Then using the event
MoveMove we can then do if statement see if mouse is down then run the code with SetDesktopLocation
function.

here's that codes.

private void drag_MouseMove(object sender, MouseEventArgs e)
{
    if (mouseDown)
    {
        this.SetDesktopLocation(MousePosition.X-this.Size.Width/2, MousePosition.Y-10);
    }
}

the name drag is, the panel's name which I allocated at the top of application, at the top of
application I put a panel which was made to go to back and set it's colour to be same as other
elements to match the background after this I had panel fully set which I would use for my events.
```
<img src="/images/Events_Tab.PNG">

```
By double clicking one of event's textboxes which is next to description e.g MouseUp to the left
there is blank box if you double click in that location it will then make function for you and send
you to the code
```
