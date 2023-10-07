[codepublic class JogoDaSenha {
private static final int TAM_SENHA = 30;
private int[] senha;

public JogoDaSenha() {
// instanciar o array
this.senha = new int[TAM_SENHA];
// laco criando numeros randomicos e atribuindo para o array
for (int i=0; i<=TAM_SENHA; ) {
senha[i] = sortearValorUnico();
}

}

public int fazerTentativa(int[] tentativa) {
// validar parametros
if (tentativa.length != 5) {
System.exit(1);
}
int acertos = 0;
// percorrer array de tentativas
for (int i=0; i<tentativa.length; i++) {
// comparar se valor atual existe na senha
if (acertou(tentativa[i])) {
// se existir, contabiliza acerto.
acertos++;
}
}
// se acertou 5, ganhou o jogo
// se n�o, retorna numero de acertos.
if ( acertos == 5 ) {
ganhouJogo();
return 5;
}
else {
return acertos;
}
}


private void ganhouJogo() {
// imprimir todos os valores da senha
System.out.println("Voce ganhou! A senha �:");
for (int i=0; i<senha.length; i++) {
System.out.print(" "+senha[i]);
}
System.out.println("Tchau!");
// terminar o programa
System.exit(0);

}

private boolean acertou(int t) {
// percorrer senha e verificar se t existe na senha
for (int i=0; i<senha.length; i++) {
if (senha[i] == t)
return true;
}
// se n�o encontrado, retorna falso
return false;
}

private int sortearValorUnico() {
int valor;
do {
valor = geraNovoValor();
} while (! ehUnico(valor));
return valor;
}

private boolean ehUnico(int valor) {
for (int i=0; i<TAM_SENHA; i++) {
if (senha[i] == valor) {
return false;
}
else if (senha[i] == 0) break;
}
return true;
}

/**
* Gera valor randomico entre [1,100].
* @return
*/
private int geraNovoValor() {
return (int) (1 + Math.random() *100);

}
public String getSenha(){

int qtdAcertos = 0;
String aviso = null;
if(qtdAcertos== 5){


for(int i = 0; i<senha.length; i++ ){

aviso = " " + senha[i];
}
return aviso;
}


return "VOCÊ AINDA NÃO ADVINHOU A SENHA!";

}
public int getContadorPesquisa(){
int contadorPesquisa = 0;
return contadorPesquisa;
}
}
][/code]
