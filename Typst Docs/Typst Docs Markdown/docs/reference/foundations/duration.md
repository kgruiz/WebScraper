  * [ ![Docs](/assets/icons/16-docs-dark.svg) ](/docs)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Reference ](/docs/reference/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Foundations ](/docs/reference/foundations/)
  * ![](/assets/icons/16-arrow-right.svg)
  * [ Duration ](/docs/reference/foundations/duration/)

#  duration

Represents a positive or negative span of time.

##  Constructor

Question mark

If a type has a constructor, you can call it like a function to create a new
value of the type.

Creates a new duration.

You can specify the [ duration ](/docs/reference/foundations/duration/
"duration") using weeks, days, hours, minutes and seconds. You can also get a
duration by subtracting two [ datetimes
](/docs/reference/foundations/datetime/) .

duration  (

seconds  :  [ int ](/docs/reference/foundations/int/) ,  minutes  :  [ int
](/docs/reference/foundations/int/) ,  hours  :  [ int
](/docs/reference/foundations/int/) ,  days  :  [ int
](/docs/reference/foundations/int/) ,  weeks  :  [ int
](/docs/reference/foundations/int/) ,

)  -> [ duration ](/docs/reference/foundations/duration/)

    
    
    #duration(
      days: 3,
      hours: 12,
    ).hours()
    

![Preview](/assets/docs/GmG9JKsQZEqcWXCc52iIiQAAAAAAAAAA.png)

####  ` seconds `

[ int ](/docs/reference/foundations/int/)

The number of seconds.

Default: ` 0  `

####  ` minutes `

[ int ](/docs/reference/foundations/int/)

The number of minutes.

Default: ` 0  `

####  ` hours `

[ int ](/docs/reference/foundations/int/)

The number of hours.

Default: ` 0  `

####  ` days `

[ int ](/docs/reference/foundations/int/)

The number of days.

Default: ` 0  `

####  ` weeks `

[ int ](/docs/reference/foundations/int/)

The number of weeks.

Default: ` 0  `

##  Definitions

Question mark

Functions and types and can have associated definitions. These are accessed by
specifying the function or type, followed by a period, and then the
definition's name.

###  ` seconds `

The duration expressed in seconds.

This function returns the total duration represented in seconds as a floating-
point number rather than the second component of the duration.

self  .  seconds  (

)  -> [ float ](/docs/reference/foundations/float/)

###  ` minutes `

The duration expressed in minutes.

This function returns the total duration represented in minutes as a floating-
point number rather than the second component of the duration.

self  .  minutes  (

)  -> [ float ](/docs/reference/foundations/float/)

###  ` hours `

The duration expressed in hours.

This function returns the total duration represented in hours as a floating-
point number rather than the second component of the duration.

self  .  hours  (

)  -> [ float ](/docs/reference/foundations/float/)

###  ` days `

The duration expressed in days.

This function returns the total duration represented in days as a floating-
point number rather than the second component of the duration.

self  .  days  (

)  -> [ float ](/docs/reference/foundations/float/)

###  ` weeks `

The duration expressed in weeks.

This function returns the total duration represented in weeks as a floating-
point number rather than the second component of the duration.

self  .  weeks  (

)  -> [ float ](/docs/reference/foundations/float/)

[ ![â](/assets/icons/16-arrow-right.svg) Dictionary  Previous page
](/docs/reference/foundations/dictionary/) [ ![â](/assets/icons/16-arrow-
right.svg) Evaluate  Next page  ](/docs/reference/foundations/eval/)

