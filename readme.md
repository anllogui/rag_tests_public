# Estrategias de RAG de menor a mayor dificultad

Instalar dependencias:

``` terminal
conda create -n rag_examples
pip install --upgrade langchain langchain-community langchainhub langchain_openai langchain_pinecone langchain langchain-community langchainhub git+https://github.com/pytube/pytube git+https://github.com/openai/whisper.git 
```

## 00_rag_openai_entire

Se carga entero el documento y se realizan preguntas sobre él.


### Links:

Video tutorial base: https://www.youtube.com/watch?v=BrsocJb-fAo
Código tutorial base: https://github.com/svpino/youtube-rag/blob/main/rag.ipynb

For fixing youtube problems change the following: 
https://github.com/pytube/pytube/issues/1707
https://github.com/pytube/pytube/issues/1894#issue-2180600881

**PROBLEMA** 
Los costes son muy grandes si cada vez hay que cargarlo todo.

**SOLUCION**
Pasamos al siguiente enfoque: enviar solo chunks.

## 01_rag_openai_pinecone

* Se trocea y se envía a pinecone.
* Se utiliza la estrategia de semantic chunk para mejorar 

### Links de text splitting:

https://community.fullstackretrieval.com/
https://github.com/FullStackRetrieval-com/RetrievalTutorials/blob/main/tutorials/LevelsOfTextSplitting/5_Levels_Of_Text_Splitting.ipynb


**PROBLEMA** 
Baja el accuracy al no tener todo el contexto.

**SOLUCION**
Pasamos al siguiente enfoque: Probar varias veces hasta que se consigue el resultado esperado.

## 01_self_rag

Se utiliza la estrategia de self rag con Langgraph.

### Links:
https://blog.langchain.dev/agentic-rag-with-langgraph/
https://github.com/langchain-ai/langchain/blob/master/cookbook/langgraph_self_rag.ipynb

# Siguientes Pasos:
[X] Cambiar el chunk para hacerlo más inteligente --> Añadido Semantic Chunk
[ ] Extraer de la mejor manera los datos de PDF
[ ] Add metadata and selfquery retriever: https://medium.com/@lorevanoudenhove/enhancing-rag-performance-with-metadata-the-power-of-self-query-retrievers-e29d4eecdb73

