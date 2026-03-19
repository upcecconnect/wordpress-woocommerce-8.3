# eCommerceConnect для WordPress (WooCommerce 8.3+ з підтримкою блоків)

## Системні вимоги

- **WordPress:** >= 6.3
- **WooCommerce:** >= 8.3 (протестовано до 8.6)
- **PHP:** >= 7.4

### Сумісність
Цей плагін повністю сумісний з:
- [WooCommerce Blocks](https://woo.com/document/cart-checkout-blocks-status/)

---

## Встановлення

### Версія 9.0.0
- видалити стару версію із wordpress стандартними средствами wordpress (deactivate, delete)
- встановити нову версію стандартними средствами wordpress (upload plugin)

Плагін сінхронізужться з системною мовою сайта wordpress. Наразі в плагіні реалізовано наступні мовні файли:
- [x] Англійська (en)
- [x] Українська (uk)
- [x] Болгарська (bg)
- [x] Босніййська (bs)
- [x] Німецька (de)
- [x] Угорська (hu)
- [x] Сербська (sr)
- [x] Албанська (sq)

Якщо на сайті встановлена мова, яка не пітримується плагіном, він буде англійською мовою.

### Версія 8.х
1. Завантажте плагін з GitHub та розпакуйте архів
2. Перенесіть папку `woocommerce-ecommerceconnect-gateway` в директорію `wp-content/plugins`
3. В адмін-панелі WordPress перейдіть в **Плагіни → Встановлені плагіни**, активуйте **eCommerceConnect Gateway**

---

## Налаштування

1. Перейдіть у **WooCommerce → Налаштування → Платежі → eCommerceConnect** та натисніть **Керувати**
2. Заповніть такі поля:
   - **Merchant ID** (отриманий від UPC)
   - **Terminal ID**
   - **URL платіжного шлюзу** (наприклад: `https://ecg.test.upc.ua` для тестів)
3. Активуйте **Тестовий режим**, якщо використовуєте тестове середовище
4. За потреби активуйте **Pre-authorization** (кошти будуть спочатку заморожені)
5. Встановіть **Порядок сортування** (Sort order)
6. Введіть **Приватний ключ (Private Key)** у форматі PEM, включаючи заголовки та підписи (`-----BEGIN PRIVATE KEY-----` …)
7. Для тестового середовища введіть тестовий ключ у відповідне поле (за наявності)
8. Введіть **URL зворотного виклику (Webhook)** у UPC (наприклад: `https://example.com/?wc-api=wc_gateway_ecommerceconnect`)
9. Виберіть **Основну валюту контракту**
10. Виберіть **Альтернативну валюту (USD або EUR)** для розрахунку в іншій валюті
11. Виберіть **Мову інтерфейсу платіжної сторінки** (UA, EN тощо)

---

## Списання коштів після Pre-authorization

- Якщо в налаштуваннях активовано **Pre-authorization**, кошти будуть **заморожені (hold)** після оплати
- Замовлення отримає статус **Очікує списання** (On Hold)
- Адміністратор може перейти на сторінку цього замовлення у **WooCommerce → Замовлення**
- На сторінці зʼявиться **форма списання через UPC**
- Після натискання кнопки, буде надіслано запит до UPC і замовлення отримає статус **Обробляється** (Processing)

---

## Офіційна документація UPC
- [API Checkout (українською)](https://docsecom.atlassian.net/wiki/spaces/DOCUK/pages/49644046/API+Checkout)

---

# eCommerceConnect for WordPress (WooCommerce 8.3+ with blocks support)

## Requirements

- **WordPress:** >= 6.3
- **WooCommerce:** >= 8.3 (tested up to 8.6)
- **PHP:** >= 7.4

### Compatibility
This plugin is fully compatible with:
- [WooCommerce Blocks](https://woo.com/document/cart-checkout-blocks-status/)

---

## Installation

1. Download the plugin from GitHub and unzip it
2. Move the folder `woocommerce-ecommerceconnect-gateway` to `wp-content/plugins`
3. In WordPress admin panel, go to **Plugins → Installed Plugins**, activate **eCommerceConnect Gateway**

---

## Configuration

1. Go to **WooCommerce → Settings → Payments → eCommerceConnect**, then click **Manage**
2. Fill in the following fields:
   - **Merchant ID** (provided by UPC)
   - **Terminal ID**
   - **Payment Gateway URL** (example: `https://ecg.test.upc.ua` for sandbox)
3. Enable **Test mode** if using test environment
4. Optionally enable **Pre-authorization** (funds will be held)
5. Set **Sort order**
6. Paste your **Private key (PEM format)** including headers (`-----BEGIN PRIVATE KEY-----` …)
7. Enter test keys for sandbox if applicable
8. Provide the **Callback URL (Webhook)** to UPC (example: `https://example.com/?wc-api=wc_gateway_ecommerceconnect`)
9. Choose your **Contract currency**
10. Choose **Alternative currency (USD or EUR)** for cross-currency processing
11. Select **Interface language** (UA, EN, etc.) for the payment page

---

## Capturing funds after Pre-authorization

- If **Pre-authorization** is enabled, funds will be **held (authorized)** after payment
- The order will be assigned **On Hold** status
- Admin can go to this order page via **WooCommerce → Orders**
- A **Capture via UPC** form will appear on the order page
- After clicking the capture button, the plugin will send a request to UPC and set order status to **Processing**

---

## Official UPC documentation
- [API Checkout (English)](https://docsecom.atlassian.net/wiki/spaces/DOCEN/pages/49971442/API+Checkout+by+the+payment+page)
