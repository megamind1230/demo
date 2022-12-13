- head
	- بيعرض اول 10 سطور في الفايل
	- head -16 fileName 
		- كده يعرض اول16
	- head -c4 fileName
		- اعرض اول 4 حروف / بايتس
- tail عكسها
- cat
	- يعرض الفايل كامل بالترتيب
	- `cat file1 file2 > somefile`
		- هيحقن المحتويين في فايل واحد من غير ما يعرض 
	- `cat > somefile`
		- هيعمل لك فايل ويخيلك تكتب فيه.. ولما تخلص اعمل ctrl d
	- `cat > somefile<<hellNah`
		- هيفضل يستقبل لحد ما يقابل hellNah
- tac يعرض أسطر الفايل بالعكس
- more
	- بيعرض المحتوي مجزأ .. دوس انتر لعرض جزئية بسيطة أخرى.. دوس مسافة هيعرض جزئية اكبر
- less
	- زي اللي فوقها بس.. لما توصل للنهاية اعمل ctrl z
- strings
	- cat بتعرض أي حاجة سواء كانت مقروءة او غير
	- strings بتعرض المقروء وفقط
		- ![[Pasted image 20221213121441.png]]
- sort
	- ترتيب تصاعدي
	- sort -r ترتيب تنازلي
- wc
	- بتعمل تقرير برقم الأسطر والكلمات والحروف
	- 
- stat
	- معلومات عن الفايل
- grep
	- grep somestr fileName
- nano
```text
ctrl k > cut

ctrl u > paste

ctrl o > save

ctrl x > exit

ctrl / or ctrl w ctrl t> go to line

nano -v somefile > view only mode

`nano +numb somefile` go to the specific line in file

alt u / alt e > undo / redo

ctrl t ctrl s > check spelling

ctrl a / e > home of line / end

alt a then move > like mouse selection

ctrl j > show wrapped line
```



#vim #nano