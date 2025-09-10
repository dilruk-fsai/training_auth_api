const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

app.post('/api/check-auth', (req, res) => {
	const{email} = req.body;
	if(!email) return res.status(400).json({error:"Email required"});
	return res.json({eligible:true, reason: "Dummy response for " + email});
});

app.listen(PORT, ()=> {
	console.log('server running on port ${PORT}');
});