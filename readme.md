This is a small REST API built using nodejs and express. It takes a post request with an audiofile which will then convert the received file to 128kbps and upload it to AWS S3. After this it will return an object containing the URL to the converted file on S3. Meant for deployment on a Raspberry Pi 3 (requires manual install of FFMPEG on the Pi).

The following enviroment variables should be set:

- NODE_ENV=  #Should be set to production on production, can be left empty otherwise
- AWS_S3_BUCKET_NAME=  #Name of S3 bucket
- AWS_S3_USER_KEY=  #AWS User key with the proper permissions
- AWS_S3_USER_SECRET=  #AWS User secret with the proper permissions

Request should be posted to /convert. It needs the following properties in the body:
```javascript
{
    audio: [AUDIO FILE | .mp3 or .m4a]
    category: [PODCAST CATEGORY | string]
    name: [NAME OF EPISODE | string]
}
```
