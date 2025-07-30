# BPE_Tokenizer
A tokenizer that processes a text file and shows tokens with their token IDs using tiktoken BPE.

The main idea in tokenizer which uses BPE algorithm is to convert text tokens into an integer representation.

['I','love','NLP'] --> [21,67,55]

The goal of the BPE tokenization algorithm is to build a vocabulary of commonly occurring subwords.

['h', 'i', 'g', 'h', '</w>']  
['h', 'i', 'g', 'h', 'e', 'r', '</w>']  
['h', 'i', 'g', 'h', 'e', 's', 't', '</w>']  

('h', 'i') → 3  
('i', 'g') → 3  
('g', 'h') → 3  
('h', '</w>') → 1  
('h', 'e') → 2  
('e', 'r') → 1  
('r', '</w>') → 1  
('e', 's') → 1  
('s', 't') → 1  
('t', '</w>') → 1

Assign token ID 256 → 'gh' - gh comes first as per alphabetical order, and in next iteration we id next most common element and so on. We try other common combinations as well like ('i','gh') -> 3 , ('h', 'igh') → 3  etc.


