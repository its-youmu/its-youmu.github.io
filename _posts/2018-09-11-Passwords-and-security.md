---
published: false
---
# All about passwords! (and user accounts a bit too!)

This post is specifically dedicated to passwords! (and user accounts a bit!)

This blog was largely inspired by the latest [DefensiveSec podcast](https://defensivesecurity.org/defensive-security-podcast-episode-225/), so I expanded a bit.

To note as well, likely none of these ideas are new.

## Securing accounts and passwords

This gets hit to death by everyone, but I feel like I still always have questions even after reading the proposed/suggested solutions.  

First off, these guidelines and standards for an organization need to be written down, because when you eventually audit password/account policies, you want to have something to compare to.

## My past experience

As an aside, an advantage of an MSP/MSSP is them having templates to choose from, and experience from many clients being able to be applied.  Even my three years in an MSP I learned *so* much from having such a large clientbase to work with, and was able to effectively recommend solutions based on past experiences.

This is one of those things where I haven't see enough time being spent thinking about it.  Additionally, the biggest pushback I have when assisting with passwords is users.  While this isn't a surprise, I find it crazy that usability seems to still be such a huge issue.*

*I don't know a solution to this.

## Frameworks

The standards from [NIST](https://pages.nist.gov/800-63-3/sp800-63b.html) are a very good starting point to review.  Ideally, an organization will have IT staff/managers who can draw experience to make starting recommendations.

The second obvious answer is to [Google it](http://lmgtfy.com/?q=password+recommendations+for+business), but it's fairly useless and are commentary (like this!) on what people think works/doesn't work.

A third framework would be the aforementioned MSP/MSSP.  They've hashed out what works/doesn't work for their clients.  If not an MSP/MSSP, then maybe a contractor.

## Verizon DBIR

I first leanred about the DBIR through the Defensive Security podcast like two? years ago and it's been a fantastic read and gives a lot to contemplate.  I definitely feel that lessons learned being shared amongst everyone is the only way we (the 'good' guys) can make sure we figure out the best way to defend.  I feel like there's so many more publicized attacks utilizing otherwise previously trusted sources.

> "Only by sharing cybercrime information can companies and governments effectively combat cyber threats."

[Verizon Credential Theft PDF](http://www.verizonenterprise.com/resources/rp_data-breach-digest-2018-credential-theft_xg_en.pdf)
### DFIR points/counterpoints

> "Assign all users separate, unique accounts—don’t use generic or shared accounts or passwords"

This never gets explained in-depth.  Communicating to a user the need and reasoning for having secure passwords and unique accounts can be tedious.  There are a lot of considerations.

- Is the account from AD?  Can it be?
- Is SSO an option? Can you tie 2FA to it, or at least to anything web-facing?
- Permissions groups are an amazing thing - are they being utilized?  Permissions creep can be reduced/more easily managed with it
- Are personal accounts tied to anything that increases the attack surface?
- Have the password policies been reviewed recently? Not just for compliance, although you can get a two-for-one then.
- Have permissions been reviewed recently? Again, not just for compliance.

> "Set first-time passwords to a unique value for new users; require password lengths of at least eight (8), preferably more, alpha-numeric-special characters"

Agreed, and fairly standard.

> "Change user passwords immediately after the first use and then at least every 90 days"

I personally agree with [Andrew](https://twitter.com/lerg) on this; password changes are needed, but maybe not as often as 90 days.

I liked the way a few orgs implement this, where they have password expiry timers based on the user's permissions and where they work.  Have a laptop, external access to emails, etc?  Maybe every 90 days is a good policy.  Only can access anything with your password while you're on-site and on the network?  I'd say it's worth considering extending that timeframe.

> Block historical passwords from being used for at least the previous four (4) utilized passwords and set the lock-out threshold to six (6) times

Again, fairly standard.

When feasible (based on risk), certain accounts should need to be manually unlocked by an administrator.

> Remove / disable inactive user accounts at least every 90 days; immediately revoke access for terminated users

Yes on all of this.

Also, do vendors/auditors have accounts?  Are they disabled when not in use, or at least have hours tied to them?  Ideally, someone needs to call to have them activated when needed, and a set of procedures to confirm  the user(s) when they're needed.

## Last thoughts

Maybe some kind of plugin for AD that can search compromised password dumps and check against them?  I'm sure there's a tool out there like this that can securely attach to a server and check the accounts against pwned accounts/password dumps.

Also, I feel like there's a more user-friendly NIST-like framework that could be more widely distributed, updated, and accepted.

Toss me thoughts on twitter, https://twitter.com/youmusec.

Thanks for reading my first post!