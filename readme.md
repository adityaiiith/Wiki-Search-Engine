# Wikipedia Search Engine

### Prerequisites
1. Python3
2. nltk
3. SAX Parser
4. stop words list


  
### About Project
Built Search Engine Platform by creating Inverted Index on the Wikipedia Data Dump (2020) of size 72 GB.

Following Steps Follows to create Inverted Indexing
* Parsing using SAX : Need to parse each page , title tag, infobox, body , category etc..
* Tokenization  : Tokenize sentense to get each token using regular expression
* Case Folding : make it all to lowercase
* Stop Words Removal : remove stop word which are more frequently occured in a sentences
* Stemming : get root/base word and store it
* Inverted Index Creation : create word & its positing list consist of doc_id : TF-IDf score


Posting List for title/body/infobox/category file: 

```
word1=doc_id_1:b1#c2,doc_id_30:t1#i1#b5,doc_id_35:b10#c1#t1
word2=doc_id_2:t1#c2#b2,doc_id_19:t2#b4
```

### Features

* support field query like title:abc body:aaa infobox:zyx
* Returns top K relevent search results 
* Response time is < 5 seconds

### Challenges 

1. Difficult to process such huge Data dump of 72 GB
2. Can not store word & its posting list into a main memory, So Used External sorting
3. Can not Load full final index into main memory, So Bild Secondary Index on top of Primary Index (Posting List)
