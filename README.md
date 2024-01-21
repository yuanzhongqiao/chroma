<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><p align="center" dir="auto">
  <a href="https://trychroma.com" rel="nofollow"><img src="https://user-images.githubusercontent.com/891664/227103090-6624bf7d-9524-4e05-9d2c-c28d5d451481.png" alt="色度标志" style="max-width: 100%;"></a>
</p>
<p align="center" dir="auto">
    <b><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Chroma - 开源嵌入数据库</font></font></b><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font><br><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
    使用内存构建 Python 或 JavaScript LLM 应用程序的最快方法！
</font></font></p>
<p align="center" dir="auto">
  <a href="https://discord.gg/MMeYNTmh3x" rel="nofollow">
      <img src="https://camo.githubusercontent.com/e2fcd196c4b9382b49d4baa08865a6858e5f760b1fd0d4583ec6a1445ffdd212/68747470733a2f2f696d672e736869656c64732e696f2f646973636f72642f31303733323933363435333033373935373432" alt="不和谐" data-canonical-src="https://img.shields.io/discord/1073293645303795742" style="max-width: 100%;">
  </a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">|
  </font><font style="vertical-align: inherit;">|
  </font><a href="https://docs.trychroma.com/" rel="nofollow"><font style="vertical-align: inherit;">
      文档
  </font></a><font style="vertical-align: inherit;">|
  </font><a href="https://www.trychroma.com/" rel="nofollow"><font style="vertical-align: inherit;">
      主页
  </font></a></font><a href="https://github.com/chroma-core/chroma/blob/master/LICENSE">
      <img src="https://camo.githubusercontent.com/7509eb9ecbcff610a1adfd2e6de2816caa1a1dad25ab6df90017683378fe9150/68747470733a2f2f696d672e736869656c64732e696f2f7374617469632f76313f6c6162656c3d6c6963656e7365266d6573736167653d41706163686520322e3026636f6c6f723d7768697465" alt="执照" data-canonical-src="https://img.shields.io/static/v1?label=license&amp;message=Apache 2.0&amp;color=white" style="max-width: 100%;">
  </a><font style="vertical-align: inherit;"></font><a href="https://docs.trychroma.com/" rel="nofollow"><font style="vertical-align: inherit;"></font></a><font style="vertical-align: inherit;"></font><a href="https://www.trychroma.com/" rel="nofollow"><font style="vertical-align: inherit;"></font></a>
</p>
<p align="center" dir="auto">
  <a href="https://github.com/chroma-core/chroma/actions/workflows/chroma-integration-test.yml">
    <img src="https://github.com/chroma-core/chroma/actions/workflows/chroma-integration-test.yml/badge.svg?branch=main" alt="集成测试" style="max-width: 100%;">
  </a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">|
  </font></font><a href="https://github.com/chroma-core/chroma/actions/workflows/chroma-test.yml">
    <img src="https://github.com/chroma-core/chroma/actions/workflows/chroma-test.yml/badge.svg?branch=main" alt="测试" style="max-width: 100%;">
  </a>
</p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>pip install chromadb <span class="pl-c"><span class="pl-c">#</span> python client</span>
<span class="pl-c"><span class="pl-c">#</span> for javascript, npm install chromadb!</span>
<span class="pl-c"><span class="pl-c">#</span> for client-server mode, chroma run --path /chroma_db_path</span></pre><div class="zeroclipboard-container">
    
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">核心 API 只有 4 个函数（运行我们的</font></font><a href="https://colab.research.google.com/drive/1QEzFyqnoFxq7LUGyP1vzR4iLt9PpCDXv?usp=sharing" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">💡 Google Colab</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><a href="https://replit.com/@swyx/BasicChromaStarter?v=1" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Replit 模板</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）：</font></font></p>
<div class="highlight highlight-source-python notranslate position-relative overflow-auto" dir="auto"><pre><span class="pl-k">import</span> <span class="pl-s1">chromadb</span>
<span class="pl-c"># setup Chroma in-memory, for easy prototyping. Can add persistence easily!</span>
<span class="pl-s1">client</span> <span class="pl-c1">=</span> <span class="pl-s1">chromadb</span>.<span class="pl-v">Client</span>()

