# ISO 8601 Durations

Today I learned that [ISO 8601 includes a spec for
durations](https://en.wikipedia.org/wiki/ISO_8601#Durations) as well as dates
and times.

Normally when I think of ISO 8601 I think of dates (2024-05-30) or times
(2024-05-30T19:54:14Z). 

But it also includes a spec for
[durations](https://www.digi.com/resources/documentation/digidocs/90001488-13/reference/r_iso_8601_duration_format.htm)!
Super convenient to have a standardized way to represent this, and
[rails](https://api.rubyonrails.org/classes/ActiveSupport/Duration.html#method-c-parse)
and [javascript
libraries](https://moment.github.io/luxon/api-docs/index.html#durationfromiso)
are able to parse it.

Some examples:
* 8 hours => `PT8H`
* 3.5 hours => `PT3H30M`
* 2 months, 1 day => `P2M1D`
* 6 years, 5 months, 4 days, 3 hours, 2 minutes, 1 second => `P6Y5M4DT3H2M1S`

via [Today I
Learned](https://til.hashrocket.com/posts/bpoggbasx9-iso-8601-durations)
