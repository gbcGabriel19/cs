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

