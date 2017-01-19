# (tentative) bikebump database schema

things in mind
* noSQL
* ok to have duplicates
* keep it dumb and shallow
* we will take performance
* [] elements will be an id or number 

```
/users *
  /[uid]:string
    name:string
    uid:string
    avatar:string(url)

/dings *
  /[dingId]:string
    dingId:string
    roadId:number // closestRoad
    raidus:number // in meters
    /coordinate
      lat:number
      lng:number
    /timestamps
      /[timestamp]:number
        timestamp:number
        value:number
        uid:string

/roads *  // converted from OSM xml
  /[roadId]:number
    roadId:number
    name:string
    kind:string
    highway:string
    motor_cycle:string
    bicycle:string
    cycleway:string
    foot:string
    /dings
      /[dingId]:string
        /coordinate
          lat:number
          lng:number
    /geometry
      type:string
      /coordinates
        /[coordinateId]:number
          lat:number
          lng:number
        
/commutes
  /[commuteId]:string
    commuteId:string
    uid:string
    /timestamps
      /[timestamp]:number
        timestamp:number
        lat:number
        lng:number

/userCommutes
  /[uid]:string
    /[commuteId]:string
      /commuteId:string
      /breadcrumbs
        /[breadcurmbId]:string
          breadcrumbId:string
          lat:number
          lng:number
          timestamp:number

/soundClips *
  /[soundClipId]:string
    [url]:string
    timestamp:number
    [dingId] // if associated with ding


```

