# Offline Tools

## Insert doc

Your can use `insert.py` to load data from local project folder. The project information can be your own private repo, or it can be crawled by yourself using a crawler.
For example, if you want to load your local project named langchain, you can use this script:
```shell
python insert.py --platform langchain --project_root_or_file my_path/langchain_doc_dir --project_name akcio_test --mode project
```
You can see the help for each arg with cmd:
```shell
python insert.py -h
```
```
usage: insert.py [-h] [--platform {towhee,langchain}] --project_root_or_file PROJECT_ROOT_OR_FILE --project_name PROJECT_NAME --mode {project,github,stackoverflow,custom}
                 [--url_domain URL_DOMAIN] [--emb_batch_size EMB_BATCH_SIZE] [--load_batch_size LOAD_BATCH_SIZE] [--enable_qa ENABLE_QA] [--qa_num_parallel QA_NUM_PARALLEL]

optional arguments:
  -h, --help            show this help message and exit
  --platform {towhee,langchain}
                        It is your option of platform to build the system.
  --project_root_or_file PROJECT_ROOT_OR_FILE
                        It can be a folder or file path containing your project information.
  --project_name PROJECT_NAME
                        It is your project name. It is also the collection_name in the vector database.
  --mode {project,github,stackoverflow,custom}
                        When mode == 'project', `project_root_or_file` is a repo root which contains **/*.md files. When mode == 'github', `project_root_or_file` can be a repo with '|', which
                        means "(namespace)|(repo_name)", or a root containing repo folders with '|'. When mode == 'stackoverflow', `project_root_or_file` can be a project folder containing
                        json files, or a root containing project folders.
  --url_domain URL_DOMAIN
                        When the mode is project, you can specify a url domain, so that the relative directory of your file is the same relative path added after your domain. When the mode is
                        github, there is no need to specify the url, the url path is the url of your github repo. When the mode is stackoverflow, there is no need to specify the url, because
                        the url can be obtained in the answer json.
  --emb_batch_size EMB_BATCH_SIZE
                        Batch size when extracting embedding.
  --load_batch_size LOAD_BATCH_SIZE
                        Batch size when loading to vector db.
  --enable_qa ENABLE_QA
                        Whether to use the generate question mode, which will use llm to generate questions related to doc chunks, and use questions to match instead of doc chunks. When the
                        mode is stackoverflow, no need to specify it.
  --qa_num_parallel QA_NUM_PARALLEL
                        The number of concurrent request when generating problems. If your openai account does not support high request rates, I suggest you set this value very small, such as
                        1, else you can use a higher num such as 8, or 16. When the mode is stackoverflow, no need to specify it.
```

## Clear doc

Todo

## Manage history

Todo