# atividade-heran-a
import java.util.Scanner;

public class Animal {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        Cachorro cachorro = new Cachorro();

        cachorro.fazerSom();

        String nome;
    }

    public void fazerSom () {
        System.out.println("Som genérico de animal");

    }
}
-----------------------------------------------------------

class Cachorro extends Animal {

    @Override
    public void fazerSom() {
        System.out.println("O cachorro late");

    }
}
-----------------------------------------------------------

import java.util.Scanner;

public class Veiculo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        Carro carro = new Carro();
        Bicicleta bicicleta = new Bicicleta();

        carro.mover();
        bicicleta.mover();


    }

    public void mover() {

        System.out.println("O veículo está se movendo");
    }
}
----------------------------------------------------------

public class Carro extends Veiculo {

    @Override
    public void mover() {

        System.out.println("O carro está se movendo rapidamente");


    }
}

----------------------------------------------------------------

public class Bicicleta extends Veiculo {

    @Override
    public void mover() {

        System.out.println("A Bicicleta está se movendo lentamente");

    }
}

----------------------------------------------------------------

public class Funcionario {

    protected String nome;
    protected Double SalarioBase;

    public Funcionario(Double SalarioBase, String nome) {
        this.SalarioBase = SalarioBase;
        this.nome = nome;
    }

    public Double calcularSalario() {
        return SalarioBase;

    }

    public void exibirInformacoes() {
        System.out.println("Nome: " + nome);
        System.out.println("Salário Base: R$" + SalarioBase);
        System.out.println("Salário Calculado: R$" + calcularSalario());
    }
}

------------------------------------------------------------------------

class Gerente extends Funcionario {
    private Double bonus;

    public Gerente(Double SalarioBase, String nome, Double bonus) {
        super(SalarioBase, nome);
        this.bonus = bonus;

    }

    @Override
    public Double calcularSalario() {
        return SalarioBase + bonus;
    }
}

-------------------------------------------------------------------------

public class Desenvolvedor extends Funcionario {

    public Desenvolvedor(Double SalarioBase, String nome) {
        super(SalarioBase, nome);
    }

    @Override
    public Double calcularSalario() {
        return SalarioBase * 1.10;
    }
}

-----------------------------------------------------------------------

public class Main {
    public static void main(String[] args) {

        Funcionario funcionario = new Funcionario(3000.0,"Joao");
        Gerente gerente = new Gerente(4000.0, "Maria", 1000.0);
        Desenvolvedor desenvolvedor = new Desenvolvedor(5000.0, "Carlos");

        System.out.println("Funcionário:");
        funcionario.exibirInformacoes();
        System.out.println();

        System.out.println("Gerente:");
        gerente.exibirInformacoes();
        System.out.println();

        System.out.println("Desenvolvedor:");
        desenvolvedor.exibirInformacoes();
    }
}

------------------------------------------------------------------------


