# Yrityksen ilmastoriskit

Pohjois-Karjalan pk-yrityksille tarkoitettu itsenäinen fyysisten ilmastoriskien
valmistelutyökalu. Demo 1.1, 11.9.2026. 18 mukautuvaa arviointikysymystä,
26 mahdollista toimea ja yrityksen oma, tulostettava ensitoimien lista.

## Kokeile heti

Pura ZIP ja avaa `index.html` selaimessa. Vaihtoehtona erikseen toimitettu
`yrityksen-ilmastoriskit-demo.html` sisältää myös kuvat ja fontit yhdessä tiedostossa.
Kokeile aloitussivulta kuvitteellista luontomatkailuyritystä tai valmistavaa yritystä.
Esimerkin voi korvata omalla arviolla valitsemalla ”Tyhjennä oma arvio”.

Vastaukset säilyvät vain avoimen sivun muistissa. Päivitys tai sulkeminen hävittää
ne. Tallenna toimintalista Excelinä, tekstinä tai PDF:nä ennen sulkemista. Koko arvio on lisäksi ladattavissa erikseen tekstinä. Sovellus ei
lähetä vastauksia palvelimelle, käytä evästeitä tai analytiikkaa eikä tarvitse
kirjautumista, tietokantaa, palvelinlogiikkaa tai ChatGPT:tä.

## Julkaise GitHub Pagesissa

1. Luo GitHubiin julkinen repositorio, esimerkiksi `yrityksen-ilmastoriskit`.
2. Pura ZIP ja siirrä sen sisältö repositorion `main`-haaran juureen
   (**Add file → Upload files**). `index.html` tulee suoraan juureen.
   Siirrä myös koko **assets-kansio** sen nimisenä ja `.nojekyll`-tiedosto.
   Älä lataa pelkkää ZIPiä äläkä siirrä kuvien sisältöä juureen ilman kansiota.
3. Avaa **Settings → Pages → Build and deployment**.
4. Valitse **Source: Deploy from a branch**, haaraksi **main**,
   kansioksi **/(root)** ja paina **Save**.
5. Avaa valmistuttua **Visit site**. Osoite on yleensä
   `https://KAYTTAJA.github.io/yrityksen-ilmastoriskit/`.
   Jaa tämä verkkosivulinkki, älä repositorion koodinäkymän osoitetta.

Julkaistu sivu avautuu ilman kirjautumista. Oma domain tai käännösvaihe ei ole
tarpeen. Polut toimivat myös GitHub Pagesin projektihakemistossa.

