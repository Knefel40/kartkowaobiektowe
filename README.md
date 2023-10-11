import java.util.ArrayList;
import java.util.List;

// Klasa Osoba
class Osoba {
    private String imie;
    private String nazwisko;
    private String dataUr;

    public Osoba(String imie, String nazwisko, String dataUr) {
        this.imie = imie;
        this.nazwisko = nazwisko;
        this.dataUr = dataUr;
    }

    // Metody set i get
    public void setImie(String imie) {
        this.imie = imie;
    }

    public String getImie() {
        return imie;
    }

    public void setNazwisko(String nazwisko) {
        this.nazwisko = nazwisko;
    }

    public String getNazwisko() {
        return nazwisko;
    }

    public void setDataUr(String dataUr) {
        this.dataUr = dataUr;
    }

    public String getDataUr() {
        return dataUr;
    }

    // Metoda toString
    public String toString() {
        return "Imię: " + imie + ", Nazwisko: " + nazwisko + ", Data urodzenia: " + dataUr;
    }
}

// Klasa Czytelnik dziedzicząca po klasie Osoba
class Czytelnik extends Osoba {
    private int nrCzytelnika;
    private List<String> wypozyczoneKsiazki;

    public Czytelnik(String imie, String nazwisko, String dataUr, int nrCzytelnika) {
        super(imie, nazwisko, dataUr);
        this.nrCzytelnika = nrCzytelnika;
        this.wypozyczoneKsiazki = new ArrayList<>();
    }

    // Metody set i get
    public void setNrCzytelnika(int nrCzytelnika) {
        this.nrCzytelnika = nrCzytelnika;
    }

    public int getNrCzytelnika() {
        return nrCzytelnika;
    }

    // Metoda wypożyczenia książki
    public void wypozyczKsiazke(String tytul) {
        wypozyczoneKsiazki.add(tytul);
    }

    // Metoda sprawdzania dostępności książki
    public boolean sprawdzCzyKsiazkaJestDostepna(String tytul) {
        return !wypozyczoneKsiazki.contains(tytul);
    }

    // Metoda sprawdzania liczby wypożyczonych książek
    public int ileKsiazekWypozyczylCzytelnik() {
        return wypozyczoneKsiazki.size();
    }

    // Metoda toString
    public String toString() {
        return super.toString() + ", Numer czytelnika: " + nrCzytelnika;
    }
}

// Klasa Bibliotekarz dziedzicząca po klasie Osoba
class Bibliotekarz extends Osoba {
    private String dataZatrudnienia;

    public Bibliotekarz(String imie, String nazwisko, String dataUr, String dataZatrudnienia) {
        super(imie, nazwisko, dataUr);
        this.dataZatrudnienia = dataZatrudnienia;
    }

    // Metody set i get
    public void setDataZatrudnienia(String dataZatrudnienia) {
        this.dataZatrudnienia = dataZatrudnienia;
    }

    public String getDataZatrudnienia() {
        return dataZatrudnienia;
    }

    // Metoda toString
    public String toString() {
        return super.toString() + ", Data zatrudnienia: " + dataZatrudnienia;
    }
}

// Klasa Ksiazka
class Ksiazka {
    private String tytul;
    private String autor;
    private boolean czyWypozyczona;

    public Ksiazka(String tytul, String autor) {
        this.tytul = tytul;
        this.autor = autor;
        this.czyWypozyczona = false;
    }

    // Metody set i get
    public void setTytul(String tytul) {
        this.tytul = tytul;
    }

    public String getTytul() {
        return tytul;
    }

    public void setAutor(String autor) {
        this.autor = autor;
    }

    public String getAutor() {
        return autor;
    }

    public boolean getCzyWypozyczona() {
        return czyWypozyczona;
    }

    // Metoda wypożyczenia książki
    public void wypozyczKsiazke() {
        czyWypozyczona = true;
    }

    // Metoda oddania książki
    public void oddajKsiazke() {
        czyWypozyczona = false;
    }

    // Metoda toString
    public String toString() {
        return "Tytuł: " + tytul + ", Autor: " + autor + ", Dostępność: " + (czyWypozyczona ? "Niedostępna" : "Dostępna");
    }
}

