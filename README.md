# CommNet Relays

Ever wanted to get money for setting up CommNet network relays?  Your dreams can come true with the **CommNet Relays** contract pack!

![CommNet Relays logo](https://raw.githubusercontent.com/Kerbas-ad-astra/CommNet-Relays/master/CommNetRelaysLogo.png)

## Features

**CommNet Relays** is a contract pack for Contract Configurator which gives you contracts for each body in the solar system (besides the homeworld, of course).  The contract is to send a satellite with an appropriate dish or combination of dishes into an orbit low enough that surface missions can use the whip antenna instead of having to pack a big dish (so long as a relay is overhead, of course).  Missions to your homeworld's moons are required to use an HG-5 or equivalent, missions to the inner planets (Duna/Mars and inward) are required to use an RA-15 or equivalent, while missions to outer planets or moons will need an RA-100 or equivalent.  You also have to have your tracking station upgraded to the appropriate level.

The contracts are generated based on the lists of planets and moons in your solar system, so you can install Outer Planets or Real Solar System or whatever you want, and the contracts will automatically adjust themselves accordingly.  Additionally, the antenna requirement does not depend on specific parts, but on the combined antenna power of the relay, so it's compatible with all modded antennas automatically.  If you really wanted to (and had a computer that could handle it), you could build a relay with 20,000 HG-5 antennas for Jool missions.

(That said, be aware that the contract range requirements are based on stock CommNet ranges, which are in turn based on the stock solar system.  I've got some patches that will modify ranges to adapt to Outer Planets and Real Solar System, but those patches assume particular balance choices for antennas and the solar system.  At the end of the day, the contract requirement is just a lower bound -- check your link budgets before launch.)

In addition to the basic "relay around body X" contracts, there are a few extra contracts to help improve uptime around the network.  You may receive contracts to place relays in highly-inclined, highly-elliptical orbits around the gas giants, so that missions to their moons or in low orbits can stay in contact around them, as well as contracts to place relays in solar orbits to keep contact with probes going behind the Sun (and also the homeworld's parent body, if you're using an alternate solar system in which the homeworld is a moon).

## Dependencies

* CommNet Relays depends on [**Contract Configurator**](http://forum.kerbalspaceprogram.com/threads/101604-1-0-2-Contract-Configurator-v1-0-4-2015-05-08), version **1.22.0** or later.
* You will need [**Module Manager**](http://forum.kerbalspaceprogram.com/index.php?/topic/50533-105-module-manager-2613-november-9th/) to patch the contracts for compatibility with other addons.

## Download and install

* [**GitHub**](https://github.com/Kerbas-ad-astra/CommNet-Relays/releases)
* CurseForge

From there, just unzip the "ContractPacks/CommNetRelays" folder into your GameData directory.

## Known issues and limitations

It might be cool if nightingale implemented a coverage-checking feature like there is for RemoteTech, but as things are, I use the number of relays or relay-like vessels in orbit as a proxy -- four is the minimum to get full coverage (though that could be as low as two depending on how forgiving you've set the line-of-sight "fudge factor" to be), so if you've got five ships with enough relay antennas in low-enough orbit around a body, I figure you have coverage that's good enough and the config won't generate contracts for that body.  In general, I've left most of the details of your network unconstrained -- the minimum and/or maximum values in the requirements will keep your satellites within range of the ground, but it's up to you to put your satellites in orbits that are useful for your particular situation.

If you find any other issues, please let me know in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-CommNet-Relays-1-0-0-%282015-Jul-24%29) or on the GitHub repo's [**issue tracker**](https://github.com/Kerbas-ad-astra/CommNet-Relays/issues)!

## Version history and changelog

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
* 02017 02 25 (2.0.0): Constructing New Relays
	* Renamed to "CommNet Relays".  Because it uses the new CommNet system, it is not backwards-compatible with pre-1.2 versions of KSP or 1.x versions of AntennaRange Relays.
	* Backend logic overhauled to use new CC antenna parameter.  Specific parts are no longer required to complete contracts.
	* Adjusted some of the contract parameters to reduce duplication and increase available choices.
	* Max/min apoapses adjusted to CommNet balance.
		* Adjusted RSS patch.
		* Added OPM patch.
	* Added new "Super DSN" contract to build enormous DSN relays.  Why?  Because we can!
* 02017 07 04 (2.0.1): Hiccup Suppression
	* Adjusted facility requirements to suppress random failures when entering the Tracking Station.
* 02017 09 04 (2.0.2): De-Proliferation
	* Added 'maxSimultaneous' values for all contracts.
* 02019 01 13 (2.1.0): Global Coverage
	* Added support for localization (so the minimum KSP version supported is now 1.3.0).  Added 'title' field to agent to reduce log spam.

## Roadmap

As my schedule permits, I'll get this mod released on CurseForge and CKAN.

If you have other suggestions, please bring them up in the [**KSP forum thread**](http://forum.kerbalspaceprogram.com/threads/129704-1-0-2-4-Contract-Pack-CommNet-Relays-1-0-0-%282015-Jul-24%29) or raise an [**issue**](https://github.com/Kerbas-ad-astra/CommNet-Relays/issues) on the GitHub repo!

## Credits

Many thanks to nightingale for Contract Configurator (and for implementing the SemiMajorAxis() method at my request, and accepting my HasAntenna parameter), toadicus for AntennaRange (which inspired the initial revision of this contract pack), and Squad for implementing CommNet!

## License

CommNet Relays is copyright 2015-2019 Kerbas_ad_astra.  Contract configuration files are released under the [**GPL v3 license**](https://www.gnu.org/licenses/gpl-3.0) (or any later version).  Any redistributions must use a different name and folder (per section 7c).  All other rights (e.g. the CommNet Relays logo and agency definition files) reserved.
