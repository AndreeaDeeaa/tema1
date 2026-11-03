# tema1

#include <iostream>
#include <string>
using namespace std;

class Persoana {
private:
    string nume;
    int varsta;

public:
    // Constructor implicit
    Persoana() {
        nume = "Necunoscut";
        varsta = 0;
        cout << "Constructor implicit Persoana\n";
    }

    // Constructor cu parametri
    Persoana(string n, int v) {
        nume = n;
        varsta = v;
        cout << "Constructor cu parametri Persoana\n";
    }

    // Destructor
    ~Persoana() {
        cout << "Destructor Persoana\n";
    }

    // Getteri
    string getNume() {
        return nume;
    }

    int getVarsta() {
        return varsta;
    }

    // Setteri
    void setNume(string n) {
        nume = n;
    }

    void setVarsta(int v) {
        varsta = v;
    }

    // Metoda de afisare
    void afisare() {
        cout << "Nume: " << nume << endl;
        cout << "Varsta: " << varsta << endl;
    }
};

// Clasa derivata (mostenire)
class Elev : public Persoana {
private:
    string clasa;
    double medie;

public:
    // Constructor implicit
    Elev() : Persoana() {
        clasa = "Necunoscuta";
        medie = 0;
        cout << "Constructor implicit Elev\n";
    }

    // Constructor cu parametri
    Elev(string n, int v, string c, double m)
        : Persoana(n, v) {
        clasa = c;
        medie = m;
        cout << "Constructor cu parametri Elev\n";
    }

    // Destructor
    ~Elev() {
        cout << "Destructor Elev\n";
    }

    // Getteri
    string getClasa() {
        return clasa;
    }

    double getMedie() {
        return medie;
    }

    // Setteri
    void setClasa(string c) {
        clasa = c;
    }

    void setMedie(double m) {
        medie = m;
    }

    // Afisare
    void afisareElev() {
        afisare();
        cout << "Clasa: " << clasa << endl;
        cout << "Media: " << medie << endl;
    }
};

int main() {
    // Crearea unui obiect
    Elev e1("Andrei", 17, "a XI-a", 9.50);

    cout << "\nInformatii elev:\n";
    e1.afisareElev();

    // Folosirea setterilor
    e1.setNume("Alex");
    e1.setVarsta(18);
    e1.setClasa("a XII-a");
    e1.setMedie(10);

    cout << "\nDupa modificare:\n";
    e1.afisareElev();

    // Folosirea getterilor
    cout << "\nNumele elevului: " << e1.getNume() << endl;
    cout << "Media elevului: " << e1.getMedie() << endl;

    return 0;
}
