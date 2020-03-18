---
title: 개발하는 동안 애플리케이션 비밀 저장
description: .NET 마이크로 서비스 및 웹 애플리케이션의 보안 - 암호, 연결 문자열 또는 API 키와 같은 애플리케이션 비밀을 소스 제어에 저장하지 마세요. ASP.NET Core에서 사용할 수 있는 옵션, 특히 “사용자 비밀”을 처리하는 방법을 이해하고 있어야 합니다.
author: mjrousos
ms.date: 01/30/2020
ms.openlocfilehash: 1ef2246746b9165f1564fa7be64ff7eb28eb1d32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77501792"
---
# <a name="store-application-secrets-safely-during-development"></a><span data-ttu-id="a0a08-103">개발 중에 애플리케이션 비밀을 안전하게 저장</span><span class="sxs-lookup"><span data-stu-id="a0a08-103">Store application secrets safely during development</span></span>

<span data-ttu-id="a0a08-104">보호된 리소스 및 기타 서비스에 연결하려면 ASP.NET Core 애플리케이션은 일반적으로 연결 문자열, 암호 또는 중요한 정보를 포함하는 다른 자격 증명을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-104">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="a0a08-105">이러한 정보의 중요한 부분을 *암호*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-105">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="a0a08-106">소스 코드에 비밀을 포함하지 않고 소스 제어에 비밀을 저장하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-106">It's a best practice to not include secrets in source code and making sure not to store secrets in source control.</span></span> <span data-ttu-id="a0a08-107">대신 ASP.NET Core 구성 모델을 사용하여 보다 안전한 위치에서 암호를 읽어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-107">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="a0a08-108">개인마다 다른 비밀 집합에 액세스해야 하기 때문에 프로덕션 리소스에 액세스할 때 사용되는 비밀과 개발 및 준비 리소스에 액세스할 때 사용되는 비밀을 분리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-108">You must separate the secrets for accessing development and staging resources from the ones used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="a0a08-109">개발 중에 사용되는 암호를 저장하는 일반적인 방법은 환경 변수에서 암호를 저장하거나 ASP.NET Core 암호 관리자 도구를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-109">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="a0a08-110">프로덕션 환경에 있는 보다 안전한 스토리지의 경우 마이크로 서비스는 Azure Key Vault에 암호를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-110">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="store-secrets-in-environment-variables"></a><span data-ttu-id="a0a08-111">환경 변수에 비밀 저장</span><span class="sxs-lookup"><span data-stu-id="a0a08-111">Store secrets in environment variables</span></span>

<span data-ttu-id="a0a08-112">소스 코드에서 암호를 유지하는 한 가지 방법은 개발자가 해당 개발 컴퓨터에서 [환경 변수](/aspnet/core/security/app-secrets#environment-variables)로 문자열 기반 암호를 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-112">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="a0a08-113">환경 변수를 사용하여 계층적 이름(예: 구성 섹션에서 중첩된 이름)으로 비밀을 저장하는 경우 해당 섹션의 전체 계층 구조를 콜론(:)으로 구분해서 포함하도록 변수의 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-113">When you use environment variables to store secrets with hierarchical names, such as the ones nested in configuration sections, you must name the variables to include the complete hierarchy of its sections, delimited with colons (:).</span></span>

<span data-ttu-id="a0a08-114">예를 들어 `Logging:LogLevel:Default` 환경 변수를 `Debug`로 설정하는 작업은 다음과 같은 JSON 파일의 구성 값에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-114">For example, setting an environment variable `Logging:LogLevel:Default` to `Debug` value would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="a0a08-115">환경 변수의 이러한 값에 액세스하려면 애플리케이션이 IConfigurationRoot 개체를 생성할 때 해당 ConfigurationBuilder에서 AddEnvironmentVariables를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-115">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="a0a08-116">대체로 환경 변수는 일반 텍스트로 저장됩니다. 따라서 환경 변수를 포함하는 머신 또는 프로세스가 손상된 경우 환경 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-116">Note that environment variables are commonly stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="store-secrets-with-the-aspnet-core-secret-manager"></a><span data-ttu-id="a0a08-117">ASP.NET Core 비밀 관리자를 사용하여 비밀 저장</span><span class="sxs-lookup"><span data-stu-id="a0a08-117">Store secrets with the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="a0a08-118">ASP.NET Core [암호 관리자](/aspnet/core/security/app-secrets#secret-manager) 도구는 **개발 도중** 소스 코드에서 암호를 유지하는 또 다른 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-118">The ASP.NET Core [Secret Manager](/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code **during development**.</span></span> <span data-ttu-id="a0a08-119">비밀 관리자 도구를 사용하려면 **Microsoft.Extensions.Configuration.SecretManager** 패키지를 프로젝트 파일에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-119">To use the Secret Manager tool, install the package **Microsoft.Extensions.Configuration.SecretManager** in your project file.</span></span> <span data-ttu-id="a0a08-120">해당 종속성이 표시되고 복원되면 `dotnet user-secrets` 명령을 사용하여 명령줄에서 비밀 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-120">Once that dependency is present and has been restored, the `dotnet user-secrets` command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="a0a08-121">이러한 암호는 소스 코드와 다르게 사용자의 프로필 디렉터리에 있는 JSON 파일에 저장됩니다(세부 정보는 운영 체제에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="a0a08-121">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="a0a08-122">비밀 관리자 도구에 의해 설정된 비밀은 비밀을 사용하는 프로젝트의 `UserSecretsId` 속성으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-122">Secrets set by the Secret Manager tool are organized by the `UserSecretsId` property of the project that's using the secrets.</span></span> <span data-ttu-id="a0a08-123">따라서 아래 코드 조각과 같이 프로젝트 파일에서 UserSecretsId 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-123">Therefore, you must be sure to set the UserSecretsId property in your project file, as shown in the snippet below.</span></span> <span data-ttu-id="a0a08-124">기본값은 Visual Studio에서 할당된 GUID이지만 컴퓨터에서 고유하기만 하면 실제 문자열은 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-124">The default value is a GUID assigned by Visual Studio, but the actual string is not important as long as it's unique in your computer.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="a0a08-125">애플리케이션에서 비밀 관리자를 통해 저장된 비밀을 사용하려면 ConfigurationBuilder 인스턴스에서 `AddUserSecrets<T>`를 호출하여 애플리케이션의 비밀을 해당 구성에 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-125">Using secrets stored with Secret Manager in an application is accomplished by calling `AddUserSecrets<T>` on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="a0a08-126">제네릭 매개 변수 T는 UserSecretId를 적용할 어셈블리의 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-126">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="a0a08-127">일반적으로 `AddUserSecrets<Startup>`을 사용해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-127">Usually using `AddUserSecrets<Startup>` is fine.</span></span>

<span data-ttu-id="a0a08-128">`AddUserSecrets<Startup>()`Program.cs`CreateDefaultBuilder`의 *메서드를 사용하는 경우 개발 환경의 기본 옵션에*이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0a08-128">The `AddUserSecrets<Startup>()` is included in the default options for the Development environment when using the `CreateDefaultBuilder` method in *Program.cs*.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a0a08-129">[이전](authorization-net-microservices-web-applications.md)
>[다음](azure-key-vault-protects-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="a0a08-129">[Previous](authorization-net-microservices-web-applications.md)
[Next](azure-key-vault-protects-secrets.md)</span></span>