[GitHubin virallinen ohje](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## Vaihtoehto: Azure Storage Static Website

Ota StorageV2-tilin **Static website** käyttöön ja aseta aloitussivuksi `index.html`.
Siirrä puretut verkkosivutiedostot ja assets-kansio `$web`-säilöön samoin poluin
esimerkiksi Storage Explorerilla. Jaa **Primary endpoint** -HTTPS-osoite ja
varmista, että tilin verkkoasetukset sallivat julkisen käytön. Käytä staattisen
verkkosivun osoitetta, älä Blob-palvelun tiedostolinkkiä. Sovellus ei tallenna
vastauksia Azureen; säilö sisältää vain julkaistut verkkosivutiedostot.

[Microsoftin virallinen ohje](https://learn.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website-how-to)

## Paketin sisältö

- `index.html`, `style.css`, `data.js`, `app.js`, `export-xlsx.js`: toimiva verkkosovellus.
- `assets/`: alkuperäinen EU-tunnus, Pohjois-Karjalan logo, Ubuntu-fontit ja lisenssi.
- `research/LAHTEET-JA-RAKENNE.md`: kaikki kysymykset ja toimet lähdeperusteluineen,
  kohdentaminen sekä menetelmän rajaukset.
- `research/rakenne.json`: sama sisältörakenne koneluettavana.
- `research/check.mjs` ja `research/check-exports.mjs`: kehittäjän tarkistukset;
  suoritus `node research/check.mjs` ja `node research/check-exports.mjs`.
- `.nojekyll`: GitHub Pagesin asetus. Ei ulkoisia kirjastoja tai riippuvuuksien asennusta. Excel-tiedosto muodostetaan paikallisella `export-xlsx.js`-moduulilla; se ei käytä verkkopalvelua.

Lähde-PDF:t avataan linkeistä verkossa, eivätkä ne sisälly pakettiin. Muut resurssit
ovat paikallisia. PHP:tä, Node-palvelinta tai API-avaimia ei tarvita julkaisuun.

## Tulostus ja pilotointi

Valitse lopuksi ”Tulosta / tallenna PDF” tai selaimen normaali tulostuskomento.
Asetukset: A4, skaala 100 %, selaimen omat ylä- ja alatunnisteet pois.
Listalle mahtuu enintään kolme ensitoimea; vapaille kirjauksille on pituusrajat.
Jos selaimesi jakaa listan usealle sivulle, lyhennä kirjauksia tai sovita skaalaa.
”Lataa toimintalista Excelinä” muodostaa aidon .xlsx-tiedoston suoraan selaimessa. ”Lataa toimintalista tekstinä” muodostaa saman yhteenvedon .txt-tiedostoksi. Molemmat sisältävät kolme tärkeintä vaikutusta, kaikki avoimet arviointikohdat, valitut ensitoimet, vastuut, tavoiteajat ja oman huomion. Koko arvio voidaan ladata erikseen TXT-tiedostoksi. PDF:n tallentamiseksi valitse selaimen tulostusikkunassa ”Tallenna PDF-muodossa”. PDF:n saavutettava rakenne on
selainkohtainen, eikä sen tunnisteita ole tässä tarkistettu.

Kooditarkistukset läpäisty: lähdeviitteet ja tunnisteet, kohdentamisen haarat,
kielteiset/avoimet vastaukset, lumi–jää-erottelu, muuttunut soveltuvuus, tulosteiden
sisältö, HTML-tekstin suojaus, paikalliset assetit ja keskeiset kontrastit.
Version 1.1 varautumislogiikka ja vientipolut on tarkistettu. Excel-tiedoston ZIP/XML-rakenne ja sisältö on lisäksi avattu riippumattomalla lukijalla: ääkköset, kirjaukset ja alkuperäinen EU-logo säilyvät, ja kaavalta näyttävät käyttäjätekstit pysyvät tekstinä. Excel-työpöytäsovelluksen tarkistusta, selain-, ruudunlukija- tai tulostuksen visuaalista auditointia ei ole tehty.
Testaa pilotissa koko polku mobiililla, näppäimistöllä ja ruudunlukijalla sekä
arvioi yritysten kanssa kysymysten ymmärrettävyys ja 10–15 minuutin tavoiteaika.

Sovellus on valmistelu- ja keskustelutyökalu, ei sertifioitu riskianalyysi.
Pohjois-Karjalan paikallinen riskiperusta tulee tiekartasta (2025) ja yrityksen
arviointilogiikka ILMASTOARVOsta (2026). Menetelmiä on kevennetty ja sovellettu;
siirtymäriskit, päästöt ja ESG on rajattu pois. Lähdeselitteet ovat myös työkalussa.

Pohjois-Karjalan ja EU:n tunnuksia käytetään hankkeen yhteydessä; niitä ei
uudelleenlisensoida tällä paketilla. Rahoitusmerkintä ja EU-tunnus sisältyvät
käyttöliittymään ja tulosteeseen. Päivitys tehdään korvaamalla vastaavat tiedostot
samassa julkaisupaikassa. Tätä pakettia ei ole julkaistu käyttäjän GitHub- tai
Azure-tilille tämän tehtävän yhteydessä.

## Muutokset versiossa 1.1

- Nimi on **Yrityksen ilmastoriskit**. Aloitusteksti selittää sään, ilmaston ja
  sopeutumisen yhteyden. Nimi- ja toimialakentät alkavat samalla tasolla.
- Alustavan arvion ohje ja riippuvuuskysymykset on selkeytetty.
- Havaittu tai mahdollinen häiriö ja nykyinen varautuminen arvioidaan erikseen.
  Vaihtoehdot: ei varautumista, työn alla, suunnitelma olemassa, toimivuutta
  kokeiltu tai tilanne selvitettävä. Puuttuva tieto ei merkitse varautumista.
- Suunnitelma ohjaa kattavuuden ja toimivuuden tarkistukseen. Se ei automaattisesti
  merkitse yksittäisiä toimenpiteitä tehdyiksi. Vaikutus arvioidaan nykyinen
  varautuminen huomioiden; työkalu ei laske jäännösriskipisteitä.
- Excelissä kaikki käyttäjän tekstit ovat tekstisoluja; ne eivät muutu kaavoiksi.
  Toimintalistan Excel ja teksti sisältävät vastaavat tiedot kuin tulostusnäkymä.

## Päivitä jo julkaistu sivu

Korvaa repositorion `index.html`, `style.css`, `data.js` ja `app.js` tämän paketin
versioilla. Lisää myös uusi **`export-xlsx.js`** ja säilytä koko assets-kansio.
Helpoin tapa on siirtää puretun ZIPin koko sisältö samoihin hakemistoihin.
Tallenna muutokset (Commit changes); Pages päivittää sivuston. Jos selain näyttää
vanhaa versiota, päivitä sivu uudelleen esimerkiksi Ctrl+F5:llä. Älä tee tätä
kesken tallentamattoman arvion. Jo käytössä olevaa repositoriota tai sen nimeä
ei tarvitse vaihtaa työkalun otsikon muutoksen vuoksi.
