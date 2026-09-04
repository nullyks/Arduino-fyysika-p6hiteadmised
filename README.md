# Arduino kasutamiseks vajalike füüsika põhiteadmiste kordamine

See õppematerjal on jätk õppematerjalile [„Sissejuhatus Arduino arendusplaatide kasutamisse”](https://github.com/nullyks/Arduino-sissejuhatus). Eeldame, et õppija oskab Arduino arendusplaadi arvutiga ühendada, sellele programmi laadida ning nupu ja LED-i abil lihtsaid sisend- ja väljundahelaid koostada.

Selles õppematerjalis korratakse Arduino projektide jaoks vajalikke füüsika põhiteadmisi. Materjalis käsitletakse Ohmi seadust, elektrivõimsust, jada- ja rööpühendust, multimeetri kasutamist ning vooluahelate koostamist ja simuleerimist.

Kursusel kasutatakse Arduino UNO R3 ja Arduino UNO R4 WiFi arendusplaate. Arvutused ja füüsilised ühendused koostatakse mõlemale plaadile sobivalt. Tinkercadi näidetes kasutatakse UNO R3 plaati, sest simulatsioonikeskkond ei paku UNO R4 WiFi mudelit.

## Õpieesmärgid

Pärast selle õppematerjali läbimist oskad kasutada Ohmi seadust ja elektrivõimsuse valemeid lihtsate alalisvooluahelate arvutamiseks. Oskad eristada jada- ja rööpühendust, kasutada multimeetrit ohutult pinge, voolutugevuse ja takistuse mõõtmiseks ning koostada ja simuleerida lihtsaid vooluahelaid. Samuti oskad hinnata, kas valitud komponent ja ühendus sobivad Arduino UNO R3 või UNO R4 WiFi elektriliste piirangutega.

## Õpiväljundid

Materjali edukalt läbinud õppija oskab:

* selgitada pinge, voolutugevuse, takistuse ja elektrivõimsuse tähendust ning kasutada nende korrektseid ühikuid;
* sõnastada Ohmi seaduse ja kasutada seda pinge, voolutugevuse või takistuse arvutamiseks;
* arvutada komponendis hajuvat elektrivõimsust ja valida sobiva võimsustaluvusega takisti;
* arvutada jada- ja rööpühenduse kogutakistust ning ahela harude pingeid ja voolutugevusi;
* mõõta multimeetriga ohutult alalispinget, alalisvoolutugevust ja takistust;
* koostada vooluahela ühendus- ja skeemijoonise ning kontrollida arvutusi simulatsioonikeskkonnas;
* hinnata vooluahela sobivust Arduino UNO R3 ja UNO R4 WiFi elektriliste piirangutega;
* koostada lihtsa seadme elementaarse dokumentatsiooni.

## Hindamisjuhend

Selle õppematerjali puhul rakendatakse mitteeristavat hindamist.

Õppematerjal loetakse arvestatuks, kui õppija lahendab iseseisvalt vähemalt neli viiest iseseisvast ülesandest. Lahendus sisaldab ülesandest olenevalt:

* arvutuskäiku koos valemite, ühikute ja põhjendatud vastusega;
* vooluahela ühendus- või skeemijoonist;
* simulatsiooni tulemust ja selle võrdlust arvutatud väärtustega;
* töötavat ning kommenteeritud Arduino programmi;
* lühikest järeldust või seadme töö kirjeldust.

Füüsilise vooluahela koostamisel peab õppija järgima multimeetri ja Arduino ohutusnõudeid. Arduino viigu voolupiiri ületav või muul viisil seadmeid kahjustada võiv ühendus tuleb enne katsetamist parandada.

## Vajalikud vahendid

* 1 x internetiühenduse ja veebibrauseriga personaalarvuti;
* 1 x Arduino UNO R3 või Arduino UNO R4 WiFi arendusplaat;
* 1 x arendusplaadile sobiv USB-andmesidekaabel — UNO R3 puhul tavaliselt USB-B ja UNO R4 WiFi puhul USB-C;
* 4 x LED-i, soovitatavalt eri värvi;
* 4 x 470 Ω takisti;
* 1 x makettplaadiga ühilduv surunupp;
* 1 x 10 kΩ lineaarne potentsiomeeter;
* 1 x makettplaat;
* makettplaadi ühendusjuhtmed, isane-isane;
* 1 x digitaalne multimeeter koos testjuhtmetega;
* juurdepääs Falstad Circuit Simulatorile ja Tinkercad Circuitsile;
* Fritzingi tarkvara seadme ühendusjoonise koostamiseks.

## Õppematerjali osad

* [Ohmi seadus](materjalid/1_Ohmi_seadus.md)
* [Elektrivõimsus](materjalid/2_võimsus.md)
* [Vooluahelad](materjalid/3_vooluahelad.md)
* [Multimeetri kasutamine](materjalid/4_multimeetri_kasutamine.md)
* [Vooluahelate skeemide koostamine ja simuleerimine](materjalid/5_skeemide_koostamine_ja_simuleerimine.md)
* [Iseseisvad ülesanded](materjalid/6_iseseisvad_ülesanded.md)

## Õppematerjali koostaja

Tanel Toova ([tanel.toova@tlu.ee](mailto:tanel.toova@tlu.ee))

## Panustamine

Parandus- ja täiendusettepanekute tegemiseks vaata [panustamisjuhendit](CONTRIBUTING.md) ning [kaastöötajate nimekirja](CONTRIBUTORS.md).

## Litsents

Õppematerjal on avaldatud [Creative Commonsi Attribution-ShareAlike 4.0 Internationali ehk CC BY-SA 4.0 litsentsi](LICENSE) alusel.
