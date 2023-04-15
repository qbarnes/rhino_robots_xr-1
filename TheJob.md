In March of 1983, I was contacted by someone at Rhino Robots.
They were looking for a TRS-80 programmer to port their
[XR-1](http://www.theoldrobots.com/rhinoarm.html) demo software on
the Apple II over to the TRS-80.

I went to the Rhino Robots site in Champaign, IL and chatted with
who I recall was their chief scientist.  We hit it off and he hired
me.  I took a low pay amount, and in return, I was promised the
TRS-80, an XR-1 robot, and its controller on delivery.

My first paid programming job!  I was very excited!

I couldn't really start full work-time though until the current
semester was over, about mid-May.  They were okay with that.

About three weeks into it, I went in for a progress status meeting
and to my surprise found out that the chief scientist who hired me
had left the company.  With the department in disarray, I got left
on my own for several weeks.

When I had started porting the Apple II software to the TRS-80,
I quickly realized it had several problems.  The biggest was a
serious flaw in the geometric engine used to calculate the robot's
position and movements through 3D space.  The only way to correct
the problems were to abandon the existing engine and redesign a new
one from scratch.  Left on my own without any clear direction, I
proceeded with the rewrite.

Because of the engine rewrite, and all the Z-80 assembly that was
needed for smooth, real-time performance, and fixing the problems in
the Apple version, the effort took much longer than expected, around
3 months, but I finished it, so I went in to give a demo.

I explained the bugs in the geometric engine to the team and
demonstrated several manifestations for them on their Apple II XR-1
setup.  I told them my version didn't have those flaws with the new
engine.  It would now correctly compute the all motors' motions
necessary to move to each set of updated coordinates every time.

The new chief scientist wasn't happy with the delay, but was quite
pleased I found and fixed those bugs.  However, the person who I
believe was the founder/owner (Sandhu?) was not happy that I had
done that.  He appeared annoyed and angry with me.

Then the owner then asked if I could add a flag to have it do the
old behavior.  I explained that it had a totally new engine.  It
would require me to port over the old, problematic engine from
scratch and doubling the amount of the engine code.  It would also
take me some additional weeks of coding and testing.

Now onto the demo of my software. I set up the Model 3, controller,
and XR-1 that I'd been using all along for my development.  Within
seconds of starting my demo, the robot ran the programmed movements
fine but every few moments, it had brief, jarring spasms!  In all
my work, I'd never seen the robot do that before.  They were upset
with me.  I told them I'd go home and try to figure it what had gone
wrong.

I brought home the exact same computer, robot, and controller.  I
set it up and it ran my exact same test scenario again.  Just like
it had done for me at home before whenever I ran the scenario, not a
single out-of-place twitch after several hours of flawless runtime!

I called them and told them I couldn't find anything wrong and
couldn't reproduce the issue at all.  I would come back in and try
again.  Returning back to their facility, within seconds of setting
up the exact same computer, controller, and robot running the exact
same software, the spasms started all over again!

I sat with the chief scientist trying to figure out what was wrong.
I enabled my debug trace points and showed him that my software was
sending the exact proper commands to the controller at the proper
times.

As I was working with the chief scientist, the person who I thought
was the owner of the company walked by and asked if the bug was
fixed yet.  We told him, "No," and he said to me, "You're fired!"
and walked off.

The chief scientist turned to me and said, "No you're not!  You're
staying right here.  We're going to figure this out."

About 20 minutes later, the owner walked by again and said, "What
are you still doing here?  I fired you.  Get out!"  And he walked
off.

The chief scientist again asked me to stay and help him.  This went
on for a total of 7 times.  Yes, I was fired and rehired 7 times in
one day!

At the end of the day though, we had made no progress.  The robot
still had random spurts of spasms and we could find nothing else
wrong.

I explained to the chief scientist that my software was working
perfectly.  The traces proved it.  And if I took it home again,
I was confident it would continue to work perfectly for me again
there.

About 3 weeks later after I had left, the chief scientist called me
and said they found the problem.  There was an undocumented factory
test pin on the controller's RS-232 port.  On the Model 3, that pin
mapped to a non-standard parity out pin.

That made sense!  As the parity rapidly floated and changed, it
kept pushing the controller in and out of factory test mode, which
in turn threw the robot into its sporadic seizures.  I had made my
own RS-232 cable and had used it at home.  It only had the RX/TX
pins and the usual handshake and flow-control signals, nothing more.
When I was on-site, they gave me an RS-232 cable that had all 25
wires mapped through pin-to-pin!

The chief scientist said they cut the wire to the factory test pin,
my software worked perfectly, and they shipped it!

I asked if I could come in and get the Model 3, controller, and
XR-1 as was promised to me upon job completion by the original
chief scientist.  He put me on hold and talked with the unfriendly
owner.  He told me the owner said that unless I had that agreement
in writing, I was not going to get it.

That phone call was the last communication I ever had with anyone
at Rhino Robots.  I never knew what ever become of my software
beyond "it shipped".

I learned three valuable lessons from the experiences of that job:

   1) Always look deeper when a bizarre problem happens.

      This was the first time I had worked with low-volume,
      temperamental third-party hardware.  Hardware can introduce
      its own unknown quirks and variables (a/k/a "anomalies")
      that aren't immediately obvious, and that's more of an issue
      with low-volume hardware.

      Instead of being distracted by them blaming my software and
      having me focused on defending it, if I had taken a moment to
      step back, taken a breath, and looked at everything involved,
      I might have come up with the uncontrolled cable variable.

   2) People are sensitive and may not like having their mistakes
      and problems pointed out, let alone in front of others.

      Some people will look to blame others rather than be open to
      the possibility that the fault may be with the products they
      designed.

   3) Always, always, always, get any business agreements in writing!

      Not getting the computer, controller, and robot really pissed
      me off, but there was nothing I could do.  I've wondered if it
      hadn't been for me unintentionally annoying and embarrassing
      the owner, if I still would have gotten the computer and
      robot.  The guy came across as a total jerk though.  In the
      time since then, what I've learned from interacting with
      entrepreneurs, owners, and C-suite types like him, I probably
      still wouldn't have gotten the hardware no matter what.

Learning all these lessons, and so early, substantially helped me
later in my career though, and many times over.

There was a fourth lesson I wished I had recognized at the time
that I didn't pick up until working at Motorola for several years.
Hardware companies (like Rhino Robots and Motorola) often see
software as just an expensive add-on promotional gimmick to sell
their 'real' product (the hardware).  As a result, that can lead
them to overlook the intrinsic value of the software and undervalue
its creators.
