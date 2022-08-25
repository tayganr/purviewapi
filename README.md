# Microsoft Purview API

Slides are available in PPTX, Markdown, HTML, and PDF under the slides folder.

## :thinking: Prerequisites

- [x] Create a Microsoft Purview Account.
- [x] Create a Service Principal (`Tenant ID`, `Client ID`, `Client Secret`).
- [x] Assign the `Data Curator` role to the Service Principal.
- [x] Download and install [Visual Studio Code](https://code.visualstudio.com/).
- [x] Install the [Thunder Client](https://www.thunderclient.com/) VS Code Extension.

## 1. Setup Environment

1. Launch Visual Studio Code.
1. Open the Thunder Client extension.
1. Switch to the **Env** tab.
1. Click the Menu icon and select **Import**.
1. Select the `environment.json` file and click **Open**.
1. Open the `Microsoft Purview REST API` environment and populate all environment variables excluding `ACCESS_TOKEN` (we do not have this value yet).
1. Click **Save**.

## 2. Import Collection

1. Switch to the **Collections** tab.
1. Click the Menu icon and select **Import**.
1. Select the `collection.json` file and click **Open**.
1. Hover your mouse over the collection, click the ellipsis icon, and select **Settings**.
1. Switch to the Environment tab, attach the `Microsoft Purview REST API` environment, and click **Save**.

## 3. Generate an Access Token

1. Expand the `Microsoft Purview REST API` collection.
1. Expand the `Access Token` folder.
1. Open the `Get Access Token` request.
1. Click **Send**.
1. 