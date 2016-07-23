#AntennaRange Relays

Ever wanted to get money for setting up AntennaRange network relays?  Your dreams can come true with the **AntennaRange Relays** contract pack!

![AntennaRange Relays logo](https://raw.githubusercontent.com/Kerbas-ad-astra/AntennaRange-Relays/master/AntennaRangeRelaysLogo.png)

##Features

**AntennaRange Relays** is a contract pack for Contract Configurator which gives you contracts for each body in the solar system (besides the homeworld, of course).  The contract is to send a satellite with an appropriate dish into an orbit low enough that surface missions can use the whip antenna instead of having to pack a big dish (so long as a relay is overhead, of course).  Missions to your homeworld's moons or the inner planets (Duna/Mars) are required to use a DTS-M1, while missions to outer planets or moons get the Communotron 88-88.  You also have to have your tracking station upgraded to the appropriate level.

The contracts are generated based on the lists of planets and moons in your solar system, so you can install Outer Planets or Real Solar System or whatever you want, and the contracts will automatically adjust themselves accordingly.  Be aware that the contracts are based on stock AntennaRange ranges, which are in turn based on the stock solar system.  Outer Planets adjusts the 88-88 to have a longer range, and RSS increases the range of everything (I submitted that patch, and I've also included a patch in AntennaRange Ranges starting in v1.1 to adjust contract ranges accordingly), but I don't know about anything else.

In addition to the basic "relay around body X" contracts, there are a few extra contracts to help improve uptime around the network.  You may receive contracts to place relays in highly-inclined, highly-elliptical orbits around the gas giants, so that missions to their moons or in low orbits can stay in contact around them, as well as contracts to place relays in solar orbits to keep contact with probes going behind the Sun (and also the homeworld's parent body, if you're using an alternate solar system in which the homeworld is a moon).

##Dependencies

* AntennaRange Relays depends on [**Contract Configurator**](http://forum.kerbalspaceprogram.com/threads/101604-1-0-2-Contract-Configurator-v1-0-4-2015-05-08), version 1.15.3 or later.
* You will need [**Module Manager**](http://forum.kerbalspaceprogram.com/index.php?/topic/50533-105-module-manager-2613-november-9th/) to patch the contracts for compatibility with other addons.

##Recommended addons

* Although it's not strictly necessary for the contracts to work, there wouldn't be much point in doing these missions without [**AntennaRange**](http://forum.kerbalspaceprogram.com/threads/56440-1-0-AntennaRange-1-8-Enforce-and-Encourage-Antenna-Diversity).

##Download and install

* [**GitHub**](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/releases)
* CurseForge

From there, just unzip the "ContractPacks/AntennaRangeRelays" folder into your GameData directory.

##Known issues and limitations

Each contract requires specific antenna parts -- the stock antennas by default, and a few from some mods that I use or have used (Hangar and SSR Microsat) via some Module Manager patches.  I'm happy to accept more, but I will only ship patches for mods that ship "natively" with AntennaRange patches themselves and which have antennas whose ranges are long enough to be useful as relays.  If you want to add patches for more addons, you can make them like this (and feel free to share them in this thread):

```
@CONTRACT_TYPE[AntennaRangeRelayWhatever] // You could use "AntennaRangeRelay*" to get all contract types at once, but they have different range needs, so think about where your antenna fits.  It's okay to allow longer-range antennas to qualify for shorter-range missions, but definitely not vice-versa!
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
* 2015 08 08 (1.1): RSS and New Horizons compatibility.
	* Moved altitude constraints into DATA nodes so that Module Manager can affect them more easily (as opposed to having magic numbers in both the orbit parameter and the target planet selection logic).
	* Fixed some initial "Escape"/"Orbit" requirements -- they were referring to "Kerbin" specifically, now referring to whatever the homeworld is.
	* Also updated comments on target planet selection logic to match the actual logic used.
	* Added a new "CoMoon" contract to be used when the homeworld is a moon.
* 2015 12 14 (1.2): Antenna pack compatibility
	* New patches that allow antennas from some addons (Asteroid Day, Hangar, SSR Microsat, USI Kolonization Systems) to qualify for the contracts.
	* Clarified contract wording.
	* Added a dedicated agency to give the contracts.
* 2016 05 03 (1.3): Antenna rearrangement
	* Moved High Gain Antenna from its own patch, now that the Asteroid Day probe parts are folded into stock.
		* Because this will cause errors on pre-1.1 installs without Asteroid Day, **this and later versions are no longer compatible with KSP 1.0.x.**
	* Removed the USI patch, since it was causing exceptions for MKS Lite users.
	* Compatible through KSP 1.1.2.
* 2016 06 26 (1.3.1): Expression expansion
	* Refactored targetbody expressions to reduce calculations-per-frame when contracts are generated.
	* Compatible through KSP 1.1.3.
* 2016 08 XX (1.4): Mission Control
	* Changes to support Contract Configurator's 1.15.3 update.
		* Because this depends on variables introduced in CC 1.15.3, **this and later versions are no longer compatible with KSP 1.0.0-2.**
	* Contracts broken out into individual cfg files (I got tired of scrolling all over the place when editing...)
		* Because of the level of time and effort I've sunk into this project, not to mention its length, I'm changing the license to the GPL v3 (or later).

##Roadmap

As my schedule permits, I'll get this mod released on CurseForge and CKAN in the near future.

Of course, once stock has antenna ranges, I'll update these contracts to work with the new system.

If you have other suggestions, please bring them up in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-AntennaRange-Relays-1-0-0-%282015-Jul-24%29) or raise an [**issue**](https://github.com/Kerbas-ad-astra/AntennaRange-Relays/issues) on the GitHub repo!

##Credits

Thanks to nightingale for Contract Configurator (and for implementing the SemiMajorAxis() method at my request) and toadicus for AntennaRange!

##License

AntennaRange Relays is copyright 2015-2016 Kerbas_ad_astra.  Contract configuration files are released under the [**GPL v3 license**](https://www.gnu.org/licenses/gpl-3.0) (or any later version).  All other rights (e.g. the AntennaRange Relays logo and agency definition files) reserved.
