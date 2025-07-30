# BPE_Tokenizer

The main idea of a tokenizer using the BPE algorithm is to segment text into subword units based on frequently occurring character pairs, and then convert those subwords into a unique integer representation.

['I','love','NLP'] --> [21,67,55]

How BPE training data is different from LLM?

BPE training data consists of small text corpora used to learn frequent character pairs and build a subword vocabulary, enabling efficient and consistent   tokenization. In contrast, LLM training data comprises massive, tokenized datasets (often in terabytes) drawn from diverse sources like books, websites, and code,   used to teach the model to predict the next token in a sequence. BPE runs before LLM training and defines how raw text is broken into tokens, which the LLM then   learns to model statistically.  

# BPE originally stands for Byte Pair Encoding because it operates at the byte level, not at the character or word level.

Since a byte consists of 8 bits, there are 2^8 = 256 possible values that a single byte can represent, ranging from 0 to 255  
0–255	--> All possible byte values (base vocabulary)  
256+ -->	Merged subwords built by BPE  

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

Every token (character, subword, or word) must be mapped to a **unique integer ID** that can later be embedded and processed by the LLM model.




