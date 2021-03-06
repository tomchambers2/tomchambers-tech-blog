title: So you want to organise a hackathon...
date: 2015-05-26 23:27:20
tags:
---
I recently organised along with [Theo Papatheodorou](http://www.visualcortex.cc/) and a couple of others, an Art Hackathon in London. It was a great success and went far better than I expected. The participants were wonderful and their creations were magnificent. I initially thought it had to be really small to work since it was our first time organising this kind of event, but my co-organiser Theo’s enthusiasm swayed me into putting on a hackathon with 70 people in attendance.

I’m primarily writing this blog post for other people who are in the same situation as we were two months ago: trying to figure out what elements of the concept would work out and what resources we’d need to organise. I’ve organised the content by the main areas one has to think about.

## Organisation
You’ll need a team. For our 50 person event four people working part time would have been suitable. The workload will move from around 1-2 hours per week initially to 20 hours a week in the final stage. Make sure you assess commitment from the start, how much time are people willing to put in? The more people you have, the higher the burden of coordination, so you should make sure you know somebody is actually going to be there on the day before you make compromises as a group to suit them.

You’ll also need a good communication channel that makes it easy to share ideas, spreadsheets, documents, arrange meetings, emails. We used email, but it gets unwieldy trying to find the right threads amongst everything else. Google docs is good for sharing other information. Make a shared folder and stick everything in it. You can add more people to the folder when they join the team.
The space
The physical space is hugely important and it’s something you need to organise fairly early on, certainly before you get people signed up or start selling tickets. The place you’re in will also have an influence on other aspects like serving food, wifi access and how many people you want to have there.

If you’re running a standard software hackathon, you just need to make sure you have a good connection and plenty of power sockets. Not having either of these things will ruin the event. If it’s something hardware related, you have a much greater burden of things to provide and if the space already has these things - it might be a hackspace, workshop or education facility - then it will be a lot easier and cheaper than buying and transporting it yourself.

Don’t forget to make the space a nice place to be. Spend a little effort and money to make the place bright, colourful and fun. People are going to be there for the entire day or weekend and might then be going back to work straight after. Don’t make it a dismal grey box.

## Catering
“Thanks for not just serving pizza”, was what one guest said to me over dinner. Having decent food makes the whole thing a much more pleasant experience. Of course, food is going to be the expense that is equal or more than the physical space. Having food meant that most of the ticket price immediately went towards that. You might prefer to have the participants bring their own food. This will reduce costs a lot, but may lead to people leaving early or going elsewhere for dinner and reducing the vibe. We had a lot of people chat to each other during mealtimes and it was a good way to take the temperature of the day. Definitely don’t imagine that you’ll be able to cater for the event yourself - you’ll be too busy.

Also consider tea, coffee, juice and snacks to be available through the day. A tea urn is not too expensive to rent (we found a tea urn and coffee machine for £40). Having things like this available just make the environment a bit more pleasant and help stave off hunger if dinner is delayed.

Start looking for caterers about 1-2 months in advance. I was surprised that it was harder to find a caterer willing to cover the event than I thought. I advise going for lowest common denominator food. Don’t order stuff that people will have trouble eating like spicy food, wheat based etc. Ask your caterer how much notice they need for dietary needs and then send an email to your participants.

## Sponsorship
Getting sponsorship for an event like this is pretty difficult. We managed to get some free hardware from Tessel and Bare Conductive, but apart from that we didn’t get anything back from about 100 emails sent off to various art startups and technology companies. If you have an existing relationship will help and if a company has a community manager or outreach person, that seems to make it a lot more likely that they’ll respond, so try and talk to that person directly.

Our budget was about £2800. £2000 of that came from Ravensbourne, the other £800 from ticket sales. We spent the lot and I’m hoping that we’ll break even. The space and catering cost about £800 a piece. Don’t forget to leave contingency for on the day things - we got taxis to transport our stuff around, snacks and booze for the last day.

## Hardware/materials
Our total budget for this was £277. Most of that is non-electronics stuff since that was provided by Tessel, Ravensbourne and us from stuff we owned already. It sounds like a lot but it adds up very quickly. I was in charge of this stuff and I bought a dizzying array of items including silly string, glitter and bubble liquid.

With hindsight it wasn’t sensible to buy a whole lot of random bits and pieces. I imagined someone being inspired by a crossword toy I picked up in a junk shop, but as far as I know none of that stuff got used. If I were doing this again I’d focus more on core items that are really useful and have a good supply of them. Gaffer tape, string, paper, pens, 3.5mm speaker cables - these are all really useful things.

Another mistake I made was in the selection and presentation of the electronics. It would have been more sensible to have an easier to grok smaller selection. The way I set things up, people had to rummage through and try and find useful things or ask for what they needed. I brought along some wireless plugs and a strobe light. These would have been cool together, but they were hidden away and not obviously useful on their own.

Try and provide complete sets of things. A clearly laid out set of arduinos with power, raspberry pis with flashed SD cards and touchboards along with paint is better than a box full of some boards and a bunch of random power supplies that didn’t match up to anything. Don’t try to provide for every need, just supply what 80% of people will recognise as useful and use. Having our hardware better physically organised would have made it much easier to pack away again as well rather than just shoving it all in a bag and hoping for the best. If all the SD cards had been together for instance it would have been easier for participants to see that they existed and could be borrowed and easier for us to visually keep track.

Some of the things you lend out might be expensive. Some of ours certainly were. We relied a lot on the trust of people not to just pick things up and walk off with them. The day was hectic enough that someone could have easily done that and there wouldn’t have been much we could have done.

You need to have a policy about what you do. We decided that we would look at people’s tickets and write their name down but we never discussed how strictly this should be enforced so it ended up only just being enforced. You should answer questions like: what happens if someone comes again, do they still need to show their ticket? Does someone need to be at the table at all times? Can people rummage through things or is the stuff on a table behind the hardware manager? Can people take part of a set of tools for 5 minutes then bring it straight back? What if someone wants to chop up and solder a cable, can they do that? Very important: what’s the liability if someone breaks something. You definitely can’t determine that after the fact. If you don’t decide these things in advance you’ll end up doing whatever’s easiest.

## Internet access
Absolutely essential for a hackathon. The place you’re in needs to have absolutely rock solid wifi and preferably wired connections. Test it well in advance of the day because a problem with the internet will ruin the day in a way that most other factors won’t. Things you should test are:
can you connect easily with a range of devices
what’s the bandwidth? will it support 50 people downloading at once?
does the connection persist for the whole day? We had a problem where connections got reset every half hour
is there any corporate authentication system? How will you work around it?
can you connect with a headless device like a Raspberry Pi? Devices like these won’t be able to deal with the splash screen that some wifi providers use. Don’t test on a laptop and assume that covers everything

## Guests
I put this section lower because I didn’t feel the guests we had at our hackathon, while great people, were an essential part of the event. We could have removed them without having changed the atmosphere or success of the hackathon to any great degree. The talks added a bit of sophistication to the event, gave a good entry into it and might have inspired a few people, but they were not the bedrock and could have been replaced by some other teambuilding activity.

It also feels a little odd to have this kind of structure in such a self-led activity. Something that helps people get to know each other and is not sitting at a table in a team is definitely a good thing, but if I were doing this again I’d probably go for an unconference where participants pitch talks, set themselves up around the space and see who comes along. This would have the added bonus of giving people a chance to check out what the other participants are like before bonding forever.

I’d also suggest that talks should be very much for the purpose of inspiring participants. Artists shouldn’t talk about themselves, they’re only useful if they kick of thought processes and discussions that lead to cool projects.

We also had our guests wander round and help participants. It’s difficult for me to say with my birds eye view how this worked out, but it seems like the technical help was more important than the conceptual stuff.
Participant experience
Absolutely the number one reason to hold a hackathon is to provide a space where people can have fun and meet new people. It’s easy to lose sight of this in the weeks leading up because a lot of the work is definitely not artistic and creative.

On the day you’ll need to have people who are responsible for certain admin tasks like checking tickets and signing people in and also people who interact and take part in teams to find out who is doing well and who needs help. We had the idea that we’d be massaging participants who weren’t quite a good fit and helping teams move around. Even though we said that people could move around if they wanted to I’m not aware of anyone actually doing so.

## Hiring people
If you’ve got a reasonably sized budget it might be useful to pay some people to look after certain aspects for you. Provided you can trust that person to manage that thing and you’re spending money you have this is a great idea. Make sure that it’s something that needs little input from you and can be absolutely forgotten about. If that person needs to ask a lot of questions and needs direction then you’ve forgone the advantage of paying them in the first place. Remember that everything that needs doing like having someone take tickets means that person can’t do anything else, like get an extension lead from the car, so if everyone if busy with big tasks, little occasional tasks will pile up and become a problem.

Trust and proficiency are absolutely essential. Be very careful about who you take on. If it’s creative work, make sure to look at their portfolios and get multiple recommendations first. Sit down with the person face to face and hash out a schedule and your precise expectations.

## On the day
Prepare everything in advance. Absolutely everything you can think of. If you want to label your hardware, do that as early as possible. Go in a few days in advance and check the AV system and the internet so you can order cables or resolve problems in advance. These simple things that can be done in a relaxed way will suddenly become a nightmare if you try to sort them out while standing on the podium with a line of 8 people behind you.

The few hours from opening to starting hacking were super busy and it was really hard to keep everything organised with setting up guests, presentations, getting people checked in, setting up the hardware library. And that was with spending all Friday setting up as well.

After people formed into teams however everything settled down and there was almost nothing to do except answer questions every so often. To help resolve questions, make sure everything is communicated multiple times. Even after tweeting and emailing all participants and having a notice on the projector screen people about adding music to the collaborative Spotify playlist (highly recommended by the way) I was still asked who was in charge of the playlist.

Everything was fairly quiet for that whole period of hacking. Quiet enough that it didn’t take all four volunteers to look after it. It was useful however to have people who could spend an hour or two helping teams with technical stuff without being short staffed elsewhere. Tasks during this period included answering questions about what hardware was available and signing it out, refilling the water for the tea urn and adding songs to the playlist.

At first our teams were very intensely involved in what they were doing. I went round to take photos and ask people how they were doing and mostly got ‘mmhmm’ and ‘yeah’ when I asked how things were going. Things started to loosen up in the first evening and people became more relaxed and the atmosphere was more fun. I really didn’t think we were going to have people staying from 9:30am till 10pm and then 8am to 6pm on both days, but the majority of people actually did that and had a great time doing it.

It should be noted that dinner on the first day is the time when people who aren’t having a good time are going to leave and not come back. So if you want to deal with those issues, you need to do it in that quiet period a few hours after people have started hacking and are having a great time/not having a great time. Of course you might put it down to those individuals just not working well with others or maybe having different expectations and it’s for the best that they enjoy their Sunday doing something else rather than being convinced to spend it at your event. Either way it was harder than I expected to spot these problems and deal with them. If someone is having a bad time, what do you do? Putting them in another team is hard because teams are generally on the verge of getting too big and if they’re not working together well they might have dynamics problems of their own. I think it’s far better to extend the time at the start of the hack so that people don’t have to make immediate choices about who they want to spend the next 48 hours with.

A lot of the stuff going on was heads down laptops stuff up or small scale creation until pretty much the very end. It was really exciting to see big things pop up and things get quite frenetic in the final few hours. I would have liked to have seen more of this throughout the hackathon and get people out of their chairs, but I’m not sure of the best way to achieve it. Often the physical structures are just the superficial shell around the cool tech part that the team have been working on all weekend. So who knows.

I’m not really a fan of awards, so I was pretty skeptical about this part. It was great to have people’s presentations though and after that we had an exhibition where people could walk round, see what others had made and chat about them. This part was really important as a lot of the stuff really had to be seen in person like the VR museum.

Try and keep presentations short. 2 minutes is pretty reasonable and it’s only a taste that then lets people walk round. We had about 40 minutes for walking round, which wasn’t really long enough. It was heartbreaking to see people have to tear up the things they’d worked really hard making and literally just finished.

The middle of the hack is sacred. Absolutely don’t interrupt it except for food. People will be annoyed at being torn away from the exciting thing they’re doing. If you want to add that sort of thing make sure it’s on the beginning or the end.

So that’s it really. I highly recommend organising this kind of event. If you’re a company organising this thing, please make it free form rather than locking it down to something that benefits you. You’ll benefit from people having fun at your event much more than if you try to control the experience.

If you want any more advice please email me at tom.chambers@gmail.com. I’m very happy to answer questions on things you’re not sure will work and how to deal with particular problems.


