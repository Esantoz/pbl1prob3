/*******************************************************************************
Autor: Esdras Evangelista de Sena Santos
Componente Curricular: Algoritmos I
Concluido em: 27/12/2018
Declaro que este código foi elaborado por mim de forma individual e não contém nenhum
trecho de código de outro colega ou de outro autor, tais como provindos de livros e
apostilas, e páginas ou documentos eletrônicos da Internet. Qualquer trecho de código
de outra autoria que não a minha está destacado com uma citação para o autor e a fonte
do código, e estou ciente que estes trechos não serão considerados para fins de avaliação.
******************************************************************************************/
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>

//estrutura do candidato
typedef struct candidato{
	char *codigo;
	char *proposta;
	char *autor;
	char *orientador;
	int *area;
	char *nomearea;
	int nota;
	int *status;
	time_t *data;
	int dia;
	float *horario;
}candidato;
candidato pales[700];
//prototipos das funcoes
void sortcancel(candidato lista[]);
void sort(candidato lista[]);
void lerbin();
void submissao();
void avaliacao();
void alocar();
void cancelar();
void arqbin();
//funcao para organizar por status
void sortcancel(candidato lista[]){
	int i,j,x,min;
	int t = 300;
	for(i = 0;i < t-1; i++){
		min = i;
		for(j = i+1;j < t;j++){
			if(lista[j].status < lista[min].status){
				min = j;
			}
		}
		x = *lista[min].status;
		lista[min] = lista[i];
		lista[i].status = &x;
	}
}
//funcao para organizar por nota
void sort(candidato lista[]){
	int i,j,x,min;
	int t = 16;
	for(i = 0;i< t-1;i++){
		min = i;
		for(j = i+1;j < t;j++){
			if(lista[j].nota < lista[min].nota && lista[j].area == lista[min].area){
				min = j;
			}
		}
		x = lista[min].nota;
		lista[min] = lista[i];
		lista[i].nota = x;
	}
}
//funcao para fazer a submissao de propostas
void submissao(){
	char l[700][200];
	char aux[3];
	int i = 0;
	int c;
	int r;
	FILE *file; 
	//verifica se o arquivo auxiliar ja foi criado
	if(file = fopen("auxbin.txt","rb")){
		for(c = 0;c <= 224;c++){
			fread(pales[c].area,sizeof(int),1,file);
			fread(pales[c].horario,sizeof(float),1,file);
			fread(pales[c].proposta,sizeof(char),80,file);
			fread(pales[c].codigo,sizeof(char),7,file);
			fread(pales[c].status,sizeof(int),1,file);
		}	
		i = c;		
	}
	int auxarea[7];
	FILE *file2 = fopen("ExemploArquivoEntrada.txt","w+");
	char resp;
	char resp2;
	char resp3;
	int o = 0;
	while(1){
		//pega a area como um numero
		while(1){
			puts("Area");
			puts("ciencias da saude.[1]");
			puts("ciencias exatas.[2]");
			puts("ciencias agrarias.[3]");
			puts("engenharias.[4]");
			puts("ciencias sociais aplicadas.[5]");
			puts("ciencias humanas.6");
			puts("linguistica,letras e artes.[7]");
			scanf("%i",pales[i].area);
			if(*pales[i].area >= 1 && *pales[i].area <= 7){
				break;
			}
			else{
				continue;
			}
		}
		//define o nome da area a partir do numero digitado
		pales[i].nomearea = (char *)malloc(sizeof(char)*35);
		if(*pales[i].area == 1)
			pales[i].nomearea = "ciencias da saude"; 
		else if(*pales[i].area == 2)
			pales[i].nomearea = "ciencias exatas";
		else if(*pales[i].area == 3)
			pales[i].nomearea = "ciencias agrarias";
		else if(*pales[i].area == 4)
			pales[i].nomearea = "engenharias";
		else if(*pales[i].area == 5)
			pales[i].nomearea = "ciencias sociais aplicadas";
		else if(*pales[i].area == 6)
			pales[i].nomearea = "ciencias humanas";
		else if(*pales[i].area == 7)	
			pales[i].nomearea = "linguistica,letras e artes";
		switch(*pales[i].area){
			//pega as areas e define os codigos de cada proposta
			case 1:
				auxarea[0] += 1;
				if(auxarea[0] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[0]);
				else if(auxarea[0] < 100)
					sprintf(pales[i].codigo,"0%i-0%i",pales[i].area,auxarea[0]);					
				break;
			case 2:
				auxarea[1] += 1;
				if(auxarea[1] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[1]);
				else if(auxarea[1] < 100)
					sprintf(pales[i].codigo,"0%i-0%i",pales[i].area,auxarea[1]);
				break;
			case 3:
				auxarea[2] += 1;
				if(auxarea[2] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[2]);
				else if(auxarea[2] < 100)
					sprintf(pales[i].codigo,"0%i-0%i",pales[i].area,auxarea[2]);
				break;
			case 4:
				auxarea[3] += 1;
				if(auxarea[3] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[3]);
				else if(auxarea[3] < 100)
					sprintf(pales[i].codigo,"0%i-0%i",pales[i].area,auxarea[3]);
				break;
			case 5:
				auxarea[4] += 1;
				if(auxarea[4] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[4]);
				else if(auxarea[4] < 100)
					sprintf(pales[i].codigo,"0%i-0%i",pales[i].area,auxarea[4]);
				break;
			case 6:
				auxarea[5] += 1;
				if(auxarea[5] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[5]);
				else if(auxarea[5] < 100)
					sprintf(pales[i].codigo,"0%i-0%i",pales[i].area,auxarea[5]);
				break;
			case 7:
				auxarea[6] += 1;
				if(auxarea[6] < 10)
					sprintf(pales[i].codigo,"0%i-00%i",pales[i].area,auxarea[6]);
				else if(auxarea[6] < 100)
					sprintf(pales[i].codigo,"0%i-%.1fi",pales[i].area,auxarea[6]);
				break;
			default:
				printf("opção invalida!\n");
				break;
		};
		//pega o titulo da proposta
		pales[i].proposta = (char *)malloc(sizeof(char)*100);
		puts("Titulo da proposta:");
		scanf("%s",pales[i].proposta);
		//pega o nome do autor
		puts("A proposta tem co-autor?[s/n] ");
		scanf("%c",&resp);
		pales[i].autor = (char *)malloc(40);
		if(resp == 's'){
			//se tiver co autor ele realoca um espacao maior
			pales[i].autor = (char *)realloc(pales[i].autor,80);
			puts("Nome do autor e co-autor(use virgula para separar):");
			scanf("%s",pales[i].autor);
		}
		else{
			//se nao, ele so usa o espaco alocado inicialmente
			printf("Nome do autor: ");
			scanf("%s",pales[i].autor);
		}
		puts("A proposta tem co-orientador?[s/n] ");
		scanf("%c",&resp2);
		//pega o orientador
		pales[i].orientador = (char *)malloc(40);
		if(resp2 == 's'){
			//se tiver co-orientador ele realoca um espaco maior
			pales[i].orientador = (char *)realloc(pales[i].orientador,80);
			puts("Nome do orientador e co-orientador(use virgula para separar):");
			scanf("%s",pales[i].orientador);
		}
		else{
			//se nao,ele usa o espaco reservado inicialmente
			printf("Nome do orientador: ");
			scanf("%s",pales[i].orientador);
		}
		time(pales[i].data);
		fprintf(file2,"\n\n%s\n%s\n%s\n%s\n%i",pales[i].codigo,pales[i].proposta,pales[i].autor,pales[i].orientador,pales[i].area);
		printf("Quer cadastra mais um palestrante?[s/n]: ");
		scanf("%c",&resp3);
		for(int o = 0;o < 7;o++){
			if(auxarea[o] == 0){
				printf("voce não pode continuar, a area %i nao tem cadastrados",auxarea[o]);
				break;
			}
			else{
				int a = 0;
				while(fgets(l[a],200,file) != NULL){
					a++;
				}
				//grava no arquivo de texto
				a++;
				strcpy(l[a],pales[i].codigo);
				a++;
				strcpy(l[a],pales[i].proposta);
				a++;
				strcpy(l[a],pales[i].nomearea);
				a++;
				strcpy(l[a],pales[i].autor);
				a++;
				strcpy(l[a],pales[i].orientador);
				for(int u = 0;u < 3;u++){
					aux[i] = l[0][i];
				}
				r = atoi(aux) + i;
				fprintf(file,"%i\n",r);
				while(fputs(l[o],file) != '\0'){
					o++;
				}
				fclose(file);
				avaliacao();
				return;
			}
		}
		++i;
	}
}
void avaliacao(){
	char resp;
	int i = 0;
	int c = 0;
	char m[100][200];
	//arquivo binario auxiliar
	FILE *file2 = fopen("auxbin.txt","wb");
	FILE *file = fopen("ExemploArquivoEntrada.txt","r");
	while(fgets(m[i],200,file) != '\0'){
		printf("%s\n",m[i]);
		i++;
	}
	for(c = 0;c < 224;c++){
		printf("Proposta: %s\n",pales[c].proposta);
		printf("digite a nota: ");
		scanf("%i",&pales[c].nota);
		printf("\nAprovado ou Reprovado?[A/R]");
		scanf("%c",&resp);
		if(resp == 'A'){
			alocar();
			//se foi aprovado recebe o valor de 1
			*pales[c].status = 1;
			fwrite(pales[c].area,sizeof(int),1,file2);
			fwrite(pales[c].horario,sizeof(float),1,file2);
			fwrite(pales[c].proposta,sizeof(char),80,file2);
			fwrite(pales[c].codigo,sizeof(char),7,file2);
			fwrite(pales[c].status,sizeof(int),1,file2);
		}
		else{
			//se foi reprovado recebe o vslor de 0
			pales[c].status = 0;
		}
		c++;
	}
	return;
}
//essa funcao vai alocar as propostas em dias da semana
void alocar(){
	int i;
	int o;
	int c = 0;
	int st=0,tq=0,qq=0,qs=0,ss=0,sd=0,ds=0;
	char *dom[32],*seg[32],*ter[32],*qua[32],*qui[32],*sex[32],*sab[32],*ex[200];
	float hora[32];
	hora[0] = 8.0;
	sort(pales);
	//enchendo os vetores com "ab" para indentificar se ele esta sendo ocupado ou nao
	for(int i = 0;i <= 32;i++){
		dom[i] = "ab";
		seg[i] = "ab";
		ter[i] = "ab";
		qua[i] = "ab";
		qui[i] = "ab";
		sex[i] = "ab";
		sab[i] = "ab";
	}
	for(o = 1;o <= 32;o++){
		if(hora[o] == 12.0){
			hora[o] += 2.0;
			continue;
		}
		hora[o] = hora[o-1] + 0.15;
	}
	for(i = 0;i < 224;i++){
		if(*pales[i].status == 1){
			if(*pales[i].area == 1){
				for(;st < 32;st++){
					/*aqui verifica se o vetor esta ocupado ou nao, se ele for igual a "ab" e por que esta vazio*/
					if(seg[st] == "ab" && st % 2 == 0){
						seg[st] = pales[st].proposta;
						pales[st].dia = 1;
						*pales[st].horario = hora[st];
						continue;
					}
					else if(ter[st] == "ab"){
						ter[st] = pales[st].proposta;
						pales[st].dia = 2;
						*pales[st].horario = hora[st];
						break;
					}
				}
			}
			else if(*pales[i].area == 2){
				for(;tq < 32;tq++){
					if(ter[tq] == "ab" && tq % 2 == 0){
						ter[tq] = pales[tq].proposta;
						pales[tq].dia = 2;
						*pales[tq].horario = hora[tq];
						continue;
					}
					else if(qua[tq] == "ab"){
						qua[tq] = pales[tq].proposta;
						pales[tq].dia = 3;
						*pales[tq].horario = hora[tq];
						break;
					}
				}
			}
			else if(*pales[i].area == 3){
				for(;qq < 32;qq++){
					if(qua[qq] == "ab" && qq % 2 == 0){
						qua[qq] = pales[qq].proposta;
						pales[qq].dia = 3;
						*pales[qq].horario = hora[qq];
						continue;
					}
					else if(qui[qq] == "ab"){
						qui[qq] = pales[qq].proposta;
						pales[qq].dia = 4;
						*pales[qq].horario = hora[qq];
						break;
					}
				}
			}
			else if(*pales[i].area == 4){
				for(;qs < 32;qs++){
					if(qui[qs] == "ab" && qs % 2 == 0){
						qui[qs] = pales[qs].proposta;
						pales[qs].dia = 4;
						*pales[qs].horario = hora[qs];
						continue;
					}
					else if(sex[qs] == "ab"){
						sex[qs] = pales[qs].proposta;
						pales[qs].dia = 5;
						*pales[qs].horario = hora[qs];
						break;
					}
				}
			}
			else if(*pales[i].area == 5){
				for(;ss < 32;ss++){
					if(sex[ss] == "ab" && ss % 2 == 0){
						sex[ss] = pales[ss].proposta;
						pales[ss].dia = 5;
						*pales[ss].horario = hora[ss];
						continue;
					}
					else if(sab[ss] == "ab"){
						sab[ss] = pales[ss].proposta;
						pales[ss].dia = 6;
						*pales[ss].horario = hora[ss];
						break;
					}
				}
			}
			else if(*pales[i].area == 6){
				for(;sd < 32;sd++){
					if(sab[sd] == "ab" && sd % 2 == 0){
						sab[sd] = pales[sd].proposta;
						pales[sd].dia = 6;
						*pales[sd].horario = hora[sd];
						continue;
					}
					else if(dom[sd] == "ab"){
						dom[sd] = pales[sd].proposta;
						pales[sd].dia = 7;
						*pales[sd].horario = hora[sd];
						break;
					}
				}
			}
			if(*pales[i].area == 7){
				for(;ds < 32;ds++){
					if(dom[ds] == "ab" && ds % 2 == 0){
						dom[ds] = pales[ds].proposta;
						pales[ds].dia = 7;
						*pales[ds].horario = hora[ds];
						continue;
					}
					else if(seg[ds] == "ab"){
						seg[ds] = pales[ds].proposta;
						pales[ds].dia = 1;
						*pales[ds].horario = hora[ds];
						break;
					}
				}	
			}	
		}
	}
}
//essa funcao vai cancelar proposta
void cancelar(){
	char aux[7];
	int a=0;
	int p;
	int u = 0;
	FILE *file = fopen("auxbin.txt","rb"); 
	int r;
	printf("digite o codigo: ");
	gets(aux);
	for(int c = 0;c < 224;c++){
		fread(pales[c].area,sizeof(int),1,file);
		fread(pales[c].proposta,sizeof(char),80,file);
		fread(pales[c].codigo,sizeof(char),7,file);
		fread(pales[c].status,sizeof(int),1,file);
		fseek(file,a+=95,SEEK_CUR);
		if(pales[u].codigo == aux){
			pales[u].status = 0;
		}
	}
	/*essa funcao vai ser chamada para organizar as propostas,pelo seu status*/
	sortcancel(pales);
}
//essa funcao vai escrever o arquivo binario
void arqbin(){
	int i = 0;
	FILE *file = fopen("fbin.txt","wb");
	for(int i = 0;i < 224;i++){
		fwrite(pales[i].data,sizeof(long int),1,file);
		fwrite(pales[i].nomearea,sizeof(char),35,file);
		fwrite(pales[i].horario,sizeof(float),1,file);
		fwrite(pales[i].proposta,sizeof(char),100,file);
		++i;
	}
}
//essa funcao vai ler o arquivo binario
//e mostra a programacao
void lerbin(){
	int i = 0;
	FILE *file = fopen("fbin.txt","rb");
	printf("Data\tAre\tHora\tProposta");
	for(int i = 0;i < 224;i++){
		fread(pales[i].data,sizeof(long int),1,file);
		fread(pales[i].nomearea,sizeof(char),35,file);
		fread(pales[i].horario,sizeof(float),1,file);
		fread(pales[i].proposta,sizeof(char),100,file);
		printf("%i\t",pales[i].data);
		printf("%s\t",pales[i].nomearea);
		printf("%f\t",pales[i].horario);
		printf("%s\n",pales[i].proposta);
		++i;
	}
}
main(){
	int resp;
	while(1){
		//opcoes de menu
		printf("==========MENU==========");
		printf("submeter nova proposta.[1]\n");
		printf("cancelar proposta.[2]\n");
		printf("ler programacao.[3]\n");
		scanf("%i",&resp);
		switch(resp){
			//submeter uma nova proposta
			case 1:
				submissao();
				break;
			//cancelar proposta	
			case 2:
				cancelar();
				break;
			//ler programacao	
			case 3:
				lerbin();
				break;
			default:
				printf("opcao nao existe tente novamente");
				break;
		};	
	}	
}
