(A)RAG - Multi-Query Query translation

Multi-Query translation will create similar queries from original question. Based those
queris, this algorithm will retieve the relevent information/document as part of the
prompt context before the final Q&A

step_to_step_query, at end, is based on the LangChain Rag youtube tutorial below, the code from the tutorial are 
listed in the first half of the python notebook. 


This function follows the same logic from the tutorial but without the abstract of Chain/Pipeline. This approach
it helps me to understand the llm processes and also can improve the prompt preparation.
Of course, the langsmith is a great tool as well. 


Input arguments to the step_to_step_fusion are
1. Document: the resume as the source of information
2. Quesition: question string

Please review the RAG tutorial from Langchain in details (part 5 - multi-query query translation)
https://www.youtube.com/watch?v=JChPi0CRnDY

(B)RAG - Fusion Query translation

RAG - Fusion Query translation

Fusion quest translation is similar to multi-query (creating similar query from question) 
but with ranking processes on retrieved documents before final answer.

step_to_step_fusion, at end, is based on the LangChain Rag youtube tutorial below, the code from the tutorial are 
listed in the first half of the python notebook. 

This function follows the same logic from the tutorial but without the abstract of Chain/Pipeline. This approach
it helps me to understand the llm processes and also can improve the prompt preparation.
Of course, the langsmith is a great tool as well. 

This function reads the PDF resumes from a directory, and each resume will be saved 
as a separated document in the vector database without duplication. 

Input arguments to the step_to_step_fusion are
1. Quesition: question string
2. Template:  the helping instructions you want the ChatPGT to return the Q&A 
with a better answer.

Please review the RAG tutorial from Langchain in details 
(part 6 - multi-fusion query translation)https://www.youtube.com/watch?v=77qELPbNgxA


