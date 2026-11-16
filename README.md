# Delfood Admin Dashboard

A lightweight, single-file admin dashboard for a restaurant and food-ordering website. It follows the visual style of the Delfood landing page (blue curved header, yellow accents, serif headings) and comes in **English** and **Arabic (RTL)** versions.

لوحة تحكم إدارية خفيفة لموقع مطعم وطلبات طعام، بتصميم مستوحى من موقع دلفود، وتتوفر بنسختين: **الإنجليزية** و**العربية (من اليمين إلى اليسار)**.

> Built with plain HTML, CSS and JavaScript. No framework, no build step, no dependencies.

## Features

- **Insights overview**
  - Total revenue, total orders, average order value and open orders
  - Revenue chart for the last 7 days
  - Orders by status, best-selling dishes and revenue by meal
- **Orders table**
  - Search by order number or customer
  - Filter by status (Pending, Preparing, Delivered, Cancelled)
  - Sortable columns and pagination
  - Order details dialog with status update (insights update instantly)
- **Food items CRUD**
  - Create, read, update and delete dishes
  - Name, meal (breakfast, lunch, dinner), price, icon, description and availability
  - Confirmation before deleting
- **Profile menu** with admin info, light/dark switch and sign-out placeholder
- Responsive layout, keyboard focus styles, automatic dark mode
- Arabic version: full RTL layout, Arabic digits, Arabic fonts, prices in EGP

## Files

| File | Description |
| --- | --- |
| `index.html` | English dashboard (LTR) |
| `ar.html` | Arabic dashboard (RTL) |
| `LICENSE` | MIT license |
| `README.md` | This file |

## Getting started

No installation needed.

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/delfood-admin.git
   cd delfood-admin
   ```
2. Open `index.html` (English) or `ar.html` (Arabic) in a browser.

To serve it locally instead:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy with GitHub Pages

1. Push the files to the `main` branch.
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and the `/ (root)` folder, then save.
4. Your site will be live at `https://<your-username>.github.io/delfood-admin/` (Arabic version at `/ar.html`).

## Important: sample data

The dashboard currently uses **in-memory sample data** (46 generated orders and 8 dishes). Changes you make, such as adding a dish or changing an order status, are lost when the page reloads. The sign-out button is a placeholder, and there is no authentication.

## Connecting a real backend

Data lives in two arrays at the top of the script, `foods` and `orders`. To use real data:

1. Replace them with `fetch()` calls to your API (for example `GET /api/orders`, `GET /api/foods`).
2. Send `POST`, `PUT` and `DELETE` requests to your API inside the food form submit handler and the delete confirmation in `foodForm()` and the click handler.
3. Send a `PATCH` request when an order status changes in `orderDlg()`.
4. Add real authentication before exposing the dashboard publicly.

## Customization

- **Colors and theme:** edit the CSS variables in `:root` (`--blue`, `--yellow`, `--orange`, and so on).
- **Currency:** change the `$$` helper (USD in `index.html`, EGP in `ar.html`).
- **Meal categories and statuses:** edit the `CATS` and `STS` constants.

## Tech stack

- HTML5, CSS3 (custom properties, grid, flexbox)
- Vanilla JavaScript (ES6)
- Google Fonts: Poppins and Cormorant Garamond (English), Cairo and Amiri (Arabic)

## Credits

The visual style is inspired by the free **Delfood** HTML template by [ThemeWagon](https://themewagon.com). No template code or images are included in this repository.

## License

Released under the [MIT License](LICENSE).
