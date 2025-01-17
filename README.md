codecept
# Codecept

> Supercharged End 2 End Testing
> First AI-powered testing framework 🪄

- [DNS](./DNS.md)
- [Documentation](./DOCUMENTATION.md)
- [Glossary](./GLOSSARY.md)
- [Hosts](./HOSTS.md)
- [Images](./IMAGES.md)
- [Podman](./PODMAN.md)
- [References](./REFERENCES.md)
- [Telemetry](./TELEMETRY.md)

**Executive Summary**

Real-world example:

```
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
```

Generated with [Rytr](https://app.rytr.me)

## 100 - Introduction

See [README.md](./100/README.md)

## 200 - Requirements

See [README.md](./200/README.md)

## 300 - Building Our Application

See [README.md](./300/README.md)

## 400 - Conclusion

See [README.md](./400/README.md)
