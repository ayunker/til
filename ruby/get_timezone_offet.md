# Get Timezone's UTC Offset

UTC offset for a timezone varies depending on Daylight Savings. To get the
current offset for a timezone, taking into account Daylight savings:

```
Time.current.in_time_zone('America/Chicago').utc_offset => -18000
Time.current.in_time_zone('America/Chicago').formatted_offset => '05:00'
```

NOTE:, `ActiveSupport::TimeZone['Central Time (US & Canada)'].formatted_offset`
does not take into account Daylight Savings.
