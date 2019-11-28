package trabJav;

import java.awt.BorderLayout;
import java.awt.Button;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import java.awt.event.MouseListener;
import java.util.ArrayList;
import java.util.List;

import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JList;
import javax.swing.JPanel;
import javax.swing.JScrollPane;
import javax.swing.JTextField;

public class Cadastro extends Tela implements ActionListener {
	private JFrame telaCadastro = new JFrame();
	private Button btVoltar = new Button("Voltar");
	private Button btConsultaTitulos = new Button("Consulta Titulos");
	private Button btConsultaLivros = new Button("Consulta Livros");
	
	//private JLabel txtMenu = new JLabel("Menu");
	//private JTextField campoNomeAutor = new JTextField();
	
	public void montarTela() {
		this.montaFrame();
		this.montaConteudo();
	}

	public void montaFrame() {
		this.telaCadastro.setSize(800,450);
		this.telaCadastro.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

		this.painel.setLayout(null);
		this.telaCadastro.add(this.painel);

		this.telaCadastro.setVisible(true);
	}

	public void montaConteudo() {
		this.painel.add(this.btVoltar);
		this.btVoltar.setBounds(45, 20, 50, 30);
		this.btVoltar.addActionListener(this);
		
		this.painel.add(this.btConsultaTitulos);
		this.btConsultaTitulos.setBounds(45, 80, 100, 30);
		this.btConsultaTitulos.addActionListener(this);
		
		this.painel.add(this.btConsultaLivros);
		this.btConsultaLivros.setBounds(45, 120, 100, 30);
		this.btConsultaLivros.addActionListener(this);
		
	}
	
	@Override
	public void actionPerformed(ActionEvent e) {
		if(e.getSource() == this.btVoltar) {
			this.setProximaTela("menu");
		} else if(e.getSource() == this.btConsultaTitulos) {
			new consultaTitulos();
		} else if(e.getSource() == this.btConsultaLivros) {
			new consultaLivros();
		}
	}
	
	public class consultaTitulos {
		consultaTitulos() {
			//poderia ser Dvd também, mas tem o mesmo retorno
			Livro livro = new Livro();
			livro.pegarTituloTamanho();
			
			
			JPanel panel = new JPanel(new BorderLayout());
		    List<String> myList = new ArrayList<>();
		    for (int index = 0; index < livro.nomeIndice.size(); index++) {
		       myList.add(index +" nome: " +  livro.nomeIndice.get(index));
		    }
		    JList<String> list = new JList<String>(myList.toArray(new String[myList.size()]));
		    JScrollPane scrollPane = new JScrollPane();
		    scrollPane.setViewportView(list);
		      
		    list.setLayoutOrientation(JList.VERTICAL);
		    panel.add(scrollPane);
		    JFrame frame = new JFrame("Demo");
		    frame.add(panel);
		    frame.setSize(500, 250);
		    frame.setLocationRelativeTo(null);
		    frame.setVisible(true);
		}
	}

	public class consultaLivros {
		consultaLivros() {
			//poderia ser Dvd também, mas tem o mesmo retorno
			Livro livro = new Livro();
			livro.pegarTituloTamanho();
			
			livro.lerArq();
			
			JPanel panel = new JPanel(new BorderLayout());
		    List<String> myList = new ArrayList<>();
		    for (int index = 0; index < livro.Livros.size(); index++) {
		    	String texto = livro.Livros.get(index);
		    	String parteTexto = " ";
		    	
		    	if(texto.length() > 150) {
		    		int cont = 0;
		    		for(int a=0; a < texto.length(); a+=100) {
		    			if(a > texto.length()) {
		    				break;
		    			} else {
		    				for(int b=a;b<=a+99;b++) {
		    					if(b >= texto.length()) {
				    				break;
				    			}
		    					parteTexto += texto.charAt(b);
		    				}
		    				myList.add(parteTexto);
		    			}
		    			parteTexto = " ";
		    		}
		    	} else {
		    		myList.add(texto);
		    	}
		    	//myList.add( livro.Livros.get(index) );
		    }
		    JList<String> list = new JList<String>(myList.toArray(new String[myList.size()]));
		    JScrollPane scrollPane = new JScrollPane();
		    scrollPane.setViewportView(list);
	
		    list.setLayoutOrientation(JList.VERTICAL);
		    panel.add(scrollPane);
		    JFrame frame = new JFrame("Demo");
		    frame.add(panel);
		    frame.setSize(800, 500);
		    frame.setLocationRelativeTo(null);
		    frame.setVisible(true);
		}
	}
	
	public void setTelaCadastro(Boolean TrueFalse) {
		if(TrueFalse == true) {
			this.telaCadastro.setVisible(true);
		} else {
			this.telaCadastro.setVisible(false);
		}
	}
}
