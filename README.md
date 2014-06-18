# This is a git readme

This is how you git

pipeline = [{
    '$match': {
        'ts': {'$gte': dt,
                '$lt': dt + timedelta(hours=1)},
        # Valid samples.
        'airTemperature.quality': '1'
    }
}, {
    '$group': {
        '_id': '$st',
        'position': {
            '$first': '$position'},
        'airTemperature': {
            '$first': '$airTemperature'}}}]

cursor = db.data.aggregate(pipeline, cursor={})
