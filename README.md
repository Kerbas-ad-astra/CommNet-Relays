#AntennaRange Relays

Ever wanted to get money for setting up AntennaRange network relays?  Your dreams can come true with the **AntennaRange Relays** contract pack!

##Features

**AntennaRange Relays** is a contract pack for Contract Configurator which gives you contracts for each body in the solar system (besides the homeworld, of course).  The contract is to send a satellite with an appropriate dish into an orbit low enough that surface missions can use the whip antenna instead of having to pack a big dish (so long as a relay is overhead, of course).  Missions to your homeworld's moons or the inner planets (Duna/Mars) are required to use a DTS-M1, while missions to outer planets or moons get the Communotron 88-88.  You also have to have your tracking station upgraded to the appropriate level.

The contracts are generated based on the lists of planets and moons in your solar system, so you can install Outer Planets or Real Solar System or whatever you want, and the contracts will automatically adjust themselves accordingly.  (Be aware that the contracts are based on stock AntennaRange ranges, which are in turn based on the stock solar system.  Outer Planets adjusts the 88-88 to have a longer range, but I don't know about RSS, for example.)

In addition to the basic "relay around body X" contracts, there are a few extra contracts to help improve uptime around the network.  You may receive contracts to place relays in highly-inclined, highly-elliptical orbits around the gas giants, so that missions to their moons or in low orbits can stay in contact around them, as well as contracts to place relays in solar orbits to keep contact with probes going behind the Sun (and also the homeworld's parent body, if you're using an alternate solar system in which the homeworld is a moon).

##Dependencies

* AntennaRange Relays depends on [Contract Configurator](http://forum.kerbalspaceprogram.com/threads/101604-1-0-2-Contract-Configurator-v1-0-4-2015-05-08), version 1.2.2 or later.

##Recommended addons

* Although it's not strictly necessary for the contracts to work, there wouldn't be much point in doing these missions without [AntennaRange](http://forum.kerbalspaceprogram.com/threads/56440-1-0-AntennaRange-1-8-Enforce-and-Encourage-Antenna-Diversity).

##Download and install

* CurseForge
* KerbalStuff
* [GitHub](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/releases)

From there, just unzip the "ContractPacks/AntennaRangeRelays" folder into your GameData directory.

##Known issues and limitations

You can harvest money by setting up one relay around a planet, and switching to that relay when more contracts come up to put relays around that planet. Is there a way to set the "must be a new ship after accepting the contract" requirement for a Contract Configurator pack?  On the other hand, if a contract comes up while there's a qualifying mission on its way to a planet, I don't want to prevent you from getting credit for it.  What are your thoughts?

Also, these contracts were written with the three stock antennas in mind only.  You will need a Module Manager patch to add some more part validation checks for whatever antennas you want for the job, like so:

```
@CONTRACT_TYPE[AntennaRangeRelayWhatever] // You could use "AntennaRangeRelay*" to get all contract types at once, but they have different range needs, so think about where your antenna fits.  It's okay to put longer-range antennas in shorter-range missions, but definitely not vice-versa!
{
	@PARAMETER[Antennas]
	{
		PARAMETER // note the lack of an "@" here, since we're adding a new parameter!
		{
			name = PartValidation
			type = PartValidation
			part = whatever_antenna_you_want_to_qualify
		}
	}
}
```

If you find any other issues, please let me know in the KSP thread or on the GitHub repo's [issue tracker](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/issues)!

##Version history and changelog

* 2015 07 26: Initial release.

##Roadmap

I'm pretty happy with this set of contracts, though it might be cool if nightingale implemented a coverage-checking feature like RemoteTech has.  As it is, I use the number of vessels in orbit as a proxy -- four is the minimum to get full coverage, so if you've got four ships in low-enough orbit around a body, I figure you have coverage that's good enough and the config won't generate contracts for that body.

Of course, once stock has antenna ranges, I'll update these contracts to work with the new system.

If you have other suggestions, please leave them here or raise an [**issue**](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/issues) on the GitHub repo!

##Credits

Thanks to nightingale for Contract Configurator and toadicus for AntennaRange!

##License

AntennaRange Relays is copyright 2015 Kerbas_ad_astra.  Contract configuration files are released under the [Apache 2.0 license](https://www.apache.org/licenses/LICENSE-2.0).  All other rights (e.g. the AntennaRange Relays logo) reserved.
