---
title: Azure Key Vault를 사용하여 프로덕션 시 비밀 보호
description: .NET 마이크로 서비스 및 웹 애플리케이션의 보안 - Azure Key Vault는 관리자가 완전히 제어하는 애플리케이션 비밀을 처리하는 뛰어난 방법입니다. 개발자가 처리하지 않고도 관리자가 개발 값을 할당하고 철회할 수도 있습니다.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 94243468b35e2db9818ae9afacd5beec0a12075e
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604621"
---
# <a name="use-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="f0b6a-104">Azure Key Vault를 사용하여 프로덕션 시 비밀 보호</span><span class="sxs-lookup"><span data-stu-id="f0b6a-104">Use Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="f0b6a-105">환경 변수로 저장되거나 비밀 관리자 도구로 저장된 비밀은 여전히 로컬로 저장되고 컴퓨터에서 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="f0b6a-106">비밀을 저장하기 위한 더 안전한 옵션은 키 및 비밀을 저장하기 위해 안전한 중앙 위치를 제공하는 [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)입니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="f0b6a-107">**Azure.Extensions.AspNetCore.Configuration.Secrets** 패키지를 통해 ASP.NET Core 애플리케이션에서 Azure Key Vault의 구성 정보를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-107">The **Azure.Extensions.AspNetCore.Configuration.Secrets** package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="f0b6a-108">Azure Key Vault에서 암호 사용을 시작하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

1. <span data-ttu-id="f0b6a-109">애플리케이션을 Azure AD 애플리케이션으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-109">Register your application as an Azure AD application.</span></span> <span data-ttu-id="f0b6a-110">(키 자격 증명 모음에 대한 액세스는 Azure AD에 의해 관리됩니다.) Azure 관리 포털을 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>\

   <span data-ttu-id="f0b6a-111">또는 암호나 클라이언트 암호 대신 인증서를 사용하여 애플리케이션을 인증하려는 경우 [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzADApplication](/powershell/module/az.resources/new-azadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="f0b6a-112">Azure Key Vault로 등록하는 인증서는 공개 키만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="f0b6a-113">애플리케이션은 프라이빗 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-113">Your application will use the private key.</span></span>

2. <span data-ttu-id="f0b6a-114">새 서비스 주체를 만들어 등록된 애플리케이션에 키 자격 증명 모음에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-114">Give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="f0b6a-115">다음 PowerShell 명령을 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-115">You can do this using the following PowerShell commands:</span></span>

   ```powershell
   $sp = New-AzADServicePrincipal -ApplicationId "<Application ID guid>"
   Set-AzKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
   ```

3. <span data-ttu-id="f0b6a-116"><xref:Microsoft.Extensions.Configuration.IConfigurationRoot> 인스턴스를 만들 때 AzureKeyVaultConfigurationExtensions.AddAzureKeyVault 확장 메서드를 호출하여 애플리케이션에 구성 소스로 키 자격 증명 모음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-116">Include the key vault as a configuration source in your application by calling the AzureKeyVaultConfigurationExtensions.AddAzureKeyVault extension method when you create an <xref:Microsoft.Extensions.Configuration.IConfigurationRoot> instance.</span></span>

<span data-ttu-id="f0b6a-117">`AddAzureKeyVault`를 호출하려면 이전 단계에서 등록되었으며 키 자격 증명 모음에 대한 액세스 권한이 부여된 애플리케이션 ID가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-117">Note that calling `AddAzureKeyVault` requires the application ID that was registered and given access to the key vault in the previous steps.</span></span> <span data-ttu-id="f0b6a-118">또는 Azure CLI 명령 `az login`을 먼저 실행한 후 클라이언트 대신 DefaultAzureCredential을 사용하는 `AddAzureKeyVault`의 오버로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-118">Or you can firstly running the Azure CLI command: `az login`, then using an overload of `AddAzureKeyVault` that takes a DefaultAzureCredential in place of the client.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f0b6a-119">Azure Key Vault를 마지막 구성 공급자로 등록하는 것이 좋습니다. 이렇게 하면 이전 공급자의 구성 값을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0b6a-119">We recommend that you register Azure Key Vault as the last configuration provider, so it can override configuration values from previous providers.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0b6a-120">추가 자료</span><span class="sxs-lookup"><span data-stu-id="f0b6a-120">Additional resources</span></span>

- <span data-ttu-id="f0b6a-121">**Azure Key Vault를 사용하여 애플리케이션 비밀 보호** </span><span class="sxs-lookup"><span data-stu-id="f0b6a-121">**Using Azure Key Vault to protect application secrets** </span></span>\
  [https://docs.microsoft.com/azure/architecture/multitenant-identity](/azure/architecture/multitenant-identity)

- <span data-ttu-id="f0b6a-122">**개발 중 안전한 앱 비밀 스토리지** </span><span class="sxs-lookup"><span data-stu-id="f0b6a-122">**Safe storage of app secrets during development** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/app-secrets](/aspnet/core/security/app-secrets)

- <span data-ttu-id="f0b6a-123">**데이터 보호 구성** </span><span class="sxs-lookup"><span data-stu-id="f0b6a-123">**Configuring data protection** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview](/aspnet/core/security/data-protection/configuration/overview)

- <span data-ttu-id="f0b6a-124">**ASP.NET Core에서 데이터 보호 키 관리 및 수명** </span><span class="sxs-lookup"><span data-stu-id="f0b6a-124">**Data Protection key management and lifetime in ASP.NET Core** </span></span>\
  [https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings](/aspnet/core/security/data-protection/configuration/default-settings)

>[!div class="step-by-step"]
><span data-ttu-id="f0b6a-125">[이전](developer-app-secrets-storage.md)
>[다음](../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="f0b6a-125">[Previous](developer-app-secrets-storage.md)
[Next](../key-takeaways.md)</span></span>
