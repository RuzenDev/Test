> iso_string = "2023-02-10T08:30:00.000Z-06:00"
> date_components = iso_string.match(/(\d{4})-(\d{2})-(\d{2})T(\d{2}):(\d{2}):(\d{2})\.(\d{3})Z(.*)/)
> year = parseInt(date_components[1])
> month = parseInt(date_components[2]) - 1
> day = parseInt(date_components[3])
> hour = parseInt(date_components[4])
> minute = parseInt(date_components[5])
> second = parseInt(date_components[6])
> milliseconds = parseInt(date_components[7])
> date = new Date(Date.UTC(year, month, day, hour, minute, second, milliseconds))
> db.mycollection.insert({"datetime_field": date})
