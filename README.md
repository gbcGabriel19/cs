# cs
 simplifica sua busca, oferecendo informações detalhadas e opções de personalização. Seja você um entusiasta de motores potentes ou um apaixonado por duas rodas.
package negocio;



public class veiculos {

	//Propiedades da classe
	
			private String modelo = "";
			private Fabricante objFabricante = null;
			private String cor = "";
			public veiculos() {
				super();
			}
			
			 //Metodos construtores da Classe
			
			public veiculos(String modelo, Fabricante objFabricante, String cor) {
				super();
				this.modelo = modelo;
				this.objFabricante = objFabricante;
				this.cor = cor;
			}
			
			//Metodos get/set da Classe
			
			public String getModelo() {
				return modelo;
			}
			public void setModelo(String modelo) {
				this.modelo = modelo;
			}
			public Fabricante getObjFabricante() {
				return objFabricante;
			}
			public void setObjFabricante(Fabricante objFabricante) {
				this.objFabricante = objFabricante;
			}
			public String getCor() {
				return cor;
			}
			public void setCor(String cor) {
				this.cor = cor;
			}	
}


package negocio;

public class Fabricante {
	//Propiedades da classe
	
			private String nome = "";

			public Fabricante() {
				super();
				
				 //Metodos construtores da Classe
				
			}

			public Fabricante(String nome) {
				super();
				this.nome = nome;
			}
			//Metodos get/set da Classe
			
			public String getNome() {
				return nome;
			}

			public void setNome(String nome) {
				this.nome = nome;
			}
			

}



 package negocio;

public class Moto extends veiculos {
	//Propiedades da Classe
	
			private int cilindrada = 0;

			public Moto() {
				super();
			}
			//Metodos construtores da Classe
			public Moto(String modelo, Fabricante objFabricante, String cor, int cilindrada) {
				super(modelo, objFabricante, cor);
				this.cilindrada = cilindrada;
			}
			//Metodos get/set da Classe
			
			public int getCilindrada() {
				return cilindrada;
			}

			public void setCilindrada(int cilindrada) {
				this.cilindrada = cilindrada;
			}		
	}


package negocio;

	

	public class Carro extends veiculos{
		
		//Propiedades da Classe
		
		private boolean tetoSolar = false;

		public Carro() {
			super();
		}
		//Metodos construtores da Classe
		public Carro(String modelo, Fabricante objFabricante, String cor, boolean tetoSolar) {
			super(modelo, objFabricante, cor);
			this.tetoSolar = tetoSolar;
		}

		//Metodos get/set da Classe
		public boolean isTetoSolar() {
			return tetoSolar;
		}

		public void setTetoSolar(boolean tetoSolar) {
			this.tetoSolar = tetoSolar;
		}
		
	}



package apresentacao;

	
	import java.io.BufferedReader;
	import java.io.InputStreamReader;

	import negocio.Carro;
	import negocio.Fabricante;
	import negocio.Moto;
	import negocio.veiculos;

	public class PrincipalConcessionaria {

		public static void main (String[] args) {
		
			//Declaracao de Variaveis
		
			BufferedReader leitor = new BufferedReader(
					                new InputStreamReader(System.in));
			
			veiculos objVeiculo = null;
			int opcao = 0;
			
			
			//Entrada de dados
		
		try {
			System.out.print("Digite <1> para carro ou " + " <2> para moto: ");
			opcao = Integer.parseInt(leitor.readLine());
			
		if (opcao == 1) {
			objVeiculo = new Carro();
		} else {
			objVeiculo = new Moto();
		}
		
		System.out.print("Digite o modelo: ");
		objVeiculo.setModelo(leitor.readLine());
		
		System.out.print("Digite o Fabricante: ");
		objVeiculo.setObjFabricante (new Fabricante(leitor.readLine()));
		
		System.out.print("Digite a Cor: ");
		objVeiculo.setCor(leitor.readLine());
		
		if (opcao == 1) {
			System.out.print("Digite <s> para teto Solar: ");
			((Carro) objVeiculo).setTetoSolar(leitor.readLine().equalsIgnoreCase("S"));
			
		} else {
			
			System.out.print("Digite a cilindrada: ");
			((Moto) objVeiculo).setCilindrada(Integer.parseInt(leitor.readLine()));
			
		}
		} catch (Exception erro) {System.out.println(erro);
		}
		
		//Saida de Dados
		
		System.out.println("Modelo: " + objVeiculo.getModelo());
		System.out.println("Fabricante: " + objVeiculo.getObjFabricante().getNome());
		System.out.println("Cor: " + objVeiculo.getCor());
		if (opcao ==1) {
			System.out.println("Teto Solar: " +
		(((Carro) objVeiculo).isTetoSolar() ? "SIM": "não"));
			
		}  else {
			System.out.println("Cilindrada: " + ((Moto) objVeiculo).getCilindrada());
		}
		
		}
		}
		




