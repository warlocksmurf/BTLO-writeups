# Step 1
We were given a zip file called ``Secret.zip``. So I used binwalk to analyze any hidden files within and and managed to extract a jpg image in it called ``SBT.jpg``. Again, I used binwalk to analyze the jpg image and managed to extract a png image called ``message.png``. However, this png image was obviously modified since there were no images. So I used strings/cat to find any hidden text in it and found our first ciphertext.

<p align='center'>
  <img src='/images/dcrypt1.png' alt="dcrypt1">
</p>

```
h5BA68F35I_%3E%3B%3BG3gdc%3E%3EFF9g5deA82hhh%3F%3Ea%3B22gdh%3Ee%3B%3B%6025%60A682bhddeA82h4IBA68F2gd%60%3E%3B%3B%3B%60g5c%3E%3EFF%60hd%3C%3Ea%3EFbhh_%3Fe8F255g%3EeEG32d%60%3EA83hg5%3C%3EaF2bhhB%3Fa8Gf55g%3Ee%3B%3C32d%60A6FF9g5%3CAA82hhh%3F%3Ea%3B22gd%60%3E%3BEG32d%60A6FGfg5%3CAJ82hh5%3F%3Ea%3B3f55_%3E%3BEG32d%60A682bhddeA82hhh%3F%3Fa8F2gdh%3Ee%3B%3B%60g5c%3EAGF9g5dca8Fhhh_%3Fe8Gfgd%60%3E%3B%3BF%6025%60A682bhd%3CAA82h4I_A%3B8Gfgdh%3EeEG3gdc%3E%3E82bhd%3CAJ%3E2bhh_%3Fe8F255g%3EeEF%60g5c%3EAFF%60hd%3CAA%3E2b4I%3F%3Ea%3B3fgd%3E%3EeEF%60g5cA6FF9g5%3C%3Ea8Fhh5%3F%3Ea%3B22gdh%3EeEG3gdcA683hg5deA%3E2bhh%3F%3Ea%3B22gd%60%3E%3BEG72d%60A682bhd%3C%3Ea%3EFb4I_%3Ee%3B23gdh%3EeEF%6025%60A6FF%60hd%3C%3EaF2bhh%3F%3Ea%3B3f55g%3EeEF%60g5c%3EAFF9g5deA%3E2b4I%3F%3Ea%3B3fgd%3E%3EeEF%6025%60A6FF9g5%3C%3Ea8Fhh5%3F%3Fa8F255g%3EeEG3gdcA683hg5%3CAA%3E2bhh_%3Ee%3B22gd%60%3E%3BEG72d%60%3E%3E82bhddeA82h4I_A%3B8Gf55_%3E%3BEG32d%60%3E%3E82bhd%3CAJ82h4I%3F%3Ea%3B3f55g%3EeEF%60g5c%3EAFF%60hd%3C%3Ea8Fhhh_%3Ee%3B3f5Ig%3EeEG32d%60%3E%3EFF9g5%3C%3Ea8Fhh5_%3Fe8Gf55_%3E%3BEF%605d%60A682bhc
```

# Step 2
Looking at the ciphertext, it was obviously URL encoded so we will decode that.

