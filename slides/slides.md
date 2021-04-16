---
marp: true
---

# Azure Purview  REST API

[aka.ms/purviewapi](https://aka.ms/purviewapi)

---

<!-- _footer: "Azure Purview High-Level Concepts" -->

![bg width:95%](../image/purviewapi.png)

<style>
section.left h4, section.left p {
  text-align: left;
}
</style>

---

## :rocket: Getting Started

---

<!-- _footer: "https://docs.microsoft.com/en-us/azure/purview/tutorial-using-rest-apis#prerequisites" -->


### :thinking: Prerequisites

* An existing **Azure Purview** account.
* You will need sufficient permissions to **register** an application (i.e. service principal) within your Azure AD tenant.
* You will need sufficient permissions to assign the application a **role** (e.g. `Purview Data Curator`) in order for Azure Purview to trust your new service principal.

---

<!-- _footer: "https://docs.microsoft.com/en-us/azure/purview/tutorial-using-rest-apis#create-a-service-principal-application" -->


### :globe_with_meridians: Create a Service Principal

1. From the [Azure Portal](https://portal.azure.com), navigate to **Azure Active Directory**.
2. Select **App registrations**.
3. Select **New registration**.
4. Populate the **Register an application** form.  

    * Name (e.g. `purviewapi`)
    * Supported account types (e.g. `Single tenant`)
    * Redirect URI (*this can be left blank*)
5. Click **Register**.

---

6. Copy the values **Application (client) ID** and the **Directory (tenant) ID** for later use.

    ![Service Principal](../image/service_principal.png)

---

<!-- _footer: "https://docs.microsoft.com/en-us/azure/purview/tutorial-using-rest-apis#create-a-service-principal-application" -->


### :key: Create a Client Secret

In order to use the service principal, we need generate a password (aka client secret).

1. From the [Azure Portal](https://portal.azure.com), navigate to **Azure Active Directory**.
2. Select **App registrations**.
3. Select your service principal from the list.
4. Select **Certificates & secrets**.
5. Select **New client secret**.
6. On the **Add a client secret** form, enter a **Description**, select an expiration period under **Expires**, and then select **Add**.

---

7. Copy the value **client secret**  for later use.

    ![Service Principal](../image/client_secret.png)

---

<!-- _footer: "https://docs.microsoft.com/en-us/azure/purview/tutorial-using-rest-apis#create-a-service-principal-application" -->


### :lock: Configure Azure Purview to Trust the Service Principal

1. From the [Azure Portal](https://portal.azure.com), navigate to your **Azure Purview** account.
2. Select **Access control (IAM)**.
3. Select **Add role assignments**.
4. For **Role**, select `Purview Data Curator`.
5. For **Assign access to**, leave the default `User, group, or service principal`.
6. For **Select**, enter the name of the service principal (e.g. `purviewapi`) and then click on the name in the results pane.
7. Click **Save**.

---