public class BibliotekaDemo {
    public static void main(String[] args) {
        // Przykładowe użycie klas
        Czytelnik czytelnik = new Czytelnik("Jan", "Kowalski", "01-01-1990", 12345);
        Bibliotekarz bibliotekarz = new Bibliotekarz("Anna", "Nowak", "15-05-1985", "01-06-2010");
        Ksiazka ksiazka1 = new Ksiazka("Wojna i Pokój", "Lew Tolstoj");
        Ksiazka ksiazka2 = new Ksiazka("Zbrodnia i Kara", "Fiodor Dostojewski");

        System.out.println("Informacje o czytelniku:\n" + czytelnik.toString() + "\n");
        System.out.println("Informacje o bibliotekarzu:\n" + bibliotekarz.toString() + "\n");
        System.out.println("Informacje o książce 1:\n" + ksiazka1.toString() + "\n");
        System.out.println("Informacje o książce 2:\n" + ksiazka2.toString() + "\n");

        // Wypożyczenie książki przez czytelnika
        czytelnik.wypozyczKsiazke(ksiazka1.getTytul());

        // Sprawdzenie dostępności książ
















public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
       /* Osoba osoba1 = new Osoba();
        osoba1.setImie("Jaś");
        osoba1.setWiek(12);
        System.out.println(osoba1.getImie());
        System.out.println(osoba1.getWiek());
        Osoba osoba2 = new Osoba("Asia",16);
        System.out.println(osoba2);  */
        Uczen uczen = new Uczen("Tomek",7,234);
        Uczen uczen1 = new Uczen("Alan",8);
        Uczen uczen2 = new Uczen("Ala",6);
        System.out.println(uczen1);
        System.out.println(uczen2);
        System.out.println(uczen);
        Nauczyciel nauczycielS = new Nauczyciel("Sebastian",35,"testowanie","bazy danych","wf","fizyka");
        Nauczyciel nauczycielW = new Nauczyciel("Witosław",50,"matematyka");
        System.out.println(nauczycielS);
        System.out.println(nauczycielW);
        Klasa klasa3p = new Klasa("3P");
        Wychowawca nauczycielP = new Wychowawca("Apolonia",70,klasa3p, "technika","muzyka");
        klasa3p.dodajuczniadoklasy(uczen);
        klasa3p.dodajuczniadoklasy(uczen1);
        klasa3p.dodajuczniadoklasy(uczen2);
        System.out.println(nauczycielP);
        System.out.println(klasa3p);

    }
}





import java.util.ArrayList;

/**
 * Klasa - klasa opisujaca zespol uczniow
 */
public class Klasa {
    private String nazwa;
    private ArrayList<Uczen> uczniowie;

    public Klasa(String nazwa) {
        this.nazwa = nazwa;
        uczniowie = new ArrayList<>();
    }

    public void dodajuczniadoklasy(Uczen uczen){
        if(uczniowie.contains((uczen))){
            System.out.println("Ten uczeń jest już w klasie");
        }
        else{
            uczniowie.add(uczen);
        }
    }
    @Override
    public String toString() {
        return "Klasa{" +
                "nazwa='" + nazwa + '\'' +
                ", uczniowie=" + uczniowie +
                '}';
    }
}





import java.util.ArrayList;

public sealed class Nauczyciel extends Osoba implements Dyzurny permits Wychowawca{
    private ArrayList<String> przedmioty = new ArrayList<>();

    public Nauczyciel(String imie, int wiek,String przedmiot) {
        super(imie, wiek);
        przedmioty.add(przedmiot);
    }

    public Nauczyciel(String imie, int wiek, String ...przedmioty) {
        super(imie, wiek);
        for (String przed:
             przedmioty) {
            this.przedmioty.add(przed);
        }
    }

    @Override
    public String toString() {
        return "Nauczyciel{" +
                "przedmioty=" + przedmioty +
                "} " + super.toString();
    }

    @Override
    public void dyzuruj() {
        System.out.println("Spacer po korytarzu");
    }
}





public abstract class Osoba {
    //klasa abstract nie pozwala na tworzenie jej obiektow
    //mozna tylko wykorzystac ja do dziedziczenia
    private String imie;
    private int wiek;

    public Osoba(String imie, int wiek) {
        this.imie = imie;
        this.wiek = wiek;
    }

    public Osoba() {
        imie = "Edek";
        wiek = 80;
    }

    public String getImie() {
        return imie;
    }

    public void setImie(String imie) {
        this.imie = imie;
    }

    public int getWiek() {
        return wiek;
    }

    public void setWiek(int wiek) {
        if(wiek<0){
            this.wiek = 0;
        }
        else{
            this.wiek = wiek;
        }
        this.wiek = wiek;
    }

    @Override
    public String toString() {
        return "Osoba{" +
                "imie='" + imie + '\'' +
                ", wiek=" + wiek +
                '}';
    }
}




public class Uczen extends Osoba implements Dyzurny{
    private int nrEwidencyjny;
    private static int liczbaUczniow = 0;

