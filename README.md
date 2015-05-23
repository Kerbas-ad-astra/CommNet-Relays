#AntennaRange Relays

Ever wanted to send relays to begin your AntennaRange networks...and get money for it?  Your wish will be fulfilled with the **AntennaRange Relays** contract pack!

##Features

**AntennaRange Relays** is a contract pack for Contract Configurator which gives you contracts for each body in the solar system (besides the homeworld, of course).  The contract is to send a satellite with an appropriate dish into an orbit low enough that surface missions (or atmospheric missions, in the case of gas giants) can use the whip antenna instead of having to pack a big dish (so long as the relay is overhead, of course).  Missions to your homeworld's moons are required to use a DTS-M1, while missions to other planets or moons get the Communotron 88-88.  You may also get contracts to put a relay in an inclined and eccentric orbit over a gas giant, so that missions can use it to talk "around" the planet.

The contracts are generated based on the lists of planets and moons in your solar system, so you can install Outer Planets or Real Solar System or whatever you want, and the contracts will automatically adjust themselves accordingly.  (They will *not* adjust to whatever antennas you have installed, however.  You will need a Module Manager patch to OR together some more part validation checks for whatever antennas you want for the job.)

##Dependencies

* AntennaRange Relays depends on [Contract Configurator](http://forum.kerbalspaceprogram.com/threads/101604-1-0-2-Contract-Configurator-v1-0-4-2015-05-08).

##Recommended addons

* Although it's not strictly necessary for the contracts to work, there wouldn't be much point in doing these missions without [AntennaRange](http://forum.kerbalspaceprogram.com/threads/56440-1-0-AntennaRange-1-8-Enforce-and-Encourage-Antenna-Diversity).

##Download and install

* CurseForge
* KerbalStuff
* GitHub

From there, just unzip the "ContractPacks/AntennaRangeRelays" folder into your GameData directory.

##Known and anticipated issues

None at this time.  If you find any, please let me know in the KSP thread or on the GitHub repo's [issue tracker](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/issues)!

##Version history and changelog

* 2015 XX: Initial release.

##Roadmap

In the long run, it might be cool if the Contract Configurator system could track AntennaRange coverage like it does RemoteTech coverage.  Unless or until that happens, I'm interested in your input on better ways to track coverage. Right now I use the number of ships in orbit around a body as a proxy, figuring that four is the minimum required for total coverage, and so if you have fewer than four ships around a body, you might get a contract to place a relay.  (nightingale may be adding a feature to allow a contract to search each ship by parts, so that it can count how many ships you have with dishes on, but I'm not sure why you'd send a ship without an antenna if you're using AntennaRange, so I don't think the extra overhead is worth it.)  It would be *really* cool to suggest orbits, but I think I'd either have to "bake in" orbits for each planet (not happening, not general enough) or have to write a custom plugin (not happening anytime soon).

##Credits

Thanks to nightingale for Contract Configurator and toadicus for AntennaRange!

##License

AntennaRange Relays is copyright 2015 Kerbas_ad_astra and released under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0).
