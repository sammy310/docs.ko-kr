---
title: .NET의 구성
description: 구성 API를 사용하여 .NET 애플리케이션을 구성하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.topic: overview
ms.openlocfilehash: 5955e46c2f5acb6776ada4e3fd6a65507d3faa1f
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "102402111"
---
# <a name="configuration-in-net"></a><span data-ttu-id="e2298-103">.NET의 구성</span><span class="sxs-lookup"><span data-stu-id="e2298-103">Configuration in .NET</span></span>

<span data-ttu-id="e2298-104">.NET의 구성은 하나 이상의 [구성 공급자](#configuration-providers)를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-104">Configuration in .NET is performed using one or more [configuration providers](#configuration-providers).</span></span> <span data-ttu-id="e2298-105">구성 공급자는 다음과 같은 다양한 구성 소스를 사용하여 키-값 쌍에서 구성 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-105">Configuration providers read configuration data from key-value pairs using a variety of configuration sources:</span></span>

- <span data-ttu-id="e2298-106">설정 파일(예: *appsettings.json*)</span><span class="sxs-lookup"><span data-stu-id="e2298-106">Settings files, such as *appsettings.json*</span></span>
- <span data-ttu-id="e2298-107">환경 변수</span><span class="sxs-lookup"><span data-stu-id="e2298-107">Environment variables</span></span>
- [<span data-ttu-id="e2298-108">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e2298-108">Azure Key Vault</span></span>](/azure/key-vault/general/overview)
- [<span data-ttu-id="e2298-109">Azure App Configuration</span><span class="sxs-lookup"><span data-stu-id="e2298-109">Azure App Configuration</span></span>](/azure/azure-app-configuration/overview)
- <span data-ttu-id="e2298-110">명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="e2298-110">Command-line arguments</span></span>
- <span data-ttu-id="e2298-111">설치되거나 만들어진 사용자 지정 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-111">Custom providers, installed or created</span></span>
- <span data-ttu-id="e2298-112">디렉터리 파일</span><span class="sxs-lookup"><span data-stu-id="e2298-112">Directory files</span></span>
- <span data-ttu-id="e2298-113">메모리 내 .NET 개체</span><span class="sxs-lookup"><span data-stu-id="e2298-113">In-memory .NET objects</span></span>

## <a name="configure-console-apps"></a><span data-ttu-id="e2298-114">콘솔 앱 구성</span><span class="sxs-lookup"><span data-stu-id="e2298-114">Configure console apps</span></span>

<span data-ttu-id="e2298-115">[dotnet new](../tools/dotnet-new.md) 또는 Visual Studio를 사용하여 만든 새 .NET 콘솔 애플리케이션은 기본적으로 구성 기능을 공개하지 ‘않습니다’.</span><span class="sxs-lookup"><span data-stu-id="e2298-115">New .NET console applications created using [dotnet new](../tools/dotnet-new.md) or Visual Studio by default *do not* expose configuration capabilities.</span></span> <span data-ttu-id="e2298-116">새 .NET 콘솔 애플리케이션에서 구성을 추가하려면 `Microsoft.Extensions.Hosting`에 [패키지 참조를 추가](../tools/dotnet-add-package.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-116">To add configuration in a new .NET console application, [add a package reference](../tools/dotnet-add-package.md) to `Microsoft.Extensions.Hosting`.</span></span> <span data-ttu-id="e2298-117">다음 코드와 일치하도록 *Program.cs* 파일을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-117">Modify the *Program.cs* file to match the following code:</span></span>

:::code language="csharp" source="snippets/configuration/console/Program.cs" highlight="18":::

<span data-ttu-id="e2298-118"><xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])?displayProperty=nameWithType> 메서드는 다음 순서로 앱의 기본 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-118">The <xref:Microsoft.Extensions.Hosting.Host.CreateDefaultBuilder(System.String[])?displayProperty=nameWithType> method provides default configuration for the app in the following order:</span></span>

1. <span data-ttu-id="e2298-119">[ChainedConfigurationProvider](xref:Microsoft.Extensions.Configuration.ChainedConfigurationSource): 기존 `IConfiguration`을 소스로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-119">[ChainedConfigurationProvider](xref:Microsoft.Extensions.Configuration.ChainedConfigurationSource) : Adds an existing `IConfiguration` as a source.</span></span>
1. <span data-ttu-id="e2298-120">[JSON 구성 공급자](configuration-providers.md#file-configuration-provider)를 사용하는 *appsettings.json*</span><span class="sxs-lookup"><span data-stu-id="e2298-120">*appsettings.json* using the [JSON configuration provider](configuration-providers.md#file-configuration-provider).</span></span>
1. <span data-ttu-id="e2298-121">[JSON 구성 공급자](configuration-providers.md#file-configuration-provider)를 사용하는 *appsettings.* `Environment` *.json*.</span><span class="sxs-lookup"><span data-stu-id="e2298-121">*appsettings.*`Environment`*.json* using the [JSON configuration provider](configuration-providers.md#file-configuration-provider).</span></span> <span data-ttu-id="e2298-122">예: *appsettings*.***Production\*\*_._json* 및 *appsettings*.\*\*\*Development** _._json\*.</span><span class="sxs-lookup"><span data-stu-id="e2298-122">For example, *appsettings*.***Production\*\*_._json* and *appsettings*.\*\*\*Development** _._json\*.</span></span>
1. <span data-ttu-id="e2298-123">앱이 `Development` 환경에서 실행되는 경우 앱 비밀</span><span class="sxs-lookup"><span data-stu-id="e2298-123">App secrets when the app runs in the `Development` environment.</span></span>
1. <span data-ttu-id="e2298-124">[환경 변수 구성 공급자](configuration-providers.md#environment-variable-configuration-provider)를 사용하는 환경 변수</span><span class="sxs-lookup"><span data-stu-id="e2298-124">Environment variables using the [Environment Variables configuration provider](configuration-providers.md#environment-variable-configuration-provider).</span></span>
1. <span data-ttu-id="e2298-125">[명령줄 구성 공급자](configuration-providers.md#command-line-configuration-provider)를 사용하는 명령줄 인수</span><span class="sxs-lookup"><span data-stu-id="e2298-125">Command-line arguments using the [Command-line configuration provider](configuration-providers.md#command-line-configuration-provider).</span></span>

<span data-ttu-id="e2298-126">나중에 추가된 구성 공급자는 이전 키 설정을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-126">Configuration providers that are added later override previous key settings.</span></span> <span data-ttu-id="e2298-127">예를 들어 `SomeKey`가 *appsettings.json* 과 환경 모두에서 설정된 경우 환경 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-127">For example, if `SomeKey` is set in both *appsettings.json* and the environment, the environment value is used.</span></span> <span data-ttu-id="e2298-128">[명령줄 구성 공급자](configuration-providers.md#command-line-configuration-provider)는 기본 구성 공급자를 사용하여 다른 모든 공급자를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-128">Using the default configuration providers, the [Command-line configuration provider](configuration-providers.md#command-line-configuration-provider) overrides all other providers.</span></span>

### <a name="binding"></a><span data-ttu-id="e2298-129">바인딩</span><span class="sxs-lookup"><span data-stu-id="e2298-129">Binding</span></span>

<span data-ttu-id="e2298-130">.NET의 구성에 관련된 주요 이점 중 하나는 구성 값을 .NET 개체 인스턴스에 바인딩하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-130">One of the key advantages to configuration in .NET is the ability to bind configuration values to instances of .NET objects.</span></span> <span data-ttu-id="e2298-131">예를 들어, JSON 구성 공급자는 *appsettings.json* 파일을 .NET 개체에 매핑하는 데 사용될 수 있으며 종속성 주입과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-131">For example, the JSON configuration provider can be used to map *appsettings.json* files to .NET objects and is used with dependency injection.</span></span> <span data-ttu-id="e2298-132">이를 통해 옵션 패턴을 사용할 수 있으며 옵션 패턴은 클래스를 사용하여 관련 설정 그룹에 대한 강력한 형식의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-132">This enables the options pattern, the options pattern uses classes to provide strongly typed access to groups of related settings.</span></span>

## <a name="configuration-providers"></a><span data-ttu-id="e2298-133">구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-133">Configuration providers</span></span>

<span data-ttu-id="e2298-134">다음 표에서는 .NET Core 앱에서 사용할 수 있는 구성 공급자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-134">The following table shows the configuration providers available to .NET Core apps.</span></span>

| <span data-ttu-id="e2298-135">공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-135">Provider</span></span>                                                                                                               | <span data-ttu-id="e2298-136">다음에서 구성 제공</span><span class="sxs-lookup"><span data-stu-id="e2298-136">Provides configuration from</span></span>        |
|------------------------------------------------------------------------------------------------------------------------|------------------------------------|
| [<span data-ttu-id="e2298-137">Azure 앱 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-137">Azure App configuration provider</span></span>](/azure/azure-app-configuration/quickstart-aspnet-core-app)                          | <span data-ttu-id="e2298-138">Azure App Configuration</span><span class="sxs-lookup"><span data-stu-id="e2298-138">Azure App Configuration</span></span>            |
| [<span data-ttu-id="e2298-139">Azure Key Vault 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-139">Azure Key Vault configuration provider</span></span>](/azure/key-vault/general/tutorial-net-virtual-machine)                        | <span data-ttu-id="e2298-140">Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="e2298-140">Azure Key Vault</span></span>                    |
| [<span data-ttu-id="e2298-141">명령줄 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-141">Command-line configuration provider</span></span>](configuration-providers.md#command-line-configuration-provider)                  | <span data-ttu-id="e2298-142">명령줄 매개 변수</span><span class="sxs-lookup"><span data-stu-id="e2298-142">Command-line parameters</span></span>            |
| [<span data-ttu-id="e2298-143">사용자 지정 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-143">Custom configuration provider</span></span>](custom-configuration-provider.md)                                                      | <span data-ttu-id="e2298-144">사용자 지정 소스</span><span class="sxs-lookup"><span data-stu-id="e2298-144">Custom source</span></span>                      |
| [<span data-ttu-id="e2298-145">환경 변수 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-145">Environment Variables configuration provider</span></span>](configuration-providers.md#environment-variable-configuration-provider) | <span data-ttu-id="e2298-146">환경 변수</span><span class="sxs-lookup"><span data-stu-id="e2298-146">Environment variables</span></span>              |
| [<span data-ttu-id="e2298-147">파일 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-147">File configuration provider</span></span>](configuration-providers.md#file-configuration-provider)                                  | <span data-ttu-id="e2298-148">JSON, XML, INI 파일</span><span class="sxs-lookup"><span data-stu-id="e2298-148">JSON, XML, and INI files</span></span>           |
| [<span data-ttu-id="e2298-149">파일별 키 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-149">Key-per-file configuration provider</span></span>](configuration-providers.md#key-per-file-configuration-provider)                  | <span data-ttu-id="e2298-150">디렉터리 파일</span><span class="sxs-lookup"><span data-stu-id="e2298-150">Directory files</span></span>                    |
| [<span data-ttu-id="e2298-151">메모리 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-151">Memory configuration provider</span></span>](configuration-providers.md#memory-configuration-provider)                              | <span data-ttu-id="e2298-152">메모리 내 컬렉션</span><span class="sxs-lookup"><span data-stu-id="e2298-152">In-memory collections</span></span>              |
| [<span data-ttu-id="e2298-153">앱 비밀(비밀 관리자)</span><span class="sxs-lookup"><span data-stu-id="e2298-153">App secrets (Secret Manager)</span></span>](/aspnet/core/security/app-secrets)                                                      | <span data-ttu-id="e2298-154">사용자 프로필 디렉터리의 파일</span><span class="sxs-lookup"><span data-stu-id="e2298-154">File in the user profile directory</span></span> |

<span data-ttu-id="e2298-155">다양한 구성 공급자에 관한 자세한 내용은 [.NET의 구성 공급자](configuration-providers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2298-155">For more information on various configuration providers, see [Configuration providers in .NET](configuration-providers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2298-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e2298-156">See also</span></span>

- [<span data-ttu-id="e2298-157">.NET의 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="e2298-157">Configuration providers in .NET</span></span>](configuration-providers.md)
- [<span data-ttu-id="e2298-158">사용자 지정 구성 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="e2298-158">Implement a custom configuration provider</span></span>](custom-configuration-provider.md)
- <span data-ttu-id="e2298-159">구성 버그는 [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) 리포지토리에서 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2298-159">Configuration bugs should be created in the [github.com/dotnet/extensions](https://github.com/dotnet/extensions/issues) repo</span></span>
