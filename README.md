# BPE_Tokenizer
A tokenizer that processes a text file and shows tokens with their token IDs using tiktoken BPE.

The main idea in tokenizer which uses BPE algorithm is to convert text tokens into an integer representation.

['I','love','NLP'] --> [21,67,55]

The goal of the BPE tokenization algorithm is to build a vocabulary of commonly occurring subwords.

for ex:  
# high higher highest  

['h', 'i', 'g', 'h']   
['h', 'i', 'g', 'h', 'e', 'r']  
['h', 'i', 'g', 'h', 'e', 's', 't']  

('h', 'i') → 3  
('i', 'g') → 3  
('g', 'h') → 3  
('h', 'e') → 2  
('e', 'r') → 1  
('e', 's') → 1  
('s', 't') → 1  


BPE assigns token ID 256 → 'gh' - as gh has highest frequency in occurence and it comes first as per alphabetical order as compare other highest frequncies, and in next iteration we id next most common elements and so on.  
We tokenize other common combinations as well like ('i','gh') -> 3 , ('h', 'igh') → 3  etc.   

Every token (character, subword, or word) must be mapped to a **unique integer ID** that can later be embedded and processed by the model.




