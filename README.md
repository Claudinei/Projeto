package br.faccamp.domain;

import br.faccamp.view.CalculadoraGUI;

public class Calculadora  {
	
	private CalculadoraGUI gui;
	private Display display;
	private Operacao operacao;

	public Calculadora() {
		gui = new CalculadoraGUI(this);
		display = new Display(gui);
	}

	public void processaMC() {
		// TODO Auto-generated method stub
		
	}

	public void processaMR() {
		// TODO Auto-generated method stub
		
	}

	public void processaMS() {
		// TODO Auto-generated method stub
		
	}

	public void processaMMais() {
		// TODO Auto-generated method stub
		
	}

	public void processaMMenos() {
		// TODO Auto-generated method stub
	}

	public void processaCE() {
		display.limpa();
		
	}

	public void processaC() {
		display.limpa();
		display.atualiza("0");
			
	}

	public void processaRaiz() {
		display.getConteudo();
		
		double op2 = new Double(display.getConteudo());
		display.SetConteudo(String.valueOf(  Math.sqrt(op2)));
		
	}

	public void processaMaisOuMenos() {
		
		double op2 = new Double(display.getConteudo());
		display.SetConteudo(String.valueOf( - op2));
		
	}

	public void processaFatorial() {
		double operador = new Double(display.getConteudo());
		fatorial(operador);
		display.SetConteudo(String.valueOf(fatorial(operador)));
		        
	    }
	
	
	public void processaSete() {
		display.atualiza("7");
		
	}

	public void processaOito() {
		display.atualiza("8");
		
	}

	public void processaNove() {
		display.atualiza("9");
		
	}

	public void processaDivisao() {
		operacao = new OperacaoDeDivisao(display.getConteudo());
		display.limpa();
		
	}

	public void processaPorcentual() {
	display.getConteudo();
	double op1 = new Double(operacao.getPrimeiroOperador());
	double op2 = new Double(display.getConteudo());
	display.SetConteudo(String.valueOf( (op1*op2)/100));
	
	}

	public void processaQuatro() {
		display.atualiza("4");
		
	}

	public void processaCinco() {
			display.atualiza("5");	
	}

	public void processaSeis() {
			display.atualiza("6");	
	}

	public void processaVezes() {
		operacao = new OperacaoDeMutiplicacao(display.getConteudo());
		display.limpa();
		
	}

	public void processaUmSobreX() {
		display.getConteudo();
		double op1 = 1;
		double op2 = new Double(display.getConteudo());
		display.SetConteudo(String.valueOf( op1 / op2));
	}

	public void processaUm() {
		display.atualiza("1");
		
	}

	public void processaDois() {
		display.atualiza("2");
		
	}

	public void processaTres() {
		display.atualiza("3");
		
	}

	public void processaMenos() {
		operacao = new OperacaoDeSubtracao(display.getConteudo());
		display.limpa();
	}

	public void processaXElevadoY() {
		operacao = new OperacaoXElevadoY (display.getConteudo());
		display.limpa();
				
	}

	public void processaZero() {
		display.atualiza("0");
	}

	public void processaVirgula() {
		
		display.atualiza(".");
		
	}

	public void processaIgual() {
		String conteudo = display.getConteudo();
		display.limpa();
		display.atualiza(operacao.calcula(conteudo));
	}

	public void processaLog() {
		
		double op2 = new Double(display.getConteudo());
		display.SetConteudo(String.valueOf(  Math.log10(op2)));
		
	}

	public void processaMais() {
		operacao = new OperacaoDeSoma(display.getConteudo());
		display.limpa();
	}


        public double fatorial(double op1){
	       if (op1 == 0) {
           return 1;
          }	 
         return op1 * fatorial(op1 - 1);
        }
     }