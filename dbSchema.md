# (tentative) bikebump database schema

things in mind
* noSQL
* ok to have duplicates
* keep it dumb and shallow
* we will take performance
* [] elements will be an id or number 

```
/users
  /[uid]:string
    name:string
    uid:string
    avatar:string(url)

/fences
  /[fenceId]:string
    fenceId:string
    raidus:number // in meters
    /coordinate
      lat:number
      lng:number
    /questions
      /[questionId]
        /[uid]:string
          value:number
    /dings
      /[dingId]
        timestamp:number
        value:number
        uid:string

/userRoads
  /[uid]:string
    /[roadId]
      /[fenceId]:string
        fenceId:string
        radius:number
        /coordinate
          lat:number
          lng:number
        /dings
          /[dingId]
            timestamp
            value:number
            uid:string

/roads
  /[roadId]:number
    roadId:number
    name:string
    kind:string
    /geometry
      type:string
      /coordinates
        /[coordinateId]:number
          lat:number
          lng:number
    /fences
      /[fenceId]:string
        fenceId:string
        raidus:number
        /coordinate
          lat:number
          lng:number
        /dings
          /[dingId]:number
            timestamp:number
            value:number
            uid:string

/commutes
  /[commuteId]:string
    /commuteId:string
    /breadcrums
      /[breadcrumId]:string
        breadcurmId:string
        lat:number
        lng:number
        timestamp:number

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

/soundClips
  /[soundClipId]:string
    [url]:string
    timestamp:number
    [dingId] // if associated with ding

/questions
  /[questionId]:string
    questionId:string
    text:string
    /choices
      value:number
      text:string


```

