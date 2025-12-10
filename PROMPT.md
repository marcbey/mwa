You are an expert front-end developer. Create a complete, production-ready static website for a tattoo artist studio based on the following requirements.

General:
- Use only static HTML, TailwindCSS and a small amount of JavaScript.
- Use a known, lightweight JavaScript slider library from a CDN (e.g. Swiper or similar).
- The whole site must be responsive and work well on desktop and mobile.
- Layout is one-column: header at the top, main content below, footer at the bottom.
- The header must be sticky (always visible when the user scrolls).
- Use semantic HTML5 elements (header, nav, main, section, footer, etc.).
- Output all files as if they were in a small static project:
  - `index.html`          → Home page
  - `gallery.html`        → Gallery page
  - `contact.html`        → Contact page
  - `faq.html`            → FAQ page
  - `about-moe.html`      → About Moe page
  - `impressum.html`      → Impressum page
- Use the given image paths as-is, do not invent new folders:
  - Logo: `assets/logo/studio.jpg`
  - Slider images: `assets/big-gallery/...`
  - Moe portrait: `assets/images/moe.jpg`

Design:
- Background: dark with background image assets/logo/studio.jpg
- Text color: white.
- Logo: white, use the image `assets/logo/mwa-logo-white.avif` in the header on the left.
- Navigation items next to the logo, horizontally aligned.
- Navigation items: `Gallery`, `FAQ`, `Contact & Booking`.
- Far right in the header: a white Instagram icon that links to `https://www.instagram.com/mwa.tattoo`.
- Font: use a system font stack that approximates “Apple SD Gothic Neo” but works in all browsers, for example:
  - `font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;`
- Keep the overall design clean, minimal, and easy to use.
- For the favicon convert assets/logo/elmo-2.jpg

Header (all pages):
- Left: logo (`assets/logo/mwa-logo-white.avif`).
- Next to it: navigation menu with links:
  - `Gallery` → `/gallery`
  - `FAQ` → `/faq`
  - `Contact & Booking` → `/contact`
- Right: Instagram icon in white, linking to `https://www.instagram.com/mwa.tattoo`.
- Sticky header (using CSS position sticky or fixed).
- On mobile, navigation must still be usable (e.g. simple flex-wrap or a basic burger menu; choose a simple solution).

Small Footer (all pages):
- Dark background, white text.
- Text: `© 2525 Moestwanted.Arts`
- Link to Impressum: `Impressum` → `/impressum`

Routing / links:
- `index.html` is the home page `/`.
- All internal links use the paths:
  - `/`               → `index.html`
  - `/gallery`        → `gallery.html`
  - `/contact`        → `contact.html`
  - `/faq`            → `faq.html`
  - `/about-moe`      → `about-moe.html`
  - `/impressum`      → `impressum.html`

Home page (`index.html`):
- Under the sticky header, in the main content:
  - Headline:

    Welcome to Moestwanted.Arts Tattoo

    Schön dass du hier bist!

  - Below the headline, add a horizontal image slider showing the first 10 images from `assets/big-gallery`.
    - Assume images are named sequentially or use placeholder file names like `assets/big-gallery/img1.jpg` … `img10.jpg`.
    - 3 images must be fully visible side by side on desktop.
    - The slider should be horizontally swipeable/scrollable, using the chosen slider library.
    - Each image in the slider links to the `/gallery` page.
  - Under the slider, add a section with two columns on desktop (stacked on mobile):
    - Left column (text):

      MOE steht für Emphatie, Professionalität und Vertrauen.

      Hier gibt es keine lieblosen Tattoos von der Stange
       
      Werfe doch gleich mal einen Blick in meine Galerie oder folge mir auf Instagram und mach dir selbst ein Bild davon. In den FAQs' werden hoffentlich alle deine Fragen beantwortet.

    - Right column:
      - Image: `assets/images/moe.jpg`
      - The image is wrapped in a link to `/about-moe`.

Gallery page (`gallery.html`):
- Main headline: `Moestwanted.Arts Tattoo Gallery`
- Below the headline, show a responsive image grid of all gallery images.
  - Up to 3 columns depending on viewport width (1 on small, 2 on medium, 3 on large screens).
