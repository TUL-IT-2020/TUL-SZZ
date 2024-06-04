# BASE 
[[CAP teorém|CAP]] říká, že není možné plnit všechny tři požadavky najednou. 
BASE systémy neuvažují konzistenci.

- **Basically Available** říká, že systém negarantuje dostupnost (availability) z CAP 
- **Soft state** říká, že systém se může měnit za běhu dokonce i bez vstupu. Díky eventual consistency modelu.
- **Eventual consistency** říká, že systém bude konzistentní v určitém čase pokud během tohoto času nepřijde žádný vstup