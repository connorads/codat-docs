---
title: "QuickBooks Desktop requirements"
description: "Software, hardware, environment and network requirements and configurations that support the connector"
sidebar_label: Requirements

supported configurations?

---

## Supported versions

Codat follows <a className="external" href="https://quickbooks.intuit.com/learn-support/en-us/help-article/feature-preferences/quickbooks-desktop-service-discontinuation-policy/L17cXxlie_US_en_US" target="_blank">Intuit’s service discontinuation policy</a> for QuickBooks Desktop (QBD) and fully supports the following versions, version tiers and special editions for Windows:

|     Versions                                                                                |     Tiers                                                                             |     Special editions                                                                                        |
|---------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| Latest three versions of:<br/> - QuickBooks Desktop (US)<br/> - QuickBooks Desktop (Canada) | Accountant<br/> Pro<br/> Pro Plus<br/> Premier<br/> Premier Plus<br/> Enterprise<br/> | Contractor<br/> Accountant<br/> Manufacturing<br/> Wholesale<br/> Professional Services<br/> Nonprofit<br/> |

Codat won't fix issues related to older versions of the software. If you experience compatibility issues with companies using older versions of the software, we advise you to upgrade to a supported version.

## Supported operating systems

Codat's web connector is compatible with QBD running on Windows 10 or Windows 11 with the latest service pack(s) installed.

We know users have successfully run the connector on older versions of Windows. We don't officially support this due to Microsoft's withdrawal of support for these operating systems and can't guarantee the connector will behave as intended.

:::caution QuickBooks Desktop for Mac

Codat doesn't support QBD for Mac OS. Only the QBD for Windows versions listed above are supported.

:::

## Limitations

The following limitations apply when using the web connector: 

- If QuickBooks Desktop is open on the SMB user's machine, the open company file must be the same company file that's been configured for the connector.

- Only one instance of QBD can be open on a user's machine at a time.

- QBD performance may vary during the syncs. You can't open an instance of QBD while a program is syncing, and its interface may behave unexpectedly.

## Supported modes

The web connector works with QBD running in single-user or multi-user mode. In **single-user mode**, only one user can access the company file at a time. Another user trying to access the same file will see an error. In **multi-user mode**, multiple users are able to work on the same company file at the same time using different machines. 

## Supported environments

Our QuickBooks Desktop Connector is verified to work in single-tenant environments only, where a single Windows user is logged on to the computer used to access QuickBooks Desktop. 

Due to limitations of syncing with QBD, complications can occur when attempting to sync in multi-tenant environments. For example, if your company files are hosted on a different server to the one where you run and use QBD, you may see performance impact. To avoid this, you can install the web connector on this server, but you need to install QBD there as well. 

You may also encounter issues in a hosted environment where multiple users log in and use QBD simultaneously, although this depends on the exact setup. This does not apply to Rightworks hosted instances.

:::note Rightworks hosted instances

Rightworks hosted instances already have the web connector installed and support our integration as a result.  Outside of the Rightworks solution, we cannot guarantee the behavior of the connector in multi-tenant or hosted environments.

:::

## Hardware requirements

Ensure that the host machine meets <a href="https://quickbooks.intuit.com/learn-support/en-us/help-article/install-products/system-requirements-quickbooks-desktop-2022/L9664spDA_US_en_US" class="external" target="_blank">Intuit's recommended specification</a> for running QuickBooks Desktop.

If you have a large number of companies, or particularly large company files, you should pay special attention to the consumption of CPU, memory, disk, and network resources on the host machine and ensure there is sufficient headroom.

## Firewall rules

The QuickBooks Desktop connector communicates over port `443` to URLs hosted on `https://quickbooksdesktop.codat.io` in production.The user's local antivirus or firewall settings may prevent the download and running of the connector. 

If you experience problems with the connector transmitting data, add the following URLs to your firewall allowlist: 

```http
https://quickbooksdesktop.codat.io/
https://connectors.codat.io
```

---

## Read next

- Enable the SMB user to [install the connector](https://docs.codat.io/integrations/accounting/quickbooksdesktop/installing-the-quickbooks-connector) once you complete the prerequisites. 