- Use a lazy-loading strategy:
  - Use `loading="lazy"` on images and/or JavaScript to load images on scroll.
- Clicking on an image opens a detail view as an overlay/lightbox:
  - Dark semi-transparent backdrop over the whole screen.
  - Centered large version of the image.
  - Close button (X) in the corner.
  - Clicking outside the image also closes the overlay.
- Use only plain JS for the overlay/lightbox (no large framework).

Contact page (`contact.html`):
- Show a simple main headline (e.g. `Contact & Booking`).
- Below it, display 4 large, easily tappable buttons with prominent icons and clear labels for:
  1. Email:
     - Label: `E-Mail`
     - Icon: typical mail icon.
     - Link: `mailto:moestwantedarts@gmail.com`
  2. Instagram:
     - Label: `Instagram`
     - Icon: Instagram logo.
     - Link: `https://www.instagram.com/mwa.tattoo`
  3. WhatsApp:
     - Label: `WhatsApp`
     - Icon: WhatsApp logo.
     - Link: `https://wa.me/4916093809002` (international format).
  4. Linktree:
     - Label: `Linktree`
     - Icon: simple link/tree icon.
     - Link: `https://linktr.ee/Moestwantedarts`
- Layout: 1 column on mobile, 2 columns on larger screens.

FAQ page (`faq.html`):
- Headline:

  Häufig gestellte Fragen:

