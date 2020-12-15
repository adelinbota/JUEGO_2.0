# JUEGO_2.0
package elJuego;

import java.util.Scanner;

public class Recreativo {

	public static int pintaMenu() {
		 
		//Guardar un nuevo juego
		//Poner puntuación a un juego
		//Ver todos los juegos
		
		Scanner leer = new Scanner(System.in);
		int menu;
		System.out.println("Si quiere una cosa, pulse 1");
		System.out.println("Si quiere otra cosa, pulse 2");
		System.out.println("Si ni la 1 ni la 2, pulse 3");
		System.out.println("Si las tres primeras no te van, pulse 4");
		System.out.println("Pulse 0 para salir, y acaba con esto");
		menu = leer.nextInt();
		return menu;
	}
	
	public static void verTodosJuegos(Juego vJuegos[]) {
		
	}
	
	public static void guardarJuego(Juego vJuegos[]) {
		//Pedir los datos del juego
		
		
		//Buscar posición libre en el vector
		for (int i = 0; i < vJuegos.length; i++) {
			if (vJuegos[i] == null) {
				vJuegos[i] = new Juego("Adelin");
				break;
			}
		}
			
	}
	
	public static void ponerPuntuacionJuego(Recreativo vJuegos[]) {
		
	}
	
	
	public static void main(String[] args) {
		
		
		Juego vJuegos[] = new Juego[100];
		
		Juego juego1 = new Juego("CiberPunk");
		Juego juego2 = new Juego("Los Sims");
		Juego juego3 = new Juego("Fifa");
		
		vJuegos[0] = juego1;
		vJuegos[1] = juego2;
		vJuegos[2] = juego3;
		vJuegos[3] = new Juego("Rumble Stars");
		
		vJuegos[2].setMultijugador(true);
		vJuegos[2].ponerRecord(100);
		
		for (int i = 0; i < vJuegos.length; i++) {
			if (vJuegos[i] != null && vJuegos[i].isMultijugador()) {
				System.out.println(vJuegos[i].toString());
			}
			
		}
		

	}



}
//-----------------------------------------------------------------------------------
//-----------------------------------------------------------------------------------
package elJuego;

public class Juego {
	//Atributos de la clase
		private String nombre;
		private int record;
		private boolean multijugador;
		
		//Métodos de la clase ------
		
		public Juego(String nombre) {
			this.nombre = nombre;
			this.record = 0;
			multijugador = false;
			
		}
		
		public Juego(String nombre, int record, boolean multijugador) {
			super();
			this.nombre = nombre;
			this.record = record;
			this.multijugador = multijugador;
		}

		public void ponerRecord(int puntuacion) {
			record = puntuacion;
		}
		
		public void setRecord(int record) {
			this.record = record;
		}

		public String getNombre() {
			return nombre;
		}


		public int getRecord() {
			return record;
		}

		

		public boolean isMultijugador() {
			return multijugador;
		}

		public void setMultijugador(boolean multijugador) {
			this.multijugador = multijugador;
		}

		@Override
		public String toString() {
			return  nombre + " --- " + record;
		}
}