    public Uczen(String imie, int wiek, int nrEwidencyjny) {
        super(imie, wiek);
        this.nrEwidencyjny = nrEwidencyjny;
    }

    public Uczen(String imie, int wiek) {
        super(imie, wiek);
        liczbaUczniow++;
        nrEwidencyjny = liczbaUczniow;

    }

    @Override
    public String toString() {
        return "Uczen{" +
                "nrEwidencyjny=" + nrEwidencyjny +
                "} " + super.toString();
    }

    @Override
    public void dyzuruj() {
        System.out.println("Wycieranie tablicy");
    }
}



public final class Wychowawca extends Nauczyciel{
        private Klasa klasa;

    public Wychowawca(String imie, int wiek, Klasa klasa, String... przedmioty) {
        super(imie, wiek, przedmioty);
        this.klasa = klasa;
    }

    @Override
    public String toString() {
        return "Wychowawca{" +
                "klasa=" + klasa +
                "} " + super.toString();
    }
}




public interface Dyzurny {
    public abstract void dyzuruj();
}













import java.util.ArrayList;
import java.util.Date;

public class Czytelnik extends Osoba{
    private int nrCzytelnika;
    private static int liczbaCzytelnik;
    private ArrayList<Ksiazka> wypozyczoneKsiazki;

    public Czytelnik(String imie, String nazwisko, Date dataUr) {
        super(imie, nazwisko, dataUr);
        liczbaCzytelnik++;
        this.nrCzytelnika = liczbaCzytelnik;
        this.wypozyczoneKsiazki = new ArrayList<>();
    }

    public int getNrCzytelnika() {
        return nrCzytelnika;
    }

    public void setNrCzytelnika(int nrCzytelnika) {
        this.nrCzytelnika = nrCzytelnika;
    }

    public static int getLiczbaCzytelnik() {
        return liczbaCzytelnik;
    }

    public static void setLiczbaCzytelnik(int liczbaCzytelnik) {
        Czytelnik.liczbaCzytelnik = liczbaCzytelnik;
    }

    public ArrayList<Ksiazka> getWypozyczoneKsiazki() {
        return wypozyczoneKsiazki;
    }

    public void setWypozyczoneKsiazki(ArrayList<Ksiazka> wypozyczoneKsiazki) {
        this.wypozyczoneKsiazki = wypozyczoneKsiazki;
    }

    @Override
    public String toString() {
        return "Czytelnik{" +
                "nrCzytelnika=" + nrCzytelnika +
                ", wypozyczoneKsiazki=" + wypozyczoneKsiazki +
                "} " + super.toString();
    }
}





public class Ksiazka {
    private String Tytul;
    private Osoba autor;
    private boolean czyWypozyczona;

    public Ksiazka(String tytul, Osoba autor) {
        Tytul = tytul;
        this.autor = autor;
        czyWypozyczona = false;
    }

    public String getTytul() {
        return Tytul;
    }

    public void setTytul(String tytul) {
        Tytul = tytul;
    }

    public Osoba getAutor() {
        return autor;
    }

    public void setAutor(Osoba autor) {
        this.autor = autor;
    }

    public boolean isCzyWypozyczona() {
        return czyWypozyczona;
    }

    public void setCzyWypozyczona(boolean czyWypozyczona) {
        this.czyWypozyczona = czyWypozyczona;
    }
}





    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}







import java.util.Date;

public class Osoba {
    private String imie;
    private Date dataUr;
    private String nazwisko;

    public Osoba(String imie, String nazwisko, Date dataUr) {
        this.imie = imie;
        this.dataUr = dataUr;
        this.nazwisko = nazwisko;
    }

    public String getImie() {
        return imie;
    }

    public void setImie(String imie) {
        this.imie = imie;
    }

    public Date getDataUr() {
        return dataUr;
    }

    public void setDataUr(Date dataUr) {
        this.dataUr = dataUr;
    }

    public String getNazwisko() {
        return nazwisko;
    }

    public void setNazwisko(String nazwisko) {
        this.nazwisko = nazwisko;
    }

    @Override
    public String toString() {
        return "Osoba{" +
                "imie='" + imie + '\'' +
                ", nazwisko='" + nazwisko + '\'' +
                '}';
    }
}















LEKCJA PANI KUPKI


BIBLIOTEKARZ

import java.util.ArrayList;

public class Biblioteka {
    public ArrayList<Czytelnik> czytelnicy;
    public ArrayList<Ksiazka> ksiazki;
    public ArrayList<Bibliotekarz> bibliotekarze;

