# DoxAI-API-Call

https://api.doxai.co/info/#api-documentation

# Example Usage
Face Match

```
const inputBody = '{
  "id": "",
  "images": ""
}';
const headers = {
  'Content-Type':'multipart/form-data',
  'Accept':'application/json',
  'x-access-key': 'YOUR ACCESS KEY',
  'x-secret-key':'YOUR SECRET KEY'
};

fetch('https://api.doxai.co/v1/face-match',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});
```

# Parameters
```
Name	In	Type	Required	Description
x-access-key	header	string	true	none
x-secret-key	header	string	true	none
body	body	object	true	none
» id	body	string(binary)	true	Take snapshot
» images	body	string(binary)	true	Upload image to compare
```

# Response
```
{
  "msg": "Request Success",
  "data": {
    "faceMatched": "true",
    "similarity": 99.01,
    "image1": {
      "result": "The face doesn't match",
      "details": {
        "isFaceCenter": true,
        "isFaceLeft": true,
        "isFaceRight": true,
        "isEyesOpen": false,
        "isWearingEyeGlasses": false,
        "isWearingSunglasses": false,
        "eyesConfidence": 95.71,
        "similarity": 95.71,
        "faceMatched": false
      }
    },
    "id": {
      "type": "Driving License",
      "confidence": 86.68
    }
  }
}
```
