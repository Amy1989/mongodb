### save
    userEnity.save(function(err, collection){
    if(err){
        return console.log(err);
      }
      console.log('添加成功!');
    });
### update
 multi:true 多条数据更新
    
    User.update({name: 'liming'}, {$set: {age: 88}}, {multi:true}, function(err, cb){
      if(err){
        return console.log(err);
      }
      console.log(cb);
    });
