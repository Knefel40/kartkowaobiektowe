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
