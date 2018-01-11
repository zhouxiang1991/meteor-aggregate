# install
```
meteor add zhoux:meteor-aggregate
```

#usage
```
import Aggregate from 'meteor/zhoux:meteor-aggregate'
const pipeline = new Aggregate();
  match({
    name: 'zhoux',
  })
  .project({
    name: 1,
    age: 1,
  })
  .append({
    $group: {
      _id: "$_id",
    }
  }).pipeline();
// [
//   {
//     $match: {
//       name: 'zhoux',
//     }
//   }
//   {
//     $project: {
//       name: 1,
//       age: 1,
//     }
//   },
//   {
//     $group: {
//       _id: '$_id',
//     }
//   }
// ]
const result = Model.aggregate(pipeline);
// aggregate.group
// aggregate.skip
// aggregate.match
// aggregate.sample
// aggregate.unwind
// aggregate.lookup
// aggregate.sort
// aggregate.limit
// aggregate.append
...
```
