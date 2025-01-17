कोडसेप्ट

# कोडसेप्ट

> सुपरचार्ज्ड एंड 2 एंड टेस्टिंग
> पहला एआई-संचालित परीक्षण ढांचा 🪄

-   [डीएनएस](./DNS.md)
-   [प्रलेखन](./DOCUMENTATION.md)
-   [शब्दकोष](./GLOSSARY.md)
-   [मेजबान](./HOSTS.md)
-   [इमेजिस](./IMAGES.md)
-   [मातहत](./PODMAN.md)
-   [संदर्भ](./REFERENCES.md)
-   [टेलीमेटरी](./TELEMETRY.md)

**कार्यकारी सारांश**

वास्तविक दुनिया का उदाहरण:

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

के साथ उत्पन्न हुआ[रित्र](https://app.rytr.me)

## 100 - Introduction

देखना[README.md](./100/README.md)

## 200 - Requirements

देखना[README.md](./200/README.md)

## 300 - हमारे एप्लिकेशन का निर्माण

देखना[README.md](./300/README.md)

## 400 - निष्कर्ष

देखना[README.md](./400/README.md)
