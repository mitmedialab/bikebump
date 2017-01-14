# bikebump database schema
ok to have duplicates, keep it dumb and shallow = we will take performance
[] elements will be an id or number 
---
/users
  /[uid]:string
    name:string
    uid:string
    avatar:string(url)

/fences
  /[fenceId]:string
    fenceId:string
    raidus:number // in meters
    /location
      lat:number
      lng:number
    /dings
      /[dingId]
        timestamp:number
        value:number

/userDings
  /[uid]:string
    /[dingId]:string
      dingId:string
      createdAt:number
      radius:number

/ road //TODO:update

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
    /[url]:string
    /timestamp:number
    /

