#AntennaRange Relays

Ever wanted to get money for setting up AntennaRange network relays?  Your dreams can come true with the **AntennaRange Relays** contract pack!

![AntennaRange Relays logo](https://raw.githubusercontent.com/Kerbas-ad-astra/AntennaRange-Relays/master/AntennaRangeRelaysLogo.png)

##Features

**AntennaRange Relays** is a contract pack for Contract Configurator which gives you contracts for each body in the solar system (besides the homeworld, of course).  The contract is to send a satellite with an appropriate dish into an orbit low enough that surface missions can use the whip antenna instead of having to pack a big dish (so long as a relay is overhead, of course).  Missions to your homeworld's moons or the inner planets (Duna/Mars) are required to use a DTS-M1, while missions to outer planets or moons get the Communotron 88-88.  You also have to have your tracking station upgraded to the appropriate level.

The contracts are generated based on the lists of planets and moons in your solar system, so you can install Outer Planets or Real Solar System or whatever you want, and the contracts will automatically adjust themselves accordingly.  (Be aware that the contracts are based on stock AntennaRange ranges, which are in turn based on the stock solar system.  Outer Planets adjusts the 88-88 to have a longer range, but I don't know about RSS, for example.)

In addition to the basic "relay around body X" contracts, there are a few extra contracts to help improve uptime around the network.  You may receive contracts to place relays in highly-inclined, highly-elliptical orbits around the gas giants, so that missions to their moons or in low orbits can stay in contact around them, as well as contracts to place relays in solar orbits to keep contact with probes going behind the Sun (and also the homeworld's parent body, if you're using an alternate solar system in which the homeworld is a moon).

##Dependencies

* AntennaRange Relays depends on [**Contract Configurator**](http://forum.kerbalspaceprogram.com/threads/101604-1-0-2-Contract-Configurator-v1-0-4-2015-05-08), version 1.5.1 or later.

##Recommended addons

* Although it's not strictly necessary for the contracts to work, there wouldn't be much point in doing these missions without [**AntennaRange**](http://forum.kerbalspaceprogram.com/threads/56440-1-0-AntennaRange-1-8-Enforce-and-Encourage-Antenna-Diversity).

##Download and install

* CurseForge
* KerbalStuff
* [**GitHub**](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/releases)

From there, just unzip the "ContractPacks/AntennaRangeRelays" folder into your GameData directory.

##Known issues and limitations

These contracts were written with the three stock antennas in mind only.  You will need a Module Manager patch to add some more part validation checks for whatever antennas you want for the job, like so:

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

It might be cool if nightingale implemented a coverage-checking feature like there is for RemoteTech, but as things are, I use the number of vessels in orbit as a proxy -- four is the minimum to get full coverage (though that could be as low as two depending on how forgiving you've set the line-of-sight "fudge factor" to be, or one if you're not using LOS at all), so if you've got five ships in low-enough orbit around a body, I figure you have coverage that's good enough and the config won't generate contracts for that body.  In general, I've left most of the details of your network unconstrained -- the minimum and/or maximum values in the requirements will keep your satellites within range of the ground, but it's up to you to put your satellites in orbits that are useful for your particular situation.

If you find any other issues, please let me know in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-AntennaRange-Relays-1-0-0-%282015-Jul-24%29) or on the GitHub repo's [**issue tracker**](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/issues)!

##Version history and changelog

* 2015 07 24: Initial release.
* 2015 07 25 (1.0.1): Added NewVessel parameter to missions, so each relay will have to be a newly-launched satellite.  Bumped up the maximum number of satellites from four to five (to give some redundancy).

##Roadmap

As my schedule permits, I'll get this mod released on KerbalStuff and CurseForge in the near future.

Of course, once stock has antenna ranges, I'll update these contracts to work with the new system.

If you have other suggestions, please bring them up in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-AntennaRange-Relays-1-0-0-%282015-Jul-24%29) or raise an [**issue**](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/issues) on the GitHub repo!

##Credits

Thanks to nightingale for Contract Configurator (and for implementing the SemiMajorAxis() method at my request) and toadicus for AntennaRange!

##License

AntennaRange Relays is copyright 2015 Kerbas_ad_astra.  Contract configuration files are released under the [**Apache 2.0 license**](https://www.apache.org/licenses/LICENSE-2.0).  All other rights (e.g. the AntennaRange Relays logo) reserved.
