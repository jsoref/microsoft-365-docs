---
title: Admin review for user reported messages
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
ms.collection:
  - m365-security
  - tier2
ms.custom:
description: Admins can learn how to review messages that were reported by users and give them feedback.
ms.subservice: mdo
ms.service: microsoft-365-security
search.appverid: met150
ms.date: 5/31/2023
---

# Admin review for user reported messages

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Applies to**
- [Exchange Online Protection](eop-about.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can send templated messages back to users after an admin has reviewed their reported messages. You can customize the templates for your organization and for the admin verdict.

The feature is designed to give feedback to your users but doesn't change the verdicts of messages in the system. To help Microsoft update and improve its filters, you need to submit messages for analysis using [Admin submission](submissions-admin.md).

Admins can mark messages and notify users of review results only if the user reported the message as a [false positives or false negatives](submissions-outlook-report-messages.md).

## What do you need to know before you begin?

- You open the Microsoft 365 Defender portal at <https://security.microsoft.com>. To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>. To go directly to the **User reported** page, use <https://security.microsoft.com/reportsubmission?viewid=user>.

- You need to be assigned permissions before you can do the procedures in this article. You have the following options:
  - [Email & collaboration RBAC in the Microsoft 365 Defender portal](mdo-portal-permissions.md): Membership in the **Organization Management** or **Security Administrator** role groups.
  - [Exchange Online RBAC](/exchange/permissions-exo/permissions-exo): Membership in the **Organization Management** role group.
  - [Azure AD RBAC](../../admin/add-users/about-admin-roles.md): Membership in the **Global Administrator** or **Security Administrator** roles gives users the required permissions _and_ permissions for other features in Microsoft 365.

- You need access to Exchange Online PowerShell. If your account doesn't have access to Exchange Online PowerShell, you get the following error: *Specify an email address in your domain*. For more information about enabling or disabling access to Exchange Online PowerShell, see the following articles:
  - [Enable or disable access to Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) ([until October 2023](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecation-of-client-access-rules-in-exchange-online/ba-p/3638563))

## Notify users from within the portal

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>, go to the **Submissions** page at **Email & collaboration** \> **Submissions** \> **User reported** tab. Or, to go directly to the **User reported** tab, use <https://security.microsoft.com/reportsubmission?viewid=user>.

2. On the **User reported** tab, find and select the message, select **Mark as and notify**, and then select one of the following values from the dropdown list:
   - **No threats found**
   - **Phishing**
   - **Spam**

   :::image type="content" source="../../media/admin-review-send-message-from-portal.png" alt-text="The page displaying the user-reported messages" lightbox="../../media/admin-review-send-message-from-portal.png":::

The reported message is marked as **No threats found**, **Phishing**, or **Spam**, and an email is automatically sent to notify the user who reported the message.

## Customize the messages used to notify users

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>, go to the **User reported** page at **Settings** \> **Email & collaboration** \> **User reported** tab. Or, to go directly to the **User reported** page, use <https://security.microsoft.com/securitysettings/userSubmission>.

2. On the **User reported** page, verify that the toggle at the top of the page is :::image type="icon" source="../../media/scc-toggle-on.png" border="false"::: **On**.

3. Find the **Email sent to user after admin review** section and configure one or more of the following settings:

   - **Specify an Office 365 mailbox to send email notifications from**: Select this option and enter the sender's email address in the box that appears.
   - **Replace the Microsoft logo with my company logo**: Select this option to replace the default Microsoft logo that's used in notifications. Before you do this step, you need to follow the instructions in [Customize the Microsoft 365 theme for your organization](../../admin/setup/customize-your-organization-theme.md) to upload your custom logo.
   - **Customize email notification messages**: Select this link to customize the email notification that's sent after an admin reviews and marks a reported message. In the **Customize admin review email notifications** flyout that appears, configure the following settings on the **Phishing**, **Junk** and **No threats found** tabs:
     - **Email box results text**: Enter the custom text to use.
       - **Footer** tab: The following options are available:
       - **Email footer text**: Enter the custom message footer text to use.

     When you're finished on the **Customize admin review email notifications** flyout, select **Confirm**.

   :::image type="content" source="../../media/admin-review-customize-message.png" alt-text="The Customize confirmation message page" lightbox="../../media/admin-review-customize-message.png":::

4. When you're finished on the **User reported** page, select **Save**. To clear these values, select **Restore** on the **User reported** page.
