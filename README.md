# 📧 Modular HTML Email Design System

### Cross-Platform Transactional & Marketing Templates

**🚧 The Challenge:**
The client required pixel-perfect adherence to their Figma design system for their marketing campaigns. Standard drag-and-drop builders (Mailchimp/Klaviyo) broke the layout on mobile devices and failed to render custom fonts and complex grid layouts on Outlook desktop clients.

**✅ The Solution:**
I engineered a raw HTML/CSS framework using table-based layouts and conditional logic to ensure 100% rendering consistency across 40+ email clients. The system is designed to be **platform-agnostic**, meaning the same code works in Klaviyo, Brevo, and HubSpot with simple variable swaps.

**⚙️ Technical Highlights:**

- **Hybrid Coding:** Utilizes "Ghost Tables" (conditional Microsoft comments) to force responsiveness on Outlook versions 2013-2019.
- **Component-Based:** Created reusable modules (Headers, Product Grids, Footers) that allow the marketing team to mix and match without breaking code.
- **Dark Mode Support:** Includes media queries (`@media (prefers-color-scheme: dark)`) to automatically adjust text and background colors for dark mode users.

**🧪 Compatibility Matrix:**
| Client | Rendering Status | Notes |
| :--- | :--- | :--- |
| **Gmail (Mobile/Web)** | ✅ Perfect | Fully fluid grid |
| **Apple Mail** | ✅ Perfect | Supports modern CSS3 |
| **Outlook (Windows)** | ✅ Perfect | Uses VML & Ghost Tables |
| **Yahoo/AOL** | ✅ Perfect | Max-width constraints active |

**🛠 Platform Integration:**
The templates are set up with dynamic variable placeholders for easy import:

- **Klaviyo:** `{{ organization.name }}`, `{% for item in event.Items %}`
- **Mailchimp:** `*|MC:SUBJECT|*`, `*|ARCHIVE|*`
- **Brevo:** `{{ contact.FIRSTNAME }}`, `{{ params.order_id }}`

**💻 Code Sample:**
_Ensuring columns stack correctly on mobile while floating side-by-side on desktop:_

```html
<div
  style="display:inline-block; width:100%; max-width:300px; vertical-align:top;"
>
  <table width="100%">
    <tr>
      <td style="padding: 20px;">
        <h3 style="font-family: Arial, sans-serif;">Left Column</h3>
      </td>
    </tr>
  </table>
</div>
<div
  style="display:inline-block; width:100%; max-width:300px; vertical-align:top;"
>
  ...
</div>
```
