package trabalhosigno1;

import java.util.Calendar;
import java.util.Scanner;

/**
 *
 * @author Joaquim
 */
public class TrabalhoSigno1 {

    public static void main(String[] args) {

        //Declarando Variaveis
        String nome, cor, signo, sexo;
        int anoNasc, diaNasc, mesNasc, numeroSorte, idade, numCor;
        Scanner ler = new Scanner(System.in);
        Calendar hoje = Calendar.getInstance();

        //Entrada de dados das informaçãoes do usuário
        System.out.println("Qual seu nome?");
        nome = ler.nextLine();
        System.out.println("Digite 1 para mulher ou 2 para homem:");
        sexo = ler.nextLine();
        System.out.println("Digite o dia de nascimento:");
        diaNasc = ler.nextInt();
        System.out.println("Digite o mês de nascimento:");
        mesNasc = ler.nextInt();
        System.out.println("Digite o ano de nascimento:");
        anoNasc = ler.nextInt();

        //verificar se o nome tem mais ou igual 8 caracteres 
        if (nome.length() >= 8) {
            System.out.println("Valido");
        } else {
            System.out.println("Seu nome não foi informado corretamente,invalido");
            return;
        }

        //Processamento pra ver se fez aniversario ou não
        int diaAtual = hoje.get(Calendar.DATE);
        int mesAtual = hoje.get(Calendar.MONTH) + 1;
        int anoAtual = hoje.get(Calendar.YEAR);
        idade = anoAtual - anoNasc;
        if (mesNasc > mesAtual || (mesNasc == mesAtual && diaNasc > diaAtual)) {
            idade--;
        }

        //entrada de dados do signo
        signo = "Aries";

        //As condições de dia/mes/ano de nascimento
        if (diaNasc >= 1 && diaNasc <= 31
                && mesNasc >= 1 && mesNasc <= 12
                && anoNasc >= 1900 && anoNasc <= anoAtual) {

            //Aries
            if ((diaNasc >= 21 && diaNasc <= 31 && mesNasc == 3)
                    || (diaNasc >= 1 && diaNasc <= 20 && mesNasc == 4)) {
                signo = "Aries";
                //Touro
            } else if ((diaNasc >= 21 && diaNasc <= 30 && mesNasc == 4)
                    || (diaNasc >= 1 && diaNasc <= 20 && mesNasc == 5)) {
                signo = "Touro";
                //Gêmeos
            } else if ((diaNasc >= 21 && diaNasc <= 31 && mesNasc == 5)
                    || (diaNasc >= 1 && diaNasc <= 20 && mesNasc == 6)) {
                signo = "Gêmeos";
                //Câncer
            } else if ((diaNasc >= 21 && diaNasc <= 30 && mesNasc == 6)
                    || (diaNasc >= 1 && diaNasc <= 21 && mesNasc == 7)) {
                signo = "Câncer";
                //Leão
            } else if ((diaNasc >= 22 && diaNasc <= 31 && mesNasc == 7)
                    || (diaNasc >= 1 && diaNasc <= 22 && mesNasc == 8)) {
                signo = "Leão";
                //Virgem
            } else if ((diaNasc >= 23 && diaNasc <= 31 && mesNasc == 8)
                    || (diaNasc >= 1 && diaNasc <= 22 && mesNasc == 9)) {
                signo = "Virgem";
                //Libra
            } else if ((diaNasc >= 23 && diaNasc <= 30 && mesNasc == 9)
                    || (diaNasc >= 1 && diaNasc <= 22 && mesNasc == 10)) {
                signo = "Libra";
                //Escorpião
            } else if ((diaNasc >= 23 && diaNasc <= 31 && mesNasc == 10)
                    || (diaNasc >= 1 && diaNasc <= 21 && mesNasc == 11)) {
                signo = "Escorpião";
                //Sagitário
            } else if ((diaNasc >= 22 && diaNasc <= 30 && mesNasc == 11)
                    || (diaNasc >= 1 && diaNasc <= 21 && mesNasc == 12)) {
                signo = "Sagitário";
                //Capricórnio
            } else if ((diaNasc >= 22 && diaNasc <= 31 && mesNasc == 12)
                    || (diaNasc >= 1 && diaNasc <= 20 && mesNasc == 1)) {
                signo = "Capricórnio";
                //Aquário
            } else if ((diaNasc >= 21 && diaNasc <= 31 && mesNasc == 1)
                    || (diaNasc >= 1 && diaNasc <= 19 && mesNasc == 2)) {
                signo = "Aquário";
                //Peixes
            } else {
                signo = "Peixes";
            }
        } else {
            System.out.println("Dia,mes, ou ano invalidos");
        }
        //Verificando se esta correto o mes,ano e dia e se nao estiver vai aparecer esta mensagem

        //Geraando um numero da sorte de 1 a 99
        numeroSorte = 1 + (int) (Math.random() * 99);

        //Gerando a sua cor de 1 a 7
        numCor = 1 + (int) (Math.random() * 7);

        //entrada de dados da cor
        cor = "azul";

        //Gerando numero da sua cor
        if (numCor == 1) {
            cor = "Rosa";
        } else if (numCor == 2) {
            cor = "Verde";
        } else if (numCor == 3) {
            cor = "Amarelo";
        } else if (numCor == 4) {
            cor = "Roxo";
        } else if (numCor == 5) {
            cor = "Laranja";
        } else if (numCor == 6) {
            cor = "Preto";
        } else if (numCor == 7) {
            cor = "Branco";
        } else {
            cor = "Azul";
        }

        //Saída de dados
        //feminino
        if (sexo.equals("1")) {
            System.out.println("Sra." + nome + ", nascida em [" + diaNasc + "/" + mesNasc + "/" + anoNasc + "], "
                    + "é do signo de " + signo + "." + " Você tem " + idade + " anos." + " Seu número da sorte é " + numeroSorte
                    + " e sua cor é " + cor + ".");

            //masculino
        } else {
            System.out.println("Sr." + nome + ", nascida(o) em [" + diaNasc + "/" + mesNasc + "/" + anoNasc + "], "
                    + "é do signo de " + signo + "." + " Você tem " + idade + " anos." + " Seu número da sorte é " + numeroSorte
                    + " e sua cor da sorte é " + cor + ".");
        }

    }

}