```
h5BA68F35I_>;;G3gdc>>FF9g5deA82hhh?>a;22gdh>e;;`25`A682bhddeA82h4IBA68F2gd`>;;;`g5c>>FF`hd<>a>Fbhh_?e8F255g>eEG32d`>A83hg5<>aF2bhhB?a8Gf55g>e;<32d`A6FF9g5<AA82hhh?>a;22gd`>;EG32d`A6FGfg5<AJ82hh5?>a;3f55_>;EG32d`A682bhddeA82hhh??a8F2gdh>e;;`g5c>AGF9g5dca8Fhhh_?e8Gfgd`>;;F`25`A682bhd<AA82h4I_A;8Gfgdh>eEG3gdc>>82bhd<AJ>2bhh_?e8F255g>eEF`g5c>AFF`hd<AA>2b4I?>a;3fgd>>eEF`g5cA6FF9g5<>a8Fhh5?>a;22gdh>eEG3gdcA683hg5deA>2bhh?>a;22gd`>;EG72d`A682bhd<>a>Fb4I_>e;23gdh>eEF`25`A6FF`hd<>aF2bhh?>a;3f55g>eEF`g5c>AFF9g5deA>2b4I?>a;3fgd>>eEF`25`A6FF9g5<>a8Fhh5??a8F255g>eEG3gdcA683hg5<AA>2bhh_>e;22gd`>;EG72d`>>82bhddeA82h4I_A;8Gf55_>;EG32d`>>82bhd<AJ82h4I?>a;3f55g>eEF`g5c>AFF`hd<>a8Fhhh_>e;3f5Ig>eEG32d`>>FF9g5<>a8Fhh5_?e8Gf55_>;EF`5d`A682bhc
```

Next, the output seems vague so I attempted the common encoding techniques such as Base64 and ROT13/ROT47. ROT47 seems to output the most logical text.

```
9dqpegubdx0mjjvb854mmuuh8d56pga999nm2jaa859m6jj1ad1pega39556pga9cxqpegua851mjjj18d4mmuu195km2mu3990n6guadd8m6tvba51mpgb98dkm2ua399qn2gv7dd8m6jkba51peuuh8dkppga999nm2jaa851mjtvba51peuv78dkpyga99dnm2jb7dd0mjtvba51pega39556pga999nn2gua859m6jj18d4mpvuh8d542gu9990n6gv7851mjju1ad1pega395kppga9cx0pjgv7859m6tvb854mmga395kpyma3990n6guadd8m6tu18d4mpuu195kppma3cxnm2jb785mm6tu18d4peuuh8dkm2gu99dnm2jaa859m6tvb854pegb98d56pma399nm2jaa851mjtvfa51pega395km2mu3cx0m6jab859m6tu1ad1peuu195km2ua399nm2jb7dd8m6tu18d4mpuuh8d56pma3cxnm2jb785mm6tu1ad1peuuh8dkm2gu99dnn2guadd8m6tvb854pegb98dkppma3990m6jaa851mjtvfa51mmga39556pga9cx0pjgv7dd0mjtvba51mmga395kpyga9cxnm2jb7dd8m6tu18d4mpuu195km2gu9990m6jb7dx8m6tvba51mmuuh8dkm2gu99d0n6gv7dd0mjtu1d51pega394
```

Similarly, I attempted the common encoding techniques again and the output with Base32 seems to work. However, Cyberchef could not decode it for some reason so I had to use browserlingtools as suggested by the challenge author.

```
KogCKoAIKkAIJkQCJkAIJkAIJASCJASCgACIJkAIgogCJACIJACIJkAIgASCJASCJkQCgkQCKAiCgAiCJoQCgkQCJkQCgkQCgkAIJkAIJACIgkQCgkgCgoAIKkAIgkAIgkQCgACIJkAIJkQCJASCJACIKoQCJACIJASCgACIKASCgACIgkAIgAiCgASCgkAIJACIgoQCJASCJkQCgACIKkAIgkQCgkAIgAiCgACIgkQCgACIKkAIJASCgkAIgAiCJkQCJkAIJACIgoQCgACIgASCgACIKASCgASCgkAIgAiCJkAIgkQCgACIKkQCJkQCgkAIgAiCgASCgkQCgACIKkQCJkQCgkAIgAiCgkQCJACIJACIgoQCJACIJkAIgAiCgkAIgkQCJACIgoAIgkAIgkQCgACIKkAIgACIJACIgoQCgkQCJkQCgACIKASCgkAIgAiCgACI
```

At this point, I had to ask a fellow BTLO member on Discord for a sanity check and they said I was going on the right track. So, I read the scenario again and notice the hint given by the author. The hint mentioned "reverse" and "base". So I tried using the reverse text decoder in browserlingtools.

```
ICAgCiAgIAkgCSAKICAgCQkJCQkgCQogICAJICAgIAkKICAgCQkgIAkgIAogICAJCQkgIAkgCiAgIAkJICAJCQogICAJICAJCQkgCiAgIAkgCQkJCQkKICAgCQkgCSAgCiAgIAkgCQkJCQkKICAgCQkgIAkJCiAgIAkgCSAgCSAKICAgCSAgICAgCQogICAJIAkJCQkJCiAgIAkgCSAJIAkKICAgCQkgICAgCiAgIAkgCQkgIAkKICAgCQkJCSAJCQogICAJIAkgCSAgCiAgIAkgICAgCSAKICAgCSAJICAJCQoKICAJCSAJCQkJIAkJICAgCQkgIAkgIAkKIAogCgkgCQkgICAJIAkJIAkgCQkgCQkJCQkgCQoJCiAgCiAKCQkgCQkJCSAJCSAgIAkJICAJICAJCgogIAkJICAgCSAJCSAJIAkJIAkJCQkJIAkKIAoKCgoK
```

Reverse done, next is to attempt a Base64 decode as mentioned in the hint.

```
   
   	 	 
   					 	
   	    	
   		  	  
   			  	 
   		  		
   	  			 
   	 					
   		 	  
   	 					
   		  		
   	 	  	 
   	     	
   	 					
   	 	 	 	
   		    
   	 		  	
   				 		
   	 	 	  
   	    	 
   	 	  		

  		 				 		   		  	  	
 
 
	 		   	 		 	 		 					 	
	
  
 
		 				 		   		  	  	

  		   	 		 	 		 					 	
 





```

Mind the language but wtf is this? I thought I did something wrong but after asking the discord member about it, they told me to research on "whitespaces" and hence I googled search whitespace decode and the results gave a whitespace language decoder in dcode (I had no idea about this encoding technique LMAO). Using the blank spaces given after Base64, we get the flag!

<p align='center'>
  <img src='/images/dcrypt2.png' alt="dcrypt2">
</p>

```
SBT{Y0U_AR3_4_N3rd!} 
```
