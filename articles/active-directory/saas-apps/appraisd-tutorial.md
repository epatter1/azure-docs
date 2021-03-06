---
title: 'Tutorial: Azure Active Directory integration with Appraisd | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Appraisd.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 05/27/2019
ms.author: jeedes
---

# Tutorial: Integrate Appraisd with Azure Active Directory

In this tutorial, you'll learn how to integrate Appraisd with Azure Active Directory (Azure AD). When you integrate Appraisd with Azure AD, you can:

* Control in Azure AD who has access to Appraisd.
* Enable your users to be automatically signed-in to Appraisd with their Azure AD accounts.
* Manage your accounts in one central location - the Azure portal.

To learn more about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis).

## Prerequisites

To get started, you need the following items:

* An Azure AD subscription. If you don't have a subscription, you can get a [free account](https://azure.microsoft.com/free/).
* Appraisd single sign-on (SSO) enabled subscription.

## Scenario description

In this tutorial, you configure and test Azure AD SSO in a test environment. Appraisd supports **SP and IDP** initiated SSO.

## Adding Appraisd from the gallery

To configure the integration of Appraisd into Azure AD, you need to add Appraisd from the gallery to your list of managed SaaS apps.

1. Sign in to the [Azure portal](https://portal.azure.com) using either a work or school account, or a personal Microsoft account.
1. On the left navigation pane, select the **Azure Active Directory** service.
1. Navigate to **Enterprise Applications** and then select **All Applications**.
1. To add new application, select **New application**.
1. In the **Add from the gallery** section, type **Appraisd** in the search box.
1. Select **Appraisd** from results panel and then add the app. Wait a few seconds while the app is added to your tenant.

## Configure and test Azure AD single sign-on

Configure and test Azure AD SSO with Appraisd using a test user called **B. Simon**. For SSO to work, you need to establish a link relationship between an Azure AD user and the related user in Appraisd.

To configure and test Azure AD SSO with Appraisd, complete the following building blocks:

1. **[Configure Azure AD SSO](#configure-azure-ad-sso)** to enable your users to use this feature.
2. **[Configure Appraisd](#configure-appraisd)** to configure the SSO settings on application side.
3. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** to test Azure AD single sign-on with B. Simon.
4. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** to enable B. Simon to use Azure AD single sign-on.
5. **[Create Appraisd test user](#create-appraisd-test-user)** to have a counterpart of B. Simon in Appraisd that is linked to the Azure AD representation of user.
6. **[Test SSO](#test-sso)** to verify whether the configuration works.

### Configure Azure AD SSO

Follow these steps to enable Azure AD SSO in the Azure portal.

1. In the [Azure portal](https://portal.azure.com/), on the **Appraisd** application integration page, find the **Manage** section and select **Single sign-on**.
1. On the **Select a Single sign-on method** page, select **SAML**.
1. On the **Set up Single Sign-On with SAML** page, click the edit/pen icon for **Basic SAML Configuration** to edit the settings.

   ![Edit Basic SAML Configuration](common/edit-urls.png)

4. On the **Basic SAML Configuration** section, the application is pre-configured and the necessary URLs are already pre-populated with Azure. The user needs to save the configuration by clicking the Save button and perform the following steps:

    a. Click **Set additional URLs**.

	b. In the **Relay State** text box, type a URL: `<TENANTCODE>`

	c. If you wish to configure the application in **SP** initiated mode, in the **Sign-on URL** text box, type a URL using the following pattern:
    `https://app.appraisd.com/saml/<TENANTCODE>`

    > [!NOTE]
	> You get the actual Sign-on URL and Relay State value on the Appraisd SSO Configuration page which is explained later in the tutorial.

1. Appraisd application expects the SAML assertions in a specific format, which requires you to add custom attribute mappings to your SAML token attributes configuration. The following screenshot shows the list of default attributes, where as **nameidentifier** is mapped with **user.userprincipalname**. Appraisd application expects **nameidentifier** to be mapped with **user.mail**, so you need to edit the attribute mapping by clicking on **Edit** icon and change the attribute mapping.

	![Screenshot shows the User Attributes pane with the edit icon highlighted.](common/edit-attribute.png)

1. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, find **Certificate (Base64)** and select **Download** to download the certificate and save it on your computer.

   ![The Certificate download link](common/certificatebase64.png)

1. On the **Set up Appraisd** section, copy the appropriate URL(s) based on your requirement.

   ![Copy configuration URLs](common/copy-configuration-urls.png)

### Configure Appraisd

1. To automate the configuration within Appraisd, you need to install **My Apps Secure Sign-in browser extension** by clicking **Install the extension**.

	![My apps extension](common/install-myappssecure-extension.png)

2. After adding extension to the browser, click on **Setup Appraisd** will direct you to the Appraisd application. From there, provide the admin credentials to sign into Appraisd. The browser extension will automatically configure the application for you and automate steps 3-7.

	![Setup configuration](common/setup-sso.png)

3. If you want to setup Appraisd manually, open a new web browser window and sign into your Appraisd company site as an administrator and perform the following steps:

4. On the top right of the page, click on **Settings** icon, then navigate to **Configuration**.

	![Screenshot shows the Configuration link called out.](./media/appraisd-tutorial/tutorial_appraisd_sett.png)

5. From the Left side of menu, click on **SAML single sign-on**.

	![Screenshot shows the Configuration options with the SAML single sign-on option highlighted.](./media/appraisd-tutorial/tutorial_appraisd_single.png)

6. On the **SAML 2.0 Single Sign-On configuration** page, perform the following steps:

	![Screenshot shows the SAML 2.0 Single Sign-On configuration page where you can edit the Default Relay State and Service-initiated login U R L.](./media/appraisd-tutorial/tutorial_appraisd_saml.png)

	a. Copy the **Default Relay State** value and paste it in **Relay State** textbox in **Basic SAML Configuration** on Azure portal.

	b. Copy the **Service-initiated login URL** value and paste it in **Sign-on URL** textbox in **Basic SAML Configuration** on Azure portal.

7. Scroll down the same page under **Identifying users**, perform the following steps:

	![Screenshot shows Identifying users where you can enter values from this step.](./media/appraisd-tutorial/tutorial_appraisd_identifying.png)

	a. In the **Identity Provider Single Sign-On URL** textbox, paste the value of **Login URL**, which you have copied from the Azure portal and click **Save**.

	b. In the **Identity Provider Issuer URL** textbox, paste the value of **Azure AD Identifier**, which you have copied from the Azure portal and click **Save**.

	c. In Notepad, open the base-64 encoded certificate that you downloaded from the Azure portal, copy its content, and then paste it into the **X.509 Certificate** box and click **Save**.

### Create an Azure AD test user

In this section, you'll create a test user in the Azure portal called B. Simon.

1. From the left pane in the Azure portal, select **Azure Active Directory**, select **Users**, and then select **All users**.
1. Select **New user** at the top of the screen.
1. In the **User** properties, follow these steps:
   1. In the **Name** field, enter `B. Simon`.  
   1. In the **User name** field, enter the username@companydomain.extension. For example, `B. Simon@contoso.com`.
   1. Select the **Show password** check box, and then write down the value that's displayed in the **Password** box.
   1. Click **Create**.

### Assign the Azure AD test user

In this section, you'll enable B. Simon to use Azure single sign-on by granting access to Appraisd.

1. In the Azure portal, select **Enterprise Applications**, and then select **All applications**.
1. In the applications list, select **Appraisd**.
1. In the app's overview page, find the **Manage** section and select **Users and groups**.

   ![The "Users and groups" link](common/users-groups-blade.png)

1. Select **Add user**, then select **Users and groups** in the **Add Assignment** dialog.

	![The Add User link](common/add-assign-user.png)

1. In the **Users and groups** dialog, select **B. Simon** from the Users list, then click the **Select** button at the bottom of the screen.
1. If you're expecting any role value in the SAML assertion, in the **Select Role** dialog, select the appropriate role for the user from the list and then click the **Select** button at the bottom of the screen.
1. In the **Add Assignment** dialog, click the **Assign** button.

### Create Appraisd test user

To enable Azure AD users sign in to Appraisd, they must be provisioned into Appraisd. In Appraisd, provisioning is a manual task.

**To provision a user account, perform the following steps:**

1. Sign in to Appraisd as a Security Administrator.

2. On the top right of the page, click on **Settings** icon, then navigate to **Administration centre**.

	![Screenshot shows the Settings options where you can select Administration centre.](./media/appraisd-tutorial/tutorial_appraisd_admin.png)

3. In the toolbar at the top of the page, click **People**, then navigate to **Add a new user**.

	![Screenshot shows the Appraisd page with People and Add a new user called out.](./media/appraisd-tutorial/tutorial_appraisd_user.png)

4. On the **Add a new user** page, perform the following steps:

	![Screenshot shows the Add a new user page.](./media/appraisd-tutorial/tutorial_appraisd_newuser.png)

	a. In **First name** text box, enter the first name of user like **Britta**.

	b. In **Last name** text box, enter the last name of user like **simon**.

	c. In **Email** text box, enter the email of user like `B. Simon@contoso.com`.

	d. Click **Add user**.

### Test SSO

When you select the Appraisd tile in the Access Panel, you should be automatically signed in to the Appraisd for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://docs.microsoft.com/azure/active-directory/active-directory-saas-access-panel-introduction).

## Additional Resources

- [List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-saas-tutorial-list)

- [What is application access and single sign-on with Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-appssoaccess-whatis)

- [What is Conditional Access in Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)
