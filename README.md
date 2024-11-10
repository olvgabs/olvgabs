public class Cliente {
    private String nome;
    private String cpf;

    // Construtor
    public Cliente(String nome, String cpf) {
        this.nome = nome;
        this.cpf = cpf;
    }

    // Métodos getters
    public String getNome() {
        return nome;
    }

    public String getCpf() {
        return cpf;
    }

    // Método para exibir informações do cliente
    public void exibirInformacoes() {
        System.out.println("Nome do Cliente: " + nome);
        System.out.println("CPF do Cliente: " + cpf);
    }
}
import java.util.ArrayList;
import java.util.List;

public class Profissional {
    private String nome;
    private List<Cliente> clientesAtendidos;

    // Construtor
    public Profissional(String nome) {
        this.nome = nome;
        this.clientesAtendidos = new ArrayList<>();
    }

    // Métodos getters
    public String getNome() {
        return nome;
    }

    public List<Cliente> getClientesAtendidos() {
        return clientesAtendidos;
    }

    // Método para adicionar cliente
    public void adicionarCliente(Cliente cliente) {
        clientesAtendidos.add(cliente);
    }

    // Método para exibir clientes atendidos
    public void exibirClientesAtendidos() {
        System.out.println("Profissional: " + nome);
        System.out.println("Clientes atendidos:");
        for (Cliente cliente : clientesAtendidos) {
            cliente.exibirInformacoes();
            System.out.println("----------------------");
        }
    }
}
public class Main {
    public static void main(String[] args) {
        // Criando alguns clientes
        Cliente cliente1 = new Cliente("João Silva", "123.456.789-00");
        Cliente cliente2 = new Cliente("Maria Oliveira", "987.654.321-00");

        // Criando um profissional
        Profissional profissional = new Profissional("Dr. Pedro");

        // Adicionando clientes ao profissional
        profissional.adicionarCliente(cliente1);
        profissional.adicionarCliente(cliente2);

        // Exibindo informações
        profissional.exibirClientesAtendidos();
    }
}