- Under the headline, implement an accordion-style FAQ list.
- Each question is clickable and toggles the answer open/closed.
- Only use HTML/CSS/JS (no heavy framework). A simple details/summary or custom accordion is fine.
- Use the following questions and answers exactly (German text, including line breaks and lists):

  1. Question:
     `Wie alt muss ich sein, um mich tätowieren zu lassen?`
     Answer text:

     Du musst mindestens 18 Jahre alt sein! Auch wenn du eine Einverständniserklärung deiner Eltern hast, mache ich KEINE AUSNAHME!

     Folgende Umstände schließen eine Tätowierung aus:

     • Schwangerschaft / Stillzeit
     • nach einer Operation (abhängig vom Gesundheitszustand)
     • während der Einnahme von Antibiotika
     (mind. 4 Wochen Pause, erst dann tätowiere ich Dich)
     • Hepatitis (alle Formen)
     • HIV
     • Bluterkrankheit
     • Fieber
     • Neurodermitis an der zu tätowierenden Hautstelle
     • Akne an der zu tätowierenden Hautstelle
     • alkoholisiert und unter schwerem Drogen- oder Medikamenteneinfluss
     • bei Verwendung von Betäubungscremes o.Ä.
     • bei Herz - Kreislaufstörungen, Schwindel oder Ohnmachtsgefahr
     • bei störendem Verhalten während der Sitzung
     • bei unhygienischem Erscheinen zum Termin

  2. Question:
     `Kann ich mal für eine Beratung oder einfach so vorbeikommen?`
     Answer: Der Erstkontakt für Neukunden erfolgt ausschließlichüber die Kontaktfunktion hier auf der Website! Sobald dieser statt gefunden hat, melde ich mich bei dir um einen persönlichen Termin für eine ausführliche Beratung zu vereinbaren. Ich arbeite in einem Atelier an meiner privaten Adresse, das bedeutet, während deiner Sitzung stören uns weder Laufkundschaft noch spontane Besuche, und ich kann mich in einer entspannten Atmosphäre voll und ganz auf dich konzentrieren. Deshalb bitte ich dich nicht einfach ohne Termin vorbei zu kommen, da ich dir dann nicht garantieren kann, dass ich Zeit für dich habe.


  3. Question:
     `Wo befindet sich dein Studio?`
     Answer: Mein Studio ist in der Nikolaus Str. 6; 70190 Stuttgart-Ost, Haltestelle Stöckach

  4. Question:
     `Wie lange muss man auf einen Termin warten?`
     Answer: In der Regel bekommst du relativ zeitnah einen Termin. Die tatsächliche Wartezeit hängt davon ab, wie lange ich an deinem Entwurf arbeite. Wenn du planst, dich erst in ein paar Monaten tätowieren zu lassen, dann melde dich bitte erst ca. 2-4 Wochen davor.

  5. Question:
     `Wann kann ich mit dem Entwurf rechnen?`
     Answer: Sobald ich mich mit meinem Entwurf wohl fühle, werde ich ihn dir per Whatsapp oder Mail senden. Du solltest dich vorher mit meinen Arbeiten und Stilen auseinandersetzen, um zu wissen, auf was du dich einlässt. Die besten Tattoos entstehen immer, wenn du mich nicht einschränkst, mir also freie Hand lässt und Vertrauen in meine Erfahrung und Kreativität hast.

  6. Question:
     `Kannst du mir etwas zeichnen und ich lasse es bei jemand anderem tätowieren?`
     Answer: Ich zeichne nur wenn wir auch einen Termin zum tätowieren abgemacht haben, also kannst du dir meine Zeichnungen nicht woanders tätowieren lassen! Meine Arbeit basiert auf Vertrauensbasis, wenn du also meinen Entwurf von einem anderen Tätowierer stechen lässt, schadest du nicht nur dessen Reputation, sondern du brichst auch mein Vertrauen. Wichtig ist auch zu erwähnen, dass ich keine Kopien bereits vorhandener Tattoos steche. Dazu ist mein Respekt vor der künstlerischen Leistung anderer zu groß. Ausnahme, Dir gefällt ein Bild oder eine Zeichnung und du hast den Künstler schriftlich um Erlaubnis gefragt und er hat eingewilligt!

  7. Question:
     `Anzahlung/Terminabsage`
     Answer: Für einen Termin benötige ich eine Anzahlung von 50€ bis 200€, je nach Motivgröße! Die Kontodaten werden dir mit dem Terminvorschlag per Mail zugeschickt. Eine Absage muss mindesten 7 Tage vorher stattfinden, damit ich genug Zeit habe den Termin neu zu vergeben und um die Anzahlung zu erstatten. Ansonsten wird die Anzahlung als Entschädigung einbehalten! Das gilt auch bei wetterbedingten Absagen oder Krankheit! Ich verdiene mit meiner Arbeit meinen Lebensunterhalt und habe leider keine Zeit zu verschenken.

  8. Question:
     `Abrechnung/Bezahlung`
     Answer: Die Abrechnung erfolgt nach Stunden. Das Anbringen des Motivs, Vorsorge und Nachsorge zählen zur Arbeitszeit. Bezahlt wird ausschließlich in bar, cash am Ende jeder Sitzung. Wie lange eine Sitzung dauert, kann man fast nie vorab wissen, da dazu mehrere Faktoren zählen. Denke also bitte daran, ausreichend Geld dabei zu haben.

  9. Question:
     `Pflege/Nachsorge`
     Answer: Solltest du noch keine Erfahrung mit der Pflege von Tattoos haben, bekommst du selbstverständlich von mir eine Pflegeanleitung via Whatapp zugeschickt. Für 5€ bekommst du jeweils eine Tattoo-Pflegesalbe.

  10. Question:
      `Hygiene/ Komplikationen`
      Answer: Bitte erscheine zu Deinem Termin gepflegt, nüchtern und gesund! Sollte ich Gegenteiliges feststellen, behalte ich mir vor, die Sitzung nicht zu beginnen und die Anzahlung einzubehalten. Trotz Einhaltung größtmöglicher Hygiene kann es zu Komplikationen kommen. Allergische Reaktionen und auch entzündliche Reaktionen sind möglich. Auch die Gefahr einer Infektion ist nicht auszuschließen. Zu deren Vermeidung solcher gehört auch die richtige Pflege der Wunde. Eine gesundheitlich unbedenkliche Komplikation: „BlowOut“ bedeutet, dass die Farbe in der Haut, ähnlich wie Tinte auf den Löschpapier, „ausläuft“. Das ist grundsätzlich nie auszuschließen und ist abhängig von deinem Bindegewebe. Dem Tätowierer ist es nicht möglich, dieses Risiko im Vorfeld ganz auszuschließen.

  11. Question:
      `Rechtschreibung bei Text-Tattoos`
      Answer: Bei Text-Tattoos obliegt dem Kunden die Richtigkeit der Rechtschreibung, bis zur endgültigen Freigabe durch ihn! Bei römischen Ziffern, Zitaten in Fremdsprachen, Namen und Daten jeglicher Art bitte stets selber darauf achten, ob in der Vorlage alles stimmt. Spätere Änderungen sind nur bedingt möglich.

  12. Question:
      `Information für Allergiker`
      Answer: Alle verwendeten Tattoofarben sind vom Bundesgesundheitsamt geprüft, freigegeben und zertifiziert. Manche Farben enthalten kleine Mengen von Nickel, Cadmium oder Titan, welche evtl. kleinere Reaktion während der Abheilphase zur Ursache haben, jedoch nach ein paar Tagen meist wieder verschwinden, außer vielleicht bei bekannten Allergien. Es werden diesbezüglich keine Probetattoos gemacht.

