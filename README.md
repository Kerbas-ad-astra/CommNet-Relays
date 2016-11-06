#CommNet Relays

Ever wanted to get money for setting up CommNet network relays?  Your dreams can come true with the **CommNet Relays** contract pack!

![CommNet Relays logo](https://raw.githubusercontent.com/Kerbas-ad-astra/CommNet-Relays/master/CommNetRelaysLogo.png)

##Features

**CommNet Relays** is a contract pack for Contract Configurator which gives you contracts for each body in the solar system (besides the homeworld, of course).  The contract is to send a satellite with an appropriate dish into an orbit low enough that surface missions can use the whip antenna instead of having to pack a big dish (so long as a relay is overhead, of course).  Missions to your homeworld's moons or the inner planets (Duna/Mars) are required to use an RA-15 or equivalent, while missions to outer planets or moons will need an RA-100 or equivalent.  You also have to have your tracking station upgraded to the appropriate level.

The contracts are generated based on the lists of planets and moons in your solar system, so you can install Outer Planets or Real Solar System or whatever you want, and the contracts will automatically adjust themselves accordingly.  Be aware that the contracts are based on stock CommNet ranges, which are in turn based on the stock solar system.  I've Outer Planets adjusts the 88-88 to have a longer range, and RSS increases the range of everything (I submitted that patch, and I've also included a patch in CommNet Ranges starting in v1.1 to adjust contract ranges accordingly), but I don't know about anything else.

In addition to the basic "relay around body X" contracts, there are a few extra contracts to help improve uptime around the network.  You may receive contracts to place relays in highly-inclined, highly-elliptical orbits around the gas giants, so that missions to their moons or in low orbits can stay in contact around them, as well as contracts to place relays in solar orbits to keep contact with probes going behind the Sun (and also the homeworld's parent body, if you're using an alternate solar system in which the homeworld is a moon).

##Dependencies

* CommNet Relays depends on [**Contract Configurator**](http://forum.kerbalspaceprogram.com/threads/101604-1-0-2-Contract-Configurator-v1-0-4-2015-05-08), version **1.21.2** or later.
* You will need [**Module Manager**](http://forum.kerbalspaceprogram.com/index.php?/topic/50533-105-module-manager-2613-november-9th/) to patch the contracts for compatibility with other addons.

##Download and install

* [**GitHub**](https://github.com/Kerbas-ad-astra/CommNet-Relays/releases)
* CurseForge

From there, just unzip the "ContractPacks/CommNetRelays" folder into your GameData directory.

##Known issues and limitations

It might be cool if nightingale implemented a coverage-checking feature like there is for RemoteTech, but as things are, I use the number of relays or relay-like vessels in orbit as a proxy -- four is the minimum to get full coverage (though that could be as low as two depending on how forgiving you've set the line-of-sight "fudge factor" to be), so if you've got five ships with enough relay antennas in low-enough orbit around a body, I figure you have coverage that's good enough and the config won't generate contracts for that body.  In general, I've left most of the details of your network unconstrained -- the minimum and/or maximum values in the requirements will keep your satellites within range of the ground, but it's up to you to put your satellites in orbits that are useful for your particular situation.

If you find any other issues, please let me know in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-CommNet-Relays-1-0-0-%282015-Jul-24%29) or on the GitHub repo's [**issue tracker**](https://github.com/Kerbas-ad-astra/CommNet-Relays/issues)!

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
* 2016 07 23 (1.4): Mission Control
	* Changes to support Contract Configurator's 1.15.3 update.
		* Because this depends on variables introduced in CC 1.15.3, **this and later versions are no longer compatible with KSP 1.1.0-2.**
	* Contracts are broken out into individual cfg files (I got tired of scrolling all over the place when editing...)
	* The license is changed to the GPL v3 (or later).
* 02016 11 XX (2.0): Constructing New Relays
	* Renamed to "CommNet Relays".
	* Reworked contracts to use new CC antenna parameter -- specific parts are no longer required, just use enough relay antennas to get the job done.
	* Adjusted some of the contract parameters to reduce duplication and increase available choices.
	* Max/min apoapses adjusted to CommNet balance.
		* Added OPM balance patch.
	* Added new "Super DSN" contract to build enormous DSN relays.  Why?  Because we can!

##Roadmap

As my schedule permits, I'll get this mod released on CurseForge and CKAN in the near future.

If you have other suggestions, please bring them up in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-CommNet-Relays-1-0-0-%282015-Jul-24%29) or raise an [**issue**](https://github.com/Kerbas-ad-astra/CommNet-Relays/issues) on the GitHub repo!

##Credits

Thanks to nightingale for Contract Configurator (and for implementing the SemiMajorAxis() method at my request) and toadicus for CommNet!

##License

CommNet Relays is copyright 2015-2016 Kerbas_ad_astra.  Contract configuration files are released under the [**GPL v3 license**](https://www.gnu.org/licenses/gpl-3.0) (or any later version).  Any redistributions must use a different name and folder (per section 7c).  All other rights (e.g. the CommNet Relays logo and agency definition files) reserved.
