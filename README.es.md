codecepto

# Codecepto

> Prueba de extremo 2 sobrealimentado
> Primer marco de pruebas impulsado por IA 🪄

-   [DNS](./DNS.md)
-   [Documentación](./DOCUMENTATION.md)
-   [Glosario](./GLOSSARY.md)
-   [Anfitriones](./HOSTS.md)
-   [Imágenes](./IMAGES.md)
-   [Suave](./PODMAN.md)
-   [Referencias](./REFERENCES.md)
-   [Telemetria](./TELEMETRY.md)

**Resumen ejecutivo**

Ejemplo del mundo real:

    const { faker } = require('@faker-js/faker');                               // Use 3rd-party JS code

    Feature('Store');

    Scenario('Create a new store', async ({ I, login, SettingsPage }) => {
      const storeName = faker.lorem.slug();
      login('customer');                                          // Login customer from saved cookies
      SettingsPage.open();                                        // Use Page objects
      I.dontSee(storeName, '.settings');                          // Assert text not present inside an element (located by CSS)
      I.click('Add', '.settings');                                // Click link by text inside element (located by CSS)
      I.fillField('Store Name', storeName);                       // Fill fields by labels or placeholders
      I.fillField('Email', faker.internet.email());
      I.fillField('Telephone', faker.phone.phoneNumberFormat());
      I.selectInDropdown('Status', 'Active');                     // Use custom methods
      I.retry(2).click('Create');                                 // Retry flaky step
      I.waitInUrl('/settings/setup/stores');                      // Explicit waiter
      I.see(storeName, '.settings');                              // Assert text present inside an element (located by CSS)
      const storeId = await I.grabTextFrom('#store-id');          // Use await to get information from browser
      I.say(`Created a store with ${storeId}`);                   // Print custom comments
    }).tag('stores');`;

Generado con[ritr](https://app.rytr.me)

## 100 - Introducción

Ver[README.md](./100/README.md)

## 200 - Requisitos

Ver[README.md](./200/README.md)

## 300 - Construyendo nuestra aplicación

Ver[README.md](./300/README.md)

## 400 - Conclusión

Ver[README.md](./400/README.md)
