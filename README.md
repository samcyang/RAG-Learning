(A)RAG - Multi-Query Query translation

Besides using the LangChain Chain/Pipeline as illustrated in the LangChain Rag tutorial below, 
this program also creates a step_to_step_query (question) function that executes within the same logic 
but without the abstract of Chain/Pipeline. it helps me to understand the processes 
and also be able to improve the prompt or question preparation better. 
Of course, langSmith is a great tool as well

Please review the RAG tutorial from Langchain in details (part 5 - multi-query query translation)
https://www.youtube.com/watch?v=JChPi0CRnDY

(B)RAG - Fusion Query translation

Besides using the LangChain Chain/Pipeline as illustrated in the LangChain Rag tutorial 
below, this program reads the PDF resumes from a directory, each resume will be saved 
as a document without duplication.  

We also create a single step_by_step_fusion (question, template) program 
that executes the same logic but without the abstract of Chain/Pipeline. 
It helps me to understand the processes and also be able to improve the template 
(prompt or question) preparation better. Of course, langSmith is a great tool as well.

The template input that passes to step_by_step_fusion is the format you 
want the ChatPGT to return such that the final process of Q&A should have a better answer.

Please review the RAG tutorial from Langchain in details 
(part 6 - multi-fusion query translation)https://www.youtube.com/watch?v=77qELPbNgxA


