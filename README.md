import java.time.LocalDateTime;
import java.time.format.DateTimeFormatter;

class Clientes {
    private String nome;
    private String cpf;
    private String telefone;

    public Clientes(String nome, String cpf, String telefone) {
        this.nome = nome;
        this.cpf = cpf;
        this.telefone = telefone;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getCpf() {
        return cpf;
    }

    public void setCpf(String cpf) {
        this.cpf = cpf;
    }

    public String getTelefone() {
        return telefone;
    }

    public void setTelefone(String telefone) {
        this.telefone = telefone;
    }

    public String toString() {
        return "Cliente [Nome: " + nome + ", CPF: " + cpf + 
                ", Telefone: " + telefone + "]";
    }
}

class Tecnico {
    private String nome;
    private String telefone;

    public Tecnico(String nome, String telefone) {
        this.nome = nome;
        this.telefone = telefone;
    }

    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getTelefone() {
        return telefone;
    }

    public void setTelefone(String telefone) {
        this.telefone = telefone;
    }

    public String toString() {
        return "Tecnico [Nome: " + nome + ", Telefone: " + telefone + "]";
    }
}

class Servico {
    private String tipoServico;

    public Servico(String tipoServico) {
        this.tipoServico = tipoServico;
    }

    public String getTipoServico() {
        return tipoServico;
    }

    public void setTipoServico(String tipoServico) {
        this.tipoServico = tipoServico;
    }

    public String toString() {
        return "Serviço [Tipo de Serviço: " + tipoServico + "]";
    }
}

class Agendamento {
    private Clientes cliente;
    private Tecnico tecnico;
    private Servico servico;
    private LocalDateTime dataHora;

    public Agendamento(Clientes cliente, Tecnico tecnico, Servico servico, LocalDateTime dataHora) {
        this.cliente = cliente;
        this.tecnico = tecnico;
        this.servico = servico;
        this.dataHora = dataHora;
    }

    public Clientes getCliente() {
        return cliente;
    }

    public void setCliente(Clientes cliente) {
        this.cliente = cliente;
    }

    public Tecnico getTecnico() {
        return tecnico;
    }

    public void setTecnico(Tecnico tecnico) {
        this.tecnico = tecnico;
    }

    public Servico getServico() {
        return servico;
    }

    public void setServico(Servico servico) {
        this.servico = servico;
    }

    public LocalDateTime getDataHora() {
        return dataHora;
    }

    public void setDataHora(LocalDateTime dataHora) {
        this.dataHora = dataHora;
    }

    public String toString() {
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("dd/MM/yyyy HH:mm");
        return "Agendamento:\n" +
                "  Cliente: " + cliente.getNome() + "\n" +
                "  Técnico: " + tecnico.getNome() + "\n" +
                "  Serviço: " + servico.getTipoServico() + "\n" +
                "  Data e Hora: " + dataHora.format(formatter);
    }
}

public class Main {
    public static void main(String[] args) {
        Clientes cliente = new Clientes("Maria", "123.456.789-00", "(21) 91234-5678");
        Tecnico tecnico = new Tecnico("Rosa", "(21) 99302-3596");
        Servico servico = new Servico("Depilação");

        // Criação do agendamento
        LocalDateTime dataHora = LocalDateTime.of(2024, 11, 30, 14, 30);
        Agendamento agendamento = new Agendamento(cliente, tecnico, servico, dataHora);

        // Impressão dos detalhes
        System.out.println(cliente);
        System.out.println(tecnico);
        System.out.println(servico);
        System.out.println(agendamento);
    }
}
