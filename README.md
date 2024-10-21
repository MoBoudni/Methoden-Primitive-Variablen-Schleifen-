package grundlagen;

/**
 * Verwendung von primitiven Datentypen in Java. Sie unterscheiden sich in der Speichergröße
 * Mit diesen Werten kann gerechnet werden
 */

public class Einfach {

	public static void main(String[] args) {
		System.out.println("-- Einstieg ins Programm --\n");
		
		System.out.println("-- ganzzahlige Datentypen --\n");
		// 1 - der kleinste der Variablen, zwischen -128 bis 127 (die Null zählt als positive Zahl 
		byte kleinsteGanzzahl = 4;
		kleinsteGanzzahl = 127;
		kleinsteGanzzahl = -128;
		
		// 2 -der short ist eine kleine Ganzzahl zwischen -32768 bis 32767
		// Unterstrich dient der besseren Lesbarkeit
		short kleineGanzzahl = 128;
		kleineGanzzahl = 1000;
		kleineGanzzahl = 32_767;
		kleineGanzzahl = -32_768;
		
		// 3 - INT: normale Ganzzahl zwischen -2_147_483_648 und 2_147_483_647
		// Integer wird Java-intern genutzt, um mit Zahlen zu rechnen. bytes werden also nach Integer verwandelt
		// normalerweise wird Integer verwendet, byte und short sehr selten
		
		int normaleGanzzahl = 342;
		normaleGanzzahl = -2_147_483_648;
		normaleGanzzahl = 2_147_483_647;
		
		// Anzeige der Min- und Max-Werte, geht natürlich auch mit short und byte
		
		System.out.println(Integer.MAX_VALUE);
		System.out.println(Integer.MIN_VALUE);
		System.out.println(Byte.MIN_VALUE);
		System.out.println(Short.MAX_VALUE);
		
		// 4 - long, noch größer als Interger zwischen -9223372036854775808 und 9223372036854775807
		// Ziffern sind in Java aber immer Integer, deswegen muss man die mit "L" oder "l" kennzeichen. Das große L unterscheidet sich aber besser vom großen "i"
		
		System.out.println(Long.MAX_VALUE);
		System.out.println(Long.MIN_VALUE);
		
		long grosseGanzzahl = 9223372036854775807L;
		grosseGanzzahl = -9223372036854775808L;
		grosseGanzzahl = -9223372036854775808L;
		
		// Wenn man Max INT +1 addiert, springt die Zahl wieder zurück auf den Minimal Wert.
		// der Compiler warnt hier als nicht und führt zu falschen Werten
		// statt 2147483647+1 kommt -2147483648 
		
		normaleGanzzahl = Integer.MAX_VALUE;
		normaleGanzzahl = normaleGanzzahl + 1;
		System.out.println(normaleGanzzahl);
		
		// 5 - Fließkommazahlen, also Kommazahlen
		// der Compiler erwartet aber eine Integerzahl und float muss daher wie "long" gekennzeichnet werden. 
		// das kleine "f" hat sich dem Großen gegenüber durchgesetzt;
		// float ist eine kleine Kommazahl, eher selten
		
		float kleineKommazahl = 3.14f;
		double normaleKommazahl = 3_123.1432434342343434f;
		
		System.out.println(Double.MIN_VALUE);
		System.out.println(Double.MAX_VALUE);
		
		// float ist wirklich sehr groß, noch größere Zahlen können mit Klassen abgebildet werden
		// Java ist aber nicht wirklich dafür geeignet und es gibt da andere Sprachen
		
		System.out.println("\n-- Mit den Zahlentypen kann gerechnet werden --");
		normaleGanzzahl = 500;
		normaleGanzzahl = normaleGanzzahl + 1 - 500/2 *3;
		
		// Das ergebnis ist immer eine Ganzzahl, Nachkommastellen werden einfach abgeschnitten
		// der Modulo-Operator gibt den Rest an
		// ! Der Modulo Operator ist bei hohen Zahlen rechenintensiv
		normaleGanzzahl = 17/4;
		int rest = 17 % 4;
		System.out.println("Rest von 17/4 =" + rest );
		
		// Nachkommazahlen werden nach Integer umgewandelt, wenn also beide Zahlen INT sind, so ist das Ergebnis auh eine Ganzahl.
		// Daher sollte eine Zahl ein Double sein
		System.out.println(normaleKommazahl = 17/4);
		System.out.println(normaleKommazahl = 17/4.0);
		
		// Konvertieren: der kleine Datentyp kann in den größeren hineingespeichert werden
		normaleKommazahl = normaleGanzzahl;
		grosseGanzzahl = 15;
		
		// Casting: der umgekehrte Vorgang geht nur mit dem Casting
		// in diesem Beispiel werden die Nahkommastellen aber abgeschnitten, Informationen gehen verloren;
		// geCastet wird z.B. wenn man Ergebnisse aus fremden Code bekommt. Man bekommt also einen Double zurück und selber braucht man aber ein INT
		int versuch = (int)3.144545;
		System.out.println(versuch);
		
		// 6 - 1 (Sonder) Zeichen: char
		char buchstabe = 'A';
		buchstabe = '\n';
		buchstabe = 'A';
		
		// Das Zeichen als Zahl darstellen
		int zahlA = buchstabe;
		System.out.println(zahlA);
		
		// Zahl umwandelnn in Buchstabe nur mit Casting, da Char "höher" als INT
		int zahlB = zahlA + 1;
		System.out.println("Buchstabe " + (char)zahlB + " Zahl " + zahlB);
		
		// 7 - boolean, gabe es in C++ nicht. IN Java also neu
		// Wahrheitsgehalt einer Aussage. Nur true oder false möglich. Casting nicht möglich
		
		boolean wahrheit = true ;
		System.out.println(wahrheit);
		
		normaleKommazahl = 999;
		wahrheit = normaleKommazahl > 1000;
		System.out.println(wahrheit);
		
		wahrheit = 10000 % 17 == 0;
		System.out.println(wahrheit);
		System.out.println(170 % 18 == 0);
		
		// && logische UND Verknüpfung
		// && untersucht den linken Teil und wenn der falsch ist wird der rechte Teil nicht mehr untersucht, da die Gesamtaussage nicht mehr richtig sein
		wahrheit = normaleGanzzahl > 10 && normaleGanzzahl < 20;
		
		// & das einfache UND untersucht beide Seiten
		wahrheit = normaleGanzzahl < 40 & normaleGanzzahl % 3 == 0;
				
		// || logische ODER Verknüpfung, nur falsch wenn beide Seiten falsch sind. Nur die erste Bedingung wird geprüft, somit können möglich Fehler der 2. Bedingung umgangen werden
		// | das einfache oder untersucht beide Seiten
		
		wahrheit = normaleGanzzahl > 10 || normaleGanzzahl % 3 == 0;
				
		System.out.println("\n-- Ende des Programms --");

	}

}
