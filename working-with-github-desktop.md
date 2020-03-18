# Arbeta med GitHub Desktop

> En guide för att arbeta med [GitHub Desktop](https://desktop.github.com).

![GitHub Desktop](images/github-desktop-landing-page.png)

## Innehållsförteckning

* [Förord](#Förord)
* [Förberedelser](#Förberedelser)
* [Terminologi](#Terminologi)
* [Skapa ett repository](#Skapa-ett-repository)
  - [Lägg till användare](#Lägg-till-användare)
* [Arbeta lokalt med GitHub Desktop](#Arbeta-lokalt-med-GitHub-Desktop)
  - [Klona ett repository](#Klona-ett-repository)
  - [Arbetsvy](#Arbetsvy)
  - [Historik](#Historik)
* [Göra ändringar](#Göra-ändringar)
  - [Skapa en branch](#Skapa-en-branch)
  - [Uppdatera .gitignore](#Uppdatera-.gitignore)
  - [Publicera ändringar](#Publicera-ändringar)
  - [Pull request](#Pull-request)

## Förord

*Detta är för stunden ett levande dokument som uppdateras allt eftersom.*

Det rekommenderas att följa denna guide från start till slut för att få en bra helhet till hur vi kan arbeta med GitHub Desktop (Git och GitHub). Därefter är det enkelt att ta beslut om vilken process som sedan lämpar sig bäst för just ert projekt.

## Förberedelser

Till att börja med måste ni [registrera er på GitHub](https://github.com/join).

För att följa med i denna guiden krävs det att ni installerar:

* [GitHub Desktop](https://desktop.github.com) (versionshantering)
* [Atom](https://atom.io) (textredigerare)

Det finns givetvis fler alternativ till textredigerare men i denna guiden används [Atom](https://atom.io) då den har bra integration med både Git och GitHub. Ett alternativ är [Visual Studio Code](https://code.visualstudio.com) som har likvärdigt stöd för Git och GitHub.

Syftet med dessa textredigerare i denna guiden är huvudsakligen integrationen med Git och GitHub, till exempel hur dessa underlättar hantering av *merge konflikter*, inte att dom nödvändigtvis måste användas till programmering.

## Terminologi

Nedan finner ni en tabell över några vanliga termer och en kortare beskrivning.

Term          | Betydelse
------------- | -----------------
Repository    | Ert projekt, dvs. alla era filer.
`.gitignore`  | Innehåller sökvägar till filer som **inte** ska publiceras till GitHub.
`README.md`   | Det innehåll som visas när någon besöker projektsidan på GitHub. Formateras enligt [Markdown](https://guides.github.com/features/mastering-markdown/).
Commit        | Att spara en eller flera ändringar med ett beskrivande meddelande.
Branch        | En version av ert projekt. Ni skapar en *branch* varje gång någon vill göra ändringar (*commits*).
Merge         | Sammanställ *commits* från en *branch* till en annan.
Working copy  | Den nuvarande *branch* (version) som ni redigerar.
Checkout      | Byta från en *branch* till en annan, dvs. er *working copy* ändras.
Remote        | Den plats där era ändringar sparas, GitHub i ert fall.
Pull          | Hämta *commits* från er *remote*.
Push          | Publicera *commits* till er *remote*.
Pull request  | Skapa ett förslag till en *commit* som sedan kan *mergas*, diskussion sker via GitHub.
Conflict      | När en *merge* från en *branch* till en annan har filändringar som kolliderar.

## Skapa ett repository

När ni har registrerat er och loggat in på [GitHub](https://github.com) kan ni i huvudmenyn välja att skapa ett nytt repository. På sidan för att skapa ett nytt repository har ni sedan möjlighet att fylla i följande uppgifter:

1. Namnet på ert repository.
2. En kort beskrivning över ert projekt (valfritt).
3. Om ert repository ska vara publikt eller privat (**välj publikt**).
4. Om ert repository ska skapas med en `README.md` (**checka i denna**).
5. Om ert repository ska skapas med en `.gitignore`.
    * **Välj en** av följande: *Unity*, *VisualStudio*, *Java* eller *Python*. Vi kommer redigera detta i ett senare skede.
6. Om ert repository ska skapas med en licens (valfritt).  

**Skapa ett nytt repository:**

![Github: create a new repository](images/2-github-create-new-repo.png)

**Ert nya repository:**

![Github: new repository](images/4-github-repo-initial-commit.png)

### Lägg till användare

Innan vi går vidare med att skapa mer innehåll i vårt repository så ska vi börja med att lägga till fler användare. Så att vi har möjlighet att börja samarbeta.

![Github: invite collaborator](images/13-github-repo-settings.png)

## Arbeta lokalt med GitHub Desktop

Nästa steg är nu att kunna börja arbeta lokalt och detta kommer ske med hjälp av [GitHub Desktop](https://desktop.github.com). Första gången ni öppnar denna applikationen presenteras ni med följande:

![Github desktop: first glance](images/5-github-desktop-first-glance.png)

### Klona ett repository

Efter ni startat applikationen första gången ska ni sedan hämta ert repository från GitHub, detta kallas att *klona* ett repository. För att göra detta klickar ni på "Clone a Repository [...]" och där ni kan ni sedan välja att logga in med ert GitHub konto, då får ni tillgång till alla repositories ni har.

![Github desktop: sign in](images/6-github-desktop-sign-in.png)

Därefter kommer ni i högerspalten se en lista över dessa **men** klicka istället på klona *igen* så ni kan välja till vilken mapp ni vill ha ert projekt i.

*Vi kommer att fortsätta göra ändringar i detta repository innan ni går vidare med att lägga till alla era egna filer och kan börja arbeta på riktigt.*

![Github desktop: clone](images/8-github-desktop-clone-repo.png)

### Arbetsvy

När ni klonat ert första repository kommer ni till *arbetsvyn* och det är denna som ni sedan huvudsakligen kommer arbeta med. Denna är indelad i två sidor, till vänster hittar ni de filer ni gjort ändringar till och till höger hittar ni vilka ändringar som gjorts (baserat på den fil ni markerat i vänstersidan).

![Github desktop: first use](images/9-github-desktop-first-use.png)

Om ni behöver ändra vilken textredigerare som ska gälla går ni in på *inställningar*.

Ni kan under *Preferences* -> *Integrations* sedan välja att byta textredigerare (t.ex. som i mitt fall, till Atom).

![Github desktop: preferences](images/10-github-desktop-preferences.png)

### Historik

I vänsterspalten kan vi välja *History* istället för *Changes* vilket ger oss *historikvyn* som helt enkelt visar all historik över ändringar.

![Github desktop: history](images/15-github-desktop-history.png)

## Göra ändringar

Nu när vi är igång ska vi göra vår första ändring (*commit*) och skicka denna till GitHub (*push*). Det första vi ska göra är att se till att vår `.gitignore` är i ordning, skulle vi inte göra detta så kommer alla filer vi lägger till i vårt repository att skickas till GitHub. Vissa filer vill endast ska finnas lokalt och behövs inte finnas centralt på GitHub, till exempel kanske vi har en fil med lösenord eller så kan det vara att det skapas filer temporärt lokalt (backups med mera) som inte ska sparas.

Eftersom vi nu ska börja arbeta med vårt repository så ska vi skapa vår första *branch* (en version av vårt repository). Detta gör vi för att vi ska kunna arbeta flera stycken parallellt, det vill säga alla har varsin version (*branch*) av samma kodbas och på så vis kan alla arbeta lokalt. Det finns däremot en *branch* som alltid finns kvar och det är **master** - denna är kärnan för hela ert repository.

När vi arbetat klart med vår *branch*, i detta fallet med `.gitignore`, kommer vi att stoppa in våra ändringar i **master branchen**, detta är vad som kalls att göra en *merge*. Anledningen till detta är för att när vi färdigställt vårt arbete vill vi de andra i projektet ska kunna hämta dessa *commits* och fortsätta arbeta.

### Skapa en branch

Vi börjar med att skapa en ny *branch*, som vi kan döpa till `update-gitignore`.

![Github desktop: create branch](images/16-github-desktop-create-branch-gitignore.png)

### Updatera .gitignore

Nu ska vi ersätta det innehåll som förvaldes i vår `.gitignore` när vi skapade vårt repository. Det första steget är att bestämma oss för vad som ska ignoreras, lyckligtvis så finns tjänsten [gitignore.io](https://gitignore.io) för detta. När ni söker så tänk på vilket operativsystem ni har, vilken textredigerare, vilket programmeringsspråk och eventuella bibliotek eller ramverk.

Ett webbrelaterat projekt hade kunnat söka på följande:

![Gitignore: search](images/gitignore-io-search.png)

Därefter skickas ni till en sida innehållande den text som ska placeras i `.gitignore`, **kopiera denna**.

![Gitignore: copy](images/gitignore-io-copy.png)

I mitt fall hade jag öppnat Atom och **klistrat** in detta innehållet och sedan **sparat** filen:

![Atom: gitignore](images/17-atom-add-gitignore-contents.png)

Direkt när jag gjort detta, det vill säga gjort en ändring jag sedan vill spara på GitHub, så öppnar vi GitHub Desktop igen.

![Github desktop: commit gitignore](images/18-github-desktop-update-gitignore.png)

### Publicera ändringar

För att spara våra ändringar (*push*), det vill säga vår *branch* och det nya innehållet i `.gitignore`, väljer vi "Publish branch".

![Github desktop: publish branch](images/19-github-desktop-publish-and-create-pull-request.png)

Nu ska vår version och ändringar finnas på GitHub. Nu kan vi antingen fortsätta att arbeta eller, om vi känner oss färdiga med denna versionen, stoppa in våra ändringar i **master** (det vill säga en *merge*). Ett vanligt arbetssätt för detta är att skapa en så kallad **pull request**, vilket kort kan beskrivas som att vår version är redo för att granskas innan den *mergas* till **mastern**.

### Pull request

För att göra en **pull request** kan ni klicka på "Create Pull Request" där det tidigare stod "Publish branch". Ni kommer därefter skickas till en webbläsare som öppnar följande sida:

![Github: create pull request](images/20-github-open-a-pull-request.png)

Därefter inväntar ni att andra granskar och ger feedback. **Klicka inte Merge pull request ännu.**

![Github: pull request](images/21-github-pull-request-1.png)

Låt oss nu säga att någon ser att någonting behövs läggas till i vår `.gitignore`, i detta fallet får jag simulera det på egen hand.

![Github: pull request comment](images/22-github-pull-request-2.png)

Kommentaren föreslår att vi ska även ignorera filer från Windows i vår `.gitignore`. Då går vi tillbaka till [gitignore.io](https://gitignore.io). Söker upp Windows och kopierar in detta innehåll i vår textredigare.

![Gitignore: search windows](images/gitignore-io-add-windows.png)
![Gitignore: copy windows](images/gitignore-io-add-windows.png)

Därefter sparar våra ändringar (*commit*) och skickar dom till GitHub (*push*).

![Github desktop: commit update gitignore](images/23-github-desktop-add-windows-to-gitignore.png)

*Glöm inte klicka Push origin.*

Nu kan vi gå in till vår **pull request** (på GitHub) och se att vår *commit* har dykt upp.

![Github: pull request update](images/24-github-pull-request-3.png)

Nu känner vi oss redo med vår version och går därför vidare till att stoppa in vår version (*merge*) till **master branchen**.

![Github: merge pull request](images/26-github-merge-pull-request-2.png)
![Github: merge pull request complete](images/27-github-pull-request-4.png)

Nu är vi ju färdiga med vår version, som var till för att skapa ändringar till `.gitignore`. Då kan vi radera den både lokalt och på GitHub. Detta gör vi enklast genom GitHub Desktop.

![Github desktop: delete branch](images/28-github-desktop-delete-branch.png)

Nästa steg är nu att hämta denna ändringen från GitHub (vår merge) till vår lokala **master**.

![Github desktop: fetch and pull to master](images/29-github-desktop-pull-origin-master.png)

Nu kan vi se historiken från vår *branch* (version) även i **mastern**.

[!Github desktop: new master branch history](images/30-github-desktop-history.png)

Nu har ni gått igenom den process som kan nyttjas för alla era ändringar, **dock** finns det fler metoder men denna är något som ingår i GitHubs egna förslag till att arbeta med Git och GitHub - [GitHub flow](https://guides.github.com/introduction/flow/).