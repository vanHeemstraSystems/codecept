程式碼感受器

# 程式碼概念

> 增壓端2端測試
> 第一個人工智慧驅動的測試框架🪄

-   [域名系統](./DNS.md)
-   [文件](./DOCUMENTATION.md)
-   [詞彙表](./GLOSSARY.md)
-   [主辦單位](./HOSTS.md)
-   [圖片](./IMAGES.md)
-   [柔和的](./PODMAN.md)
-   [參考](./REFERENCES.md)
-   [遙測](./TELEMETRY.md)

**執行摘要**

現實世界的例子：

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

生成於[里特爾](https://app.rytr.me)

## 100 - 簡介

看[README.md](./100/README.md)

## 200 - 要求

看[README.md](./200/README.md)

## 300 - 建立我們的應用程式

看[README.md](./300/README.md)

## 400 - 結論

看[README.md](./400/README.md)
