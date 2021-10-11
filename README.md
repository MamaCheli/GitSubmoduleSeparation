# Инструкция

1. Клонирую свой репозиторий GitSubmoduleSeparation и репозиторий с проектом tensorflow

2. В tensorflow оставляю всё нужное в репозитеории с проектом `git filter-branch --subdirectory-filter tensorflow/contrib -- --all`

3. `mkdir move-folder`
`mv * move-folder`
Чтобы все файлы были внутри той же папки, что и раньше, а не в корне нового репозитория.

4. Всё коммичу. Затем добавляю удаленный репозиторий NewRepoGitSubmoduleSeparation и кидаю туда все изменения:
`git add .`
`git commit -m "Preparing to extract folder"`
`git remote add main "https://github.com/MamaCheli/NewRepoGitSubmoduleSeparation.git"`
`git push -u origin r1.14`

5. Наконец, в репозитории GitSubmoduleSeparation, я создаю ссылку на NewRepoGitSubmoduleSeparation:
`git submodule add "https://github.com/MamaCheli/NewRepoGitSubmoduleSeparation.git"`
`git add --all`
`git commit -am "Link repo"`
`git push origin`
