## 连接数据库
var mongoose = require('mongoose');
var db = mongoose.connect('mongodb://localhost/test');
## 创建schema
   var userSchema = db.Schema({
      name: String,
      age: Number
    });
## 创建model
var User = db.model('User', userSchema);


## save
  报存的时候先创建实体
    var userEnity = new User({
      name: 'liming',
      age: '22'
    })
    userEnity.save(function(err, collection){
    if(err){
        return console.log(err);
      }
      console.log('添加成功!');
    });
## update
 multi:true 多条数据更新
    
    User.update({name: 'liming'}, {$set: {age: 88}}, {multi:true}, function(err, cb){
      if(err){
        return console.log(err);
      }
      console.log(cb);
    });
