# Aggregated guides on NXDN and Kenwood-specific NXDN codeplugging

Entering into the digital voice world is a blessing for me, in my humble opinion.  Anyhow, NXDN is one other compared to DMR: no way to look around to help me setup, much to my dismay.  So, this is where I stumble over the world of NXDN and, in the process, program and use my Kenwood with it.

## Background

As for my setup, I'm currently using an MMDVM_HS_HAT configured in WPSD as DMR hotspot for my Baofeng DM-32UV and Motorola XiR C2620.  This hotspot configuration could work for NXDN as well, with a few software configuration (note: shell access is necessary, but not entirely mandatory).

There's also a MMDVM_HS_Dual_HAT laying around: terrible RX recepetion is why it's gathering dust right now.  But it will come in handy soon...

The target is to connect my NXDN radio: Kenwood NX-820-E.  Obviously, my codeplug software may not compatible with your Kenwood, but some settings may share similarities.

## Disclaimer

I am not responsible for the bricking of your radio.

Also, I would suggest you contact your dealer for a copy of Kenwood codeplug software.

## Checklists for Kenwood hotspot connection

1. Obviously, [you need an NXDN ID from RadioID](https://radioid.net).

2. There are excelent guides on the Internet to help you setting up Pi-Star or WPSD for DMR if you haven't done that.  Note the frequencies that you configured, you will be needing that later.

3. Basicly, [This](https://nxdnscotland.wordpress.com/nxdn-via-pi-star/) is one of the simplest getting started to enable NXDN on Pi-Star (WPSD would be similar).  **Remember to note down the NXDN RAN, you will be needing it later.**

4. **Disable DMR mode on your Pi-Star**, or create a new profile for NXDN then disable DMR from Configuration if you are on WPSD.  I find it helpful if you need to troubleshoot your NXDN radio connection later (foreshadowing).

5. You should have a copy of the compatile Kenwood codeplug software and installed it on your Windows PC by now (sorry, all CPS software that I found are run on Windows, except open-source ones which are unsupported btw; if that's not your cup of tea, maybe considering DMR with DM-32UV and qdmr CPS instead).

6. You should, by now, also have a comaptible codeplug cable for your Kenwood radio as well.  They could be obtained for cheap, or use the Kenwood dealership.

5. [Kenwood NX-820 simplex codeplug](/Kenwood_simplex.md).  I'll get back to you if I successfully configured it for duplex mode.

## Connecting your NXDN over DMR network

**!NOTICE!  Please read the rules and guidelines carefully regarding the DMR talkgroup you are trying to connect to.  Not all talkgroups allow you to just simply connect the transcoder to their stream.**

TODO: I am still figuring it out, as WPSD does not supported it (yet?).

## Licensing and credits

_To puut it simply:_ you can share it anyways you like, just please reference rightly, and give the credits where it was due to these following great contributors:

- [G4KLX](https://www.qrz.com/db/G4KLX) for creating everything around [MMDVM](https://github.com/g4klx);
- [MW0MWZ](https://www.qrz.com/db/MW0MWZ) for creating [Pi-Star](https://pistar.uk)
- [W0CHP](https://www.qrz.com/db/W0CHP) for spearheading forward with [WPSD](https://w0chp.radio/wpsd), among other projects.