<span class="pl-c"># Create collection. get_collection, get_or_create_collection, delete_collection also available!</span>
<span class="pl-s1">collection</span> <span class="pl-c1">=</span> <span class="pl-s1">client</span>.<span class="pl-en">create_collection</span>(<span class="pl-s">"all-my-documents"</span>)

<span class="pl-c"># Add docs to the collection. Can also update and delete. Row-based API coming soon!</span>
<span class="pl-s1">collection</span>.<span class="pl-en">add</span>(
    <span class="pl-s1">documents</span><span class="pl-c1">=</span>[<span class="pl-s">"This is document1"</span>, <span class="pl-s">"This is document2"</span>], <span class="pl-c"># we handle tokenization, embedding, and indexing automatically. You can skip that and add your own embeddings as well</span>
    <span class="pl-s1">metadatas</span><span class="pl-c1">=</span>[{<span class="pl-s">"source"</span>: <span class="pl-s">"notion"</span>}, {<span class="pl-s">"source"</span>: <span class="pl-s">"google-docs"</span>}], <span class="pl-c"># filter on these!</span>
    <span class="pl-s1">ids</span><span class="pl-c1">=</span>[<span class="pl-s">"doc1"</span>, <span class="pl-s">"doc2"</span>], <span class="pl-c"># unique for each doc</span>
)

<span class="pl-c"># Query/search 2 most similar results. You can also .get by id</span>
<span class="pl-s1">results</span> <span class="pl-c1">=</span> <span class="pl-s1">collection</span>.<span class="pl-en">query</span>(
    <span class="pl-s1">query_texts</span><span class="pl-c1">=</span>[<span class="pl-s">"This is a query document"</span>],
    <span class="pl-s1">n_results</span><span class="pl-c1">=</span><span class="pl-c1">2</span>,
    <span class="pl-c"># where={"metadata_field": "is_equal_to_this"}, # optional filter</span>
    <span class="pl-c"># where_document={"$contains":"search_string"}  # optional filter</span>
)</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="import chromadb
# setup Chroma in-memory, for easy prototyping. Can add persistence easily!
client = chromadb.Client()

# Create collection. get_collection, get_or_create_collection, delete_collection also available!
collection = client.create_collection(&quot;all-my-documents&quot;)

# Add docs to the collection. Can also update and delete. Row-based API coming soon!
collection.add(
    documents=[&quot;This is document1&quot;, &quot;This is document2&quot;], # we handle tokenization, embedding, and indexing automatically. You can skip that and add your own embeddings as well
    metadatas=[{&quot;source&quot;: &quot;notion&quot;}, {&quot;source&quot;: &quot;google-docs&quot;}], # filter on these!
    ids=[&quot;doc1&quot;, &quot;doc2&quot;], # unique for each doc
)