About Moe page (`about-moe.html`):
- Main headline: e.g. `About Moe`.
- Below the headline, show the Moe image `assets/images/moe.jpg` nicely (e.g. centered, rounded corners).
- Under the image, display the following text exactly, preserving paragraphs:

  Seit 2010 ist Tätowieren nicht nur mein Beruf, sondern meine Berufung – getragen von einem tiefen Anspruch an Qualität, Ästhetik und Individualität.
   
  Jedes Tattoo entsteht in engem Austausch mit der Person, die es tragen wird – als ausdrucksstarkes Unikat, das zum Körper und zur Geschichte passt.
   
  Meine künstlerische Entwicklung wurde durch zahlreiche Projekte, internationale Gastaufenthalte und Begegnungen mit anderen Künstler:innen geprägt – jede Station auf diesem Weg hat mich wachsen lassen und meine Handschrift weiter verfeinert.
   
  Heute arbeite ich in meinem eigenen privaten Tattoo-Atelier in Stuttgart Ost. Dort gestalte ich in ruhiger, fokussierter Atmosphäre individuelle Tattoos – von grafischen Konzepten über Black & Grey bis hin zu farbintensiven Arbeiten. Dabei verbinde ich technisches Know-how, ein geschultes Auge für Komposition und ein tiefes Gespür für Formen und Haut.
   
  Ich nehme mir Zeit – für die Idee, das Design, die Umsetzung.
   
  Mein Anspruch: Tätowierungen zu kreieren, die nicht nur heute wirken, sondern dich langfristig begleiten – als Teil deiner Identität.
   
  Wirf einen Blick in meine Galerie – und wenn du spürst, dass du bereit bist für ein echtes Piece: Dann lass uns reden.
   
  Werf doch gleich mal einen Blick in meine Galerie und mach dir selbst ein Bild davon.

Impressum page (`impressum.html`):
- Headline: `Impressum`.
- Display the full Impressum text exactly as provided:

  Moestwanted.Arts Inh. Michael Oßwald, Nikolaus Str. 6, 70190 Stuttgart
  Steuernummer 55314/71205 

  KONTAKT:

  E-Mail: Moestwantedarts@gmail.com

  HAFTUNGSAUSSCHLUSS (DISCLAIMER)

  Haftung für Inhalte
  [...]
  (Use the complete German text for Haftung für Inhalte, Haftung für Links, Urheberrecht exactly as specified.)

Implementation details:
- Include Tailwind via CDN in every HTML file.
- Include the slider library via CDN only where it is used (home page, optionally gallery).
- Write clean, well-indented HTML.
- Keep JavaScript simple and in `<script>` tags at the end of `<body>` or in a small inline script block.
- Do not use React, Vue, Angular or any other framework.
- Output the full contents of each HTML file in one response, separated with clear comments like:
  `<!-- index.html -->`, `<!-- gallery.html -->`, etc.
