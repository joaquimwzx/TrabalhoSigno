# TrabalhoSigno
package trabalhosigno;

import java.util.Calendar;
import java.util.Scanner;

/**
 *
 * @author Joaquim Alves Data 10/04/2025
 */
public class TrabalhoSigno {

    public static void main(String[] args) {
        //Declaração de variaveis

        String nome, signo = null, corSorte = null;
        int sexo, diaNasc, mesNasc, anoNasc, diaAtual, mesAtual, anoAtual, idade, numeroSorte;
        Scanner ler = new Scanner(System.in);

        //Entrada de dados
        System.out.println("Qual e o seu nome");
        nome = ler.nextLine();
        //Veriicar se o nome tem mais que 8 caracteres
        if (nome.length() >= 8) {
            System.out.println("Seu nome não foi informado corretamente");
        }

        //Contiuação da entrada de dados
        System.out.println("Informe o seu sexo, 1 para feminino e 2 para masculino,numeros maiores que 2 ira ser considerado masculino");
        sexo = ler.nextInt();
        System.out.println("Digite o dia de nascimento 1-31");
        diaNasc = ler.nextInt();
        System.out.println("Digite o mês de nascimento 1-12");
        mesNasc = ler.nextInt();
        System.out.println("Digite o ano de nascimento 1900-2025");
        anoNasc = ler.nextInt();

        //Data Atual
        Calendar hoje = Calendar.getInstance();
        diaAtual = hoje.get(Calendar.DATE);
        mesAtual = hoje.get(Calendar.MONTH) + 1; //Janeiro é zero, por isso o 1
        anoAtual = hoje.get(Calendar.YEAR);

        //Calculo da idade
        idade = anoAtual - anoNasc;
        if (mesNasc > mesAtual || (mesNasc == mesAtual && diaNasc > diaAtual)) {
            idade--;
        }

        //Determinando o signo
        if ((mesNasc == 3 && diaNasc >= 21) || (mesNasc == 4 && diaNasc <= 19)) {
            signo = "Áries";
        } else if ((mesNasc == 4 && diaNasc >= 20) || (mesNasc == 5 && diaNasc <= 20)) {
            signo = "Touro";
        } else if ((mesNasc == 5 && diaNasc >= 21) || (mesNasc == 6 && diaNasc <= 20)) {
            signo = "Gêmeos";
        } else if ((mesNasc == 6 && diaNasc >= 21) || (mesNasc == 7 && diaNasc <= 22)) {
            signo = "Câncer";
        } else if ((mesNasc == 7 && diaNasc >= 23) || (mesNasc == 8 && diaNasc <= 22)) {
            signo = "Leão";
        } else if ((mesNasc == 8 && diaNasc >= 23) || (mesNasc == 9 && diaNasc <= 22)) {
            signo = "Virgem";
        } else if ((mesNasc == 9 && diaNasc >= 23) || (mesNasc == 10 && diaNasc <= 22)) {
            signo = "Libra";
        } else if ((mesNasc == 10 && diaNasc >= 23) || (mesNasc == 11 && diaNasc <= 21)) {
            signo = "Escorpião";
        } else if ((mesNasc == 11 && diaNasc >= 22) || (mesNasc == 12 && diaNasc <= 21)) {
            signo = "Sagitário";
        } else if ((mesNasc == 12 && diaNasc >= 22) || (mesNasc == 1 && diaNasc <= 19)) {
            signo = "Capricórnio";
        } else if ((mesNasc == 1 && diaNasc >= 20) || (mesNasc == 2 && diaNasc <= 18)) {
            signo = "Aquário";
        } else {

        }

        //Numero da sorte
        numeroSorte = 1 + (int) (Math.random() * 99);

        //Cor da sorte
        int numCor = 1 + (int) (Math.random() * 5);
        if (numCor == 1) {
            corSorte = "vermelho";
        } else if (numCor == 2) {
            corSorte = "verde";
        } else if (numCor == 3) {
            corSorte = "preto";
        } else if (numCor == 4) {
            corSorte = "branco";
        } else if (numCor == 5) {
            corSorte = "azul";
        }

        //Saida de dados
        //mulheres
        if (sexo == 1) {
            System.out.println("Sra. " + nome + ", nascida em " + diaNasc + "/" + mesNasc + "/" + anoNasc
                    + ", é do signo de " + signo + ". Você tem " + idade + " anos. Seu número da sorte é " + numeroSorte + " e sua cor é " + corSorte + ".");
            //homens
        } else {
            System.out.println("Sr. " + nome + ", nascido em " + diaNasc + "/" + mesNasc + "/" + anoNasc
                    + ", é do signo de " + signo + ". Você tem " + idade + " anos. Seu número da sorte é " + numeroSorte + " e sua cor é " + corSorte + ".");
        }
    }

}
