SilverStripe Addressable and Geocodable Module
===============================

The Addressable/Geocodable module is an extension to Andrew Short's Addressable module (which adds address fields and geocoding to an object) to also allow for a user to manually specify a location on a google map.

Maintainer Contact
------------------
*  Mark James (<mail@mark.james.name>)

Requirements
------------
*  SilverStripe 2.4 (not compatible with 3.x)

Documentation
-------------

Quick Usage Overview
--------------------

In order to add simple address fields (address, suburb, city, postcode and
country) to an object, simply apply to `Addressable` extension:

    Object::add_extension('Object', 'Addressable');

In order to then render the full address into a template, you can use either
`$FullAddress` to return a simple string, or `$LocalisedFullAddressHTML` to render
the address into one of the address templates.

To add automatic geocoding to an `Addressable` object when the address is
changed, simple apply the `Geocodable` extension:

    Object::add_extension('Object', 'Geocodable');

This will then use the Google Maps API to translate the address into a latitude
and longitude on save, and save it into the `Lat` and `Lng` fields.

You can define a global set of allowed states or countries using
`Addressable::set_allowed_states()` and `::set_allowed_countries()`
respectively. These can also be set per-instance using `setAllowedStates()` and
`setAllowedCountries()`.

If a single string is provided as a value, then this will be set as the field
for all new objects and the user will not be presented with an input field. If
the value is an array, the user will be presented with a dropdown field.
