# -counting_invoices
cena_z_vat=float(input("Wprowadź cenę zakupu z vat(cena zakupu brutto): "))
wysokosc_vat=int(input("Podaj ile % ma vat: "))
wysokosc_marzy=int(input("Podaj wysokosc marzy: "))
ilosc=int(input("Podaj ilosc produktow: "))
promocja=float(input("Podaj ile wynosi promcja: "))

cena_zakupu_brutto=cena_z_vat
to_przez_co_dzielisz= wysokosc_vat + 100
cena_zakupu_netto=(cena_zakupu_brutto*100)/to_przez_co_dzielisz
cena_sprzedazy_netto=(cena_zakupu_netto*(wysokosc_marzy/100))+cena_zakupu_netto
cena_sprzedazy_brutto=(cena_zakupu_brutto*(wysokosc_marzy/100))+cena_zakupu_brutto

def pierwsza_rzecz():
    print("Cena zakupu z VAT:",cena_zakupu_brutto)
    print("Cenza zakupu netto: ",round(cena_zakupu_netto,2))
    print("Cena sprzedazy netto: ",round(cena_sprzedazy_netto,2))
    print("Cena sprzedazy brutto: ",round(cena_sprzedazy_brutto,2))
    print("Wartosc podatku: ",round(wysokosc_vat,2))

def prom():
    produkt_po_promocji=cena_sprzedazy_brutto-(cena_sprzedazy_brutto*(promocja/100))
    print("Wartość produktu po promocji:",round(produkt_po_promocji,2))
    
def fakt():
    if (ilosc>1):
        global cena_sprzedazy_netto
        global cena_zakupu_netto

        wartosc_sprzedazy_netto=(cena_sprzedazy_netto)+((cena_sprzedazy_netto)*(promocja/100))*(ilosc-1)
        kwota_podatku=wartosc_sprzedazy_netto*(wysokosc_vat/100)
        wartosc_sprzedazy_brutto=wartosc_sprzedazy_netto+kwota_podatku
        print("Cena jednostkowa netto: ",round(cena_sprzedazy_netto,2))
        print("Wartość sprzedaży netto: ",round(wartosc_sprzedazy_netto,2))
        print("Stawka podatku: ",wysokosc_vat)
        print("Kwota podatku: ",round(kwota_podatku,2))
        print("Wartość sprzedaży brutto: ",round(wartosc_sprzedazy_brutto,2))
    else:
        podatek=cena_sprzedazy_netto*(wysokosc_vat/100)
        print("Cena jednostkowa netto: ",round(cena_sprzedazy_netto,2))
        print("Wartość sprzedaży netto: ",round(cena_sprzedazy_netto,2))
        print("Stawka podatku: ",wysokosc_vat)
        print("Kwota podatku: ",round(podatek,2))
        print("Wartość sprzedaży brutto: ",cena_sprzedazy_brutto,)

print("----------------------------------------")   
pierwsza_rzecz()
print("----------------------------------------")
prom()    
print("----------------------------------------")
fakt()
    