    public Biblioteka() {
        czytelnicy = new ArrayList<>();
        ksiazki= new ArrayList<>();
        bibliotekarze= new ArrayList<>();
    }
    public void wyporzyczKsiazke(Ksiazka ksiazka, Czytelnik czytelnik){
        if(ksiazka.isCzyWypozyczona()){
            System.out.println("nie można wyporzyczyć ksiazki");
        }
        else{
            czytelnik.dodajKsiazke(ksiazka);
            ksiazka.setCzyWypozyczona(true);
            //nie mogę zmienić parametru ksiazki

        }
    }
    public int ileKsiazekWyporzyczyl(Czytelnik czytelnik){
        return czytelnik.ileKsiazekWypozyczyl();
    }

}

BIBLIOTEKARZ

import java.util.Date;

public class Bibliotekarz extends Osoba{
    private Date dataZatrudnienia;

    public Bibliotekarz(String imie, String nazwisko, Date dataUrodzenia) {
        super(imie, nazwisko, dataUrodzenia);
        dataZatrudnienia = new Date();
    }
}


CZYTELNIK


import java.util.ArrayList;
import java.util.Date;

public class Czytelnik extends Osoba{
    private int nrCzytelnika;
    private static int liczbaCzytelnikow;
    private ArrayList<Ksiazka> wypozyczoneKsiazki = new ArrayList<>();

    public Czytelnik(String imie, String nazwisko, Date dataUrodzenia) {
        super(imie, nazwisko, dataUrodzenia);
        liczbaCzytelnikow++;
        this.nrCzytelnika = liczbaCzytelnikow;
    }

    public int getNrCzytelnika() {
        return nrCzytelnika;
    }

    public void setNrCzytelnika(int nrCzytelnika) {
        this.nrCzytelnika = nrCzytelnika;
    }

    public static int getLiczbaCzytelnikow() {
        return liczbaCzytelnikow;
    }

    public static void setLiczbaCzytelnikow(int liczbaCzytelnikow) {
        Czytelnik.liczbaCzytelnikow = liczbaCzytelnikow;
    }

    public ArrayList<Ksiazka> getWypozyczoneKsiazki() {
        return wypozyczoneKsiazki;
    }

    public void setWypozyczoneKsiazki(ArrayList<Ksiazka> wypozyczoneKsiazki) {
        this.wypozyczoneKsiazki = wypozyczoneKsiazki;
    }
    public void dodajKsiazke(Ksiazka ksiazka){
        wypozyczoneKsiazki.add(ksiazka);
    }
    public int ileKsiazekWypozyczyl(){
        return wypozyczoneKsiazki.size();
    }
}


KSIAZKA

import java.util.Date;

public class Ksiazka {
    private String tytul;
    private Osoba autor;
    private boolean czyWypozyczona;

    public Ksiazka(String tytul, String imie, String nazwisko, Date dataUr) {
        this.tytul = tytul;
        this.czyWypozyczona = false;
        autor = new Osoba(imie,nazwisko,dataUr);
    }

    public String getTytul() {
        return tytul;
    }

    public void setTytul(String tytul) {
        this.tytul = tytul;
    }

    public Osoba getAutor() {
        return autor;
    }

    public void setAutor(Osoba autor) {
        this.autor = autor;
    }

    public boolean isCzyWypozyczona() {
        return czyWypozyczona;
    }

    public void setCzyWypozyczona(boolean czyWypozyczona) {
        this.czyWypozyczona = czyWypozyczona;
    }
}


MAIN

public class Main {
    public static void main(String[] args) {
        System.out.println("Hello world!");
    }
}


OSOBA

import java.util.Date;

 public class Osoba {
    private String imie;
    private String nazwisko;

    private Date dataUrodzenia;

    public Osoba(String imie, String nazwisko,int rok,int m,int d) {
        this.imie = imie;
        this.nazwisko = nazwisko;
        dataUrodzenia = new Date(rok,m,d);
    }

     public Osoba(String imie, String nazwisko, Date dataUrodzenia) {
         this.imie = imie;
         this.nazwisko = nazwisko;
         this.dataUrodzenia = dataUrodzenia;
     }

     public String getImie() {
        return imie;
    }

    public void setImie(String imie) {
        this.imie = imie;
    }

    public String getNazwisko() {
        return nazwisko;
    }

    public void setNazwisko(String nazwisko) {
        this.nazwisko = nazwisko;
    }

    public Date getDataUrodzenia() {
        return dataUrodzenia;
    }

    public void setDataUrodzenia(Date dataUrodzenia) {
        this.dataUrodzenia = dataUrodzenia;
    }
}
