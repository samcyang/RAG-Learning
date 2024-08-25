(A)RAG-Multi-Query-Translation-LangChina.ipybn
RAG - Multi-Query Query translation

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

(B)RAG-Requirements-Multi-Query-Translation.ipybn

Instead of a signle question, this sample program validates if the resume of a candidate 
can satisfy the necessary job requirements.

1. The logic starts with Multi-Query translation of each Job Requirement to multiple sub-questions.
2. The logic queries each sub-question against the resume and aggregates 
all the answers from sub-questions as the aggregated context. (similar to RAG Decomposition) 
3. The final logic queries the aggregated context with the requirement and provides a summary to 
identify if this candidate meets this job requirements. 


Input arguments to the step_to_step_fusion are
1. Template: how to generate the sub-questions from a requirement
2. Template2: How to generate the summary of each requirement
3. Requirements: The requirement list
4. Resume: The resume of a candidate.

(C)RAG-Fusion-LangChain.ipynb
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

(D)RAG-Decomposition-LangChina.ipybn
RAG - Decomposition question to sub-questions and aggregating each sub-question/answar pair
as part of prompt context in the next sub-question prompt till final.

RAG - Decomposition question to sub-questions, and provide the final answer from the 
retrieved documents of each sub-question.

Decomposition translation is different from multi-query or fusion, instead of 
creating similar questions, it creates sub-questions from the original question. 

step_to_step_decomposition, at end, is based on the LangChain Rag youtube tutorial below, 
the code from the tutorial is listed in the first half of the ipython notebook. 

This function follows the same logic from the tutorial but without the abstract of 
Chain/Pipeline. This approach helps me to understand the sub-questions creation, 
llm processes and also can improve the final prompt preparation. 
Of course, the langsmith is a great tool as well. 

I may be wrong, but it seems to me the separate the sub-questions as individual questions
can return more accurate results than the aggregation approach. 
However, the aggregation decomposition approach provide more details in answer.


Input arguments to the step_to_step_fusion are
1. Quesition: question string
2. Additional_background:  the helping instructions you want the ChatPGT to return the Q&A 
with a better answer.
3. Aggregation: 1 means aggregating sub-questions as prompt for the next sub-question Q&A


Please review the RAG tutorial from Langchain in details (part 7 
- decompistion query translation)
https://www.youtube.com/watch?v=h0OPWlEOank

(E)RAG-RAPTOR.ipynb

RAG - RAPTOR

Based on the question, the RAPTOR process recursively builds a "tree"  from raw 
docs(leafs) to more abstract summaries.

It is very important to create the right prompt with enough information 
(or requirements).  Otherwise, the summaries may be misleading or is not sufficient 
to answer the question correclty.

I am still using the same PDF resumes in other RAP notebooks, as the raw docs (leafs)
instead of retrieving them from the Web.

I also tried two models: gpt-4-turbo and claude-3-5-sonnet-20240620.  gpt-4-turbo
runs a bit longer than claude-3-5-sonnet-20240620.

Both can answer the question correctly but it seems to me Claude-3-5 provides m
ore insight. 


Please review the RAG tutorial from Langchain in details 
https://github.com/langchain-ai/langchain/blob/master/cookbook/RAPTOR.ipynb
