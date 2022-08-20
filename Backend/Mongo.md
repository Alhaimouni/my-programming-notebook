how to show my mongodb contents :

1- start mongodb : sudo service mongodb start // should see [ OK ].
2- see monog status : mongo  // should see the status and version.
3- we are inside mongo , write show dbs to see all the dbs we have.
4- if u want to go insde one of dbs we have , write use <db name>.
5- how to show what inside the db , write show collections.
6- db.<collection name>.find()   or db.<collection name>.find().pretty()

==========================================================================================================================
https://mongoosejs.com/docs/index.html  note: how to use mongoose 
==========================================================================================================================
we can add new db using - use <new db name> - note: if i do show dbs i cant see it cuz its empty
==========================================================================================================================
mongoose.connect('mongodb://localhost:27017/<db name>')  note: connect my api with specific db in mongo until i make a model
==========================================================================================================================

note : to create a new collection we need two things (schema and model)

const x  = new mongoose.Schema({
name : String,
age : String
});

let yModel = mongoose.model('collectionName',x<schema name>);

let newData = new yModel({name:'ahmad',age:'20'});

yModel.find({},(error, result)=>{(error)? : res.send(result)}) //requist from api server to mongo db 

.find() //always returns an array
==========================================================================================================================
let person2 = new yModel({name:'ali',age:'27'})
person2.save()   
بدل م اعمل شخص واعمل بعديها حفظ ممكن ابدل هالخطوتين بخطوه وحده اسمها 
create
y.Model.create({name:'ali',age:'27'}) 
هاي الحركه عملت نفس الي فوق تماما 
==========================================================================================================================
.save()
.create()    
باخدوا وقت ف ممكن اعمل معهم اذا طلب الامر 
(async/await) or .then
==========================================================================================================================
//axios.post(<endpoint>,<body object>)
==========================================================================================================================
from react : 
let obj = { name : 'ahmad' , age : 25 , hoppy : 'motors'}
let url = `http://localhost:3001/test`;
let axiosRes = axios.post(url,obj)

from server :
server.post(/test,handleTest);

function handleTest(req, res) {
	let {name, age, hoppy} = req.body; // req.body will be undefinde until i parse it by using server.use(express.json())
	//server.use(express.json()) called middleware to decode any request body to json
	.
	.}
==========================================================================================================================
على فرض انا وديت فنكشن ك بروبس لكمبوننت تاني اسم الفنكشن بريس زي المثال تحت 
<bottun OnClick={this.props.press}> Press Here </bottun>
في حال بدي احط بالفنكش قيمه بين اقواس ما رح يزبط اكتبه زي فوق ,لازم احطه جوا فنكشن تاني زي المثال تحت 
<bottun OnClick={()=>{this.props.press(anyvlue)}> Press Here </bottun>
او بعمل فنكشن تاني برا يكون جواته هاد الحكي وبستدعيه
deleteThing = ()=> {
	this.props.press(anyvlue)
}

<bottun OnClick={this.deleteThing}> Press Here </bottun>
===========================================================================================================================
how to delete : 

from server :
server.delete(/test,deleteSmthing);

function deleteSmthing(req, res) {
	//على الاغلب الريكويست رح يوصلني فيه اي دي الاشي الي بدي احذفه
	// delete takes query as get 
let {any} = req.query;
modelName.remove({},(err,req)=>{})
//or
modeName.deleteOne({},(err,req)=>{})  // need time u can use (async,await) or .then
//or
modeName.deleteMany({},(err,req)=>{})

}



















