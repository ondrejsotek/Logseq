- Git hooks - umístit do .git/hooks
	- post-commit
		- ```bash
		  #!/bin/sh
		  git push origin master
		  ```
	- pre-commit
	- u obou souborů nastavit chmod +x
	-