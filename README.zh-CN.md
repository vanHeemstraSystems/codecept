代码感受器

# 代码概念

> Supercharged End 2 End Testing
> First AI-powered testing framework 🪄

-   [域名系统](./DNS.md)
-   [文档](./DOCUMENTATION.md)
-   [词汇表](./GLOSSARY.md)
-   [主办方](./HOSTS.md)
-   [图片](./IMAGES.md)
-   [柔和的](./PODMAN.md)
-   [参考](./REFERENCES.md)
-   [遥测](./TELEMETRY.md)

**执行摘要**

现实世界的例子：

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

Generated with [里特尔](https://app.rytr.me)

## 100 - 简介

看[README.md](./100/README.md)

## 200 - 要求

See [README.md](./200/README.md)

## 300 - 构建我们的应用程序

看[README.md](./300/README.md)

## 400 - 结论

看[README.md](./400/README.md)
