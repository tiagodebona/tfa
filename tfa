#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <ctype.h>
#include <time.h>
#include "admin.h"
#include "cor.h"
#include "leitura.h"
#include "login.h"
#include "estruturas.h"
#include "usuario.h"

int main(){

	int op;

	FILE *fp = fopen("usuario.txt", "a");
	if(!ftell(fp)){
		
		printf("\tNão há nenhum administrador cadastrado\n\n");
		cadastrar(1);
		fclose(fp);
		
		
        printf("\nAdministrador cadastrado com sucesso!\n\n");
        __fpurge(stdin);
		getchar();		  
	}

	system("clear");

	Usuario usuario_logado;
	while(op != 5 && op != 7){

		usuario_logado = loginTodos();
		
		if(usuario_logado.tipo == 1){
			op = 0;
			while(op != 4 && op != 5){
				op = menuAdm();

				if(op == 1){
					cadastrar(0);
				}
				else if(op == 2){
					visualizarUsuarios();
				}
				else if(op == 3){
					removerUsuario();
				}
			}
		}
		else{
			op = 0;
			while(op != 6 && op != 7){
				op = menuUser();

				if(op == 1){
					cadastrarClube(0);
				}
				else if(op == 2){
					continuarCadastro();
				}
				else if(op == 3){
					modificarDados(usuario_logado.login);
				}
			}
		}
	}
}