# Query/search 2 most similar results. You can also .get by id
results = collection.query(
    query_texts=[&quot;This is a query document&quot;],
    n_results=2,
    # where={&quot;metadata_field&quot;: &quot;is_equal_to_this&quot;}, # optional filter
    # where_document={&quot;$contains&quot;:&quot;search_string&quot;}  # optional filter
)" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<h2 tabindex="-1" dir="auto"><a id="user-content-features" class="anchor" aria-hidden="true" tabindex="-1" href="#features"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">特征</font></font></h2>
<ul dir="auto">
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">简单</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：完全类型、完全测试、完全记录==幸福</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">集成</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：</font></font><a href="https://blog.langchain.dev/langchain-chroma/" rel="nofollow"><code>🦜️🔗 LangChain</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（python 和 js），</font></font><a href="https://twitter.com/atroyn/status/1628557389762007040" rel="nofollow"><code>🦙 LlamaIndex</code></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以及更多内容</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">开发、测试、生产</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：在 Python Notebook 中运行的相同 API，可扩展到您的集群</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">功能丰富</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：查询、过滤、密度估计等</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">免费和开源</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：Apache 2.0 许可</font></font></li>
</ul>
<h2 tabindex="-1" dir="auto"><a id="user-content-use-case-chatgpt-for-______" class="anchor" aria-hidden="true" tabindex="-1" href="#use-case-chatgpt-for-______"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用例：ChatGPT 用于 ______</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">例如，</font></font><code>"Chat your data"</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用例：</font></font></p>
<ol dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将文档添加到您的数据库。</font><font style="vertical-align: inherit;">您可以传入您自己的嵌入、嵌入函数，或者让 Chroma 为您嵌入它们。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用自然语言查询相关文档。</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将文档撰写到法学硕士的上下文窗口中，例如</font></font><code>GPT3</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">进行额外的总结或分析。</font></font></li>
</ol>
<h2 tabindex="-1" dir="auto"><a id="user-content-embeddings" class="anchor" aria-hidden="true" tabindex="-1" href="#embeddings"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">嵌入？</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">什么是嵌入？</font></font></p>
<ul dir="auto">
<li><a href="https://platform.openai.com/docs/guides/embeddings/what-are-embeddings" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">阅读 OpenAI 的指南</font></font></a></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文字</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：嵌入某些内容会将其从图像/文本/音频转换为数字列表。</font><font style="vertical-align: inherit;">🖼️ 或 📄 =&gt; </font></font><code>[1.2, 2.1, ....]</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font><font style="vertical-align: inherit;">此过程使机器学习模型“可以理解”文档。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以此类推</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：嵌入代表了文档的本质。</font><font style="vertical-align: inherit;">这使得具有相同本质的文档和查询彼此“接近”，因此易于查找。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">技术</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：嵌入是文档在深度神经网络层的潜在空间位置。</font><font style="vertical-align: inherit;">对于专门训练来嵌入数据的模型，这是最后一层。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">一个小例子</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：如果您在照片中搜索“旧金山著名的桥梁”。</font><font style="vertical-align: inherit;">通过嵌入此查询并将其与照片及其元数据的嵌入进行比较 - 它应该返回金门大桥的照片。</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">嵌入数据库（也称为</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">向量数据库</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）存储嵌入，并允许您按最近邻居进行搜索，而不是像传统数据库那样按子字符串进行搜索。</font><font style="vertical-align: inherit;">默认情况下，Chroma 使用</font></font><a href="https://docs.trychroma.com/embeddings#sentence-transformers" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Sentence Transformers</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为您嵌入，但您也可以使用 OpenAI 嵌入、Cohere（多语言）嵌入或您自己的嵌入。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-get-involved" class="anchor" aria-hidden="true" tabindex="-1" href="#get-involved"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">参与其中</font></font></h2>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Chroma 是一个快速发展的项目。</font><font style="vertical-align: inherit;">我们欢迎公关贡献者和关于如何改进该项目的想法。</font></font></p>
<ul dir="auto">
<li><a href="https://discord.gg/MMeYNTmh3x" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">加入 Discord 上的对话</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">-</font></font><code>#contributing</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">频道</font></font></li>
<li><a href="https://docs.trychroma.com/roadmap" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">查看 🛣️ 路线图并贡献您的想法</font></font></a></li>
<li><a href="https://github.com/chroma-core/chroma/issues"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">抓住一个问题并打开 PR</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> -</font></font><a href="https://github.com/chroma-core/chroma/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22"><code>Good first issue tag</code></a></li>
<li><a href="https://docs.trychroma.com/contributing" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">阅读我们的贡献指南</font></font></a></li>
</ul>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">发布 Cadence</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">
我们目前在周一发布</font></font><code>pypi</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和</font></font><code>npm</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">软件包的新标记版本。</font><font style="vertical-align: inherit;">修补程序在一周中的任何时间都会发布。</font></font></p>
<h2 tabindex="-1" dir="auto"><a id="user-content-license" class="anchor" aria-hidden="true" tabindex="-1" href="#license"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">执照</font></font></h2>
<p dir="auto"><a href="/chroma-core/chroma/blob/main/LICENSE"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">阿帕奇2.0</font></font></a></p>
</article></div>
