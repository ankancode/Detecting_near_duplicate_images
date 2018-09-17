# Detecting_near_duplicate_images
## Duplicate Defination :  
I have defined duplicates as near duplicates images based on following criteria- 
1) If images are exactly same.
2) If they are similar in the sense that they are same tops but they have some minor image or color differences in the top then it must be detected. 
3) If a same top is worn by a different model and also if the model is standing in a different pose in the same dress then it must be detected.  
4) If the same image is cropped at different portion or if the resolution of the images are different or if it has some noise in the image then also it must be detected.

I have commented the code, so that it is easily understandable. I have saved all my images with the productID, for Example : <productId.jpg>. 

## Files Description:
1. Data_Preprocessing.ipynb ( It does all the Data processing that is needed to done for my further tasks)
2. download_images.ipynb ( Downloading all the tops images using multiprocessing ) 
3. dhash.ipynb ( dhashing all our tops inventory and saving it )
4. Near_Dup_Img.ipynb ( Calculating the similarity score of our input images with our inventory of tops images and Dumping the json output file ) you may use Near_Dup_Img.py if you want it to run from the terminal.
Command : python Near_Dup_Img.py <image_1> <image_2> ...<image_3>
5. Output is saved in this file "near_duplicate_image.json" .


## Other experimental techniques that I have tried are as follows-

1. Histogram based strategy using Hellinger Distance, the technique gave the duplicate outputs but false positives count was quite high. ( I have added the code for this method in the file "compare_helinger.ipynb", but I have not used it in my final solution )

2. I also tried p-hash to find the duplicates and the results were quite good for exact duplicates,but not for near duplicate images.

3. One more experiment that I could have tried, but I didn't because of less RAM on my machine, that is getting the image embedding from a pre-trained network (e.g Resent50) trained over imagenet dataset. And then finding the cosine similarity over inventory embeddings to find the near duplicate images.
