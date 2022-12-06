# How-to-connect-supabase-storage-appsmith

Document explaining in detail how to make a connection and upload files to supabase storage

1. First we will create a new ahutentication API data source.
   ![image](https://user-images.githubusercontent.com/114161539/205972223-de1c8118-74cf-4590-aec7-d3e9aeda0bf7.png)
2. Let's navigate to the supabase dashboard to get our credentials.

![image](https://user-images.githubusercontent.com/114161539/205975220-d66c0e8e-3281-48d9-80d0-d9b62cd64ddb.png)

3. Next in our url we will write it in this way

`https://mritzxpfuqsbselcjefc.supabase.co/storage/v1/object/`

![image](https://user-images.githubusercontent.com/114161539/205974488-868a80c4-4814-4f50-8e1b-3fca41de51b6.png)

4. Now we will add our `apikey`

![image](https://user-images.githubusercontent.com/114161539/205975465-d749181d-442f-457d-9522-28abbb722541.png)

5. Let's add bearer token authentication.

![image](https://user-images.githubusercontent.com/114161539/205975770-a98d2f7d-f113-475a-a74d-3ae799f4d021.png)

6. Now we add the bearer token `It is the same token as the apikey`

![image](https://user-images.githubusercontent.com/114161539/205976359-1666ff58-b3a2-4ba4-9743-97dd53a5d6ef.png)

Perfect with this we should already have our connection made successfully.

### How to upload files to supabase

1. We create a new bucket in supabase.

![image](https://user-images.githubusercontent.com/114161539/205976813-acd2c93e-a04f-4383-9b6e-8bc6c22a1628.png)

2. We create a new query in our appsmith application.

![image](https://user-images.githubusercontent.com/114161539/205977234-41fcd38a-b8c5-4d96-b1e0-b41bf38b0bbc.png)

3. We will add a new Filepicker widget.

   ![image](https://user-images.githubusercontent.com/114161539/205977697-e76b70bb-5abb-416e-be1f-14885837569b.png)

4. In the query created, we will add the name of our bucket and the file name to be created `we will extract it from the filepicker.`

   `appsmith/{{FilePicker1.files[0].name}}`

![image](https://user-images.githubusercontent.com/114161539/205978391-a4ffd67c-23b5-41f5-912a-d3f9dde20bba.png)

5. Then we will add this header.

   - key `content-type` value `application/json`
   
     ![image](https://user-images.githubusercontent.com/114161539/205978982-41889919-42d6-4dde-9102-f2dce474e109.png)

6. We will put the API method as post.

![image](https://user-images.githubusercontent.com/114161539/205983017-11b42330-e153-4ea7-b428-0046af71380b.png)

7. And finally we will add the information that we are going to load in the body in this way.

![image](https://user-images.githubusercontent.com/114161539/205979151-3e280bff-393a-47b4-8700-4c2f035b885c.png)

8. And ready now to test if it works, let's select a file with the file picker and execute the query.

![image](https://user-images.githubusercontent.com/114161539/205983689-3abf5310-2eff-474d-b00a-709fe7e7fd2f.png)
