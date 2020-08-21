
##
##    	Autor: Smythy Costa
##      Email: smythy.costa@gmail.com
##      GITHub: github.com/smythycosta
##

	

# 1 - CRENDENCIAS DO USUARIO
	git config --global user.name "John Doe" 			#sua identidade.
	git config --global user.email johndoe@example.com 		#seu email.
	git config -l   						#listando as configurações padrao do user.
	git remote -v   						#caminho do diretorio.


# 2 - SINCRONIZANDO
	git init 						#para criar um novo repositório.
	git init --bare 					#pasta do central do projeto.
	git remote add origin /caminho/para/o/repositório 	#para sincronizar as pastas.
	git clone /caminho/para/o/repositório 			#crie uma cópia de trabalho em um repositório local.
	git clone usuário@servidor:/caminho-REPOSITORIO/	#usar um servidor remoto.


# 3 - ALTERANDO O DIRETORIO DE ORIGEM
	git remote set-url origin url


# 4 - TRABALHANDO DE FORMA BÁSICA
	git add arquivo								#ADD ARQUIVO ESPECIFICO.
	git add .								#ADD ALL.
	git commit -m "comentários das alterações"		                #COMENTADO AS ALTERAÇÕES.
	git push origin master							#enviar estas alterações ao seu repositório remoto.
	git remote add origin <servidor> 				        #conectar seu repositório a um servidor remoto .


# 5 - LOGS
	git log 			#mostar todos os commits com detalhes, ordena pelos commits mais recentes.
	git log --name--status 		#mostar todos os commits com detalhes dos codigos.
	git log --oneline		#lista os mostrando somente a descricao do commit.
	git log --pretty=format:"" 	#personalisando o log.


# 6 - VERIFICANDO AS ALTERAÇÕES
	git diff					#mostra as alteraçoes feitas nos arquivos antes do commit.
	git diff nome_arquivo 		                #alteraçoes feitas somente neste arquivo.
	git diff commit1 commit2                        #vendo as diferenças entre os commits.


# 7 - COMPARANDO DIRETORIOS
	git status 			#compara (WORKING DIRCTORY) X (STAGING AREA).
	git diff --staged		#compara o (STAGING AREA) X (GIT REPOSITORY).


# 8 - IGINORANDO ARQUIVOS
	.gitignore 				#iginorar arquivos e pastas.


# 9 - BRANCH
	git branch						#lista as branchs.
	git branch nome_branch					#criar uma branchs, obs log desta nova, se basean na branch que esta no momento de criacao.
	git checkout --orphan nome_branch			#criar uma branch, obs log sera vazio, orfao.
	git checkout nome_branch				#mudando de brach.
	git merge nome_branch 					#sincronizando, branch que ta trabalhando c/ branch passada pelo merge.
	git checkout -b nome_branch				#criar uma branch e te joga para dentro da q foi criada.
	git checkout id_commit -b nome_branch 			#criar uma branch baseada com o log do commit passado.
	git checkout -m novo_nome				#renomeando a branche que esta trabalhando.
	git branch -D nome_branch				#deletando a branche.


# 10 - ERROS
	git merge --abort       	#aborta o merge em caso de erros.
	git reset 			#desfaz o commit antes do add.


# 11 - CHECKOUT PROJECT FOR DEBUG
	git checkout id_commit 					#Para pegar uma versao antida do projeto.
	git fetch && git checkout background 			#baixando uma branch para desenvolvimento.


# 12 - CASOS RAROS 
	
	* pegar alterações de em um branch/ramo específico de um repositório remoto no GIT?
		
	https://pt.stackoverflow.com/questions/6172/como-pegar-alterações-de-em-um-branch-ramo-específico-de-um-repositório-remoto-n
		

# 13 - REVERTENDO CODIGO

How to discard all uncommitted changes.

https://pt.stackoverflow.com/questions/323668/como-descartar-todas-as-altera%C3%A7%C3%B5es-n%C3%A3o-commitadas

	git checkout -- . 		#reverter todas as alterações em arquivos que estavam versionados.
	git clean -f -d			#apagar todos os arquivos e diretórios criados
	git reset HEAD -- .		#remove arquivos q foram add no HEAD, mais n foi commitado.


# 14 - Revertendo Merge

	git revert -m 1 HEAD

	https://stackoverflow.com/questions/1809484/git-how-to-reverse-merge-a-commit


# 15 - Revertendo commit

	git log --stat 					# lista dos commits.
	git reset --hard 19ccc39 			# Revert(delete) commit, remover do codigo.

	https://pt.stackoverflow.com/questions/323668/como-descartar-todas-as-altera%C3%A7%C3%B5es-n%C3%A3o-commitadas
	
	https://stackoverflow.com/questions/1338728/delete-commits-from-a-branch-in-git
	

# 16 - Merge a specific commit

* cherry-pick
* rebase

	https://stackoverflow.com/questions/881092/how-to-merge-a-specific-commit-in-git
	
	https://stackoverflow.com/questions/1670970/how-to-cherry-pick-multiple-commits


# 17 - Cannot see new remote branch

	git branch -r
	git ls-remote origin
	git fetch origin <name_branch>:<name_branch>

[references] (https://stackoverflow.com/questions/12762922/git-cannot-see-new-remote-branch/46081117#:~:text=First%2C%20double%20check%20that%20the,references%20from%20the%20remote%20repository)




# 18 - Superficial Clone

	git clone --depth=1 http://10.999.999.999/xxx/src/src-xxx.git
	cd <project dir>
	git fetch --depth=4 					# depth=N, with increasing N
	git fetch --depth=100 					# depth=N, with increasing N
	git fetch --depth=500 					# depth=N, with increasing N
	git fetch --unshallow 					# end

[references] (https://stackoverflow.com/questions/38618885/error-rpc-failed-curl-transfer-closed-with-outstanding-read-data-remaining)







