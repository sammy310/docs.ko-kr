---
title: .NET에서 사용자 지정 구성 공급자 구현
description: .NET 애플리케이션에서 사용자 지정 구성 공급자를 구현하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 12/04/2020
ms.topic: how-to
ms.openlocfilehash: 22e46b7df8b02421633d6be251d990879baa8b2b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "102402108"
---
# <a name="implement-a-custom-configuration-provider-in-net"></a><span data-ttu-id="6bb43-103">.NET에서 사용자 지정 구성 공급자 구현</span><span class="sxs-lookup"><span data-stu-id="6bb43-103">Implement a custom configuration provider in .NET</span></span>

<span data-ttu-id="6bb43-104">JSON, XML 및 INI 파일과 같은 일반적인 구성 소스에 사용할 수 있는 여러 [구성 공급자](configuration-providers.md)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-104">There are many [configuration providers](configuration-providers.md) available for common configuration sources such as JSON, XML, and INI files.</span></span> <span data-ttu-id="6bb43-105">사용 가능한 공급자 중 하나가 애플리케이션 요구 사항에 맞지 않는 경우 사용자 지정 구성 공급자를 구현해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-105">You may need to implement a custom configuration provider when one of the available providers doesn't suit your application needs.</span></span> <span data-ttu-id="6bb43-106">이 문서에서는 데이터베이스를 구성 소스로 사용하는 사용자 지정 구성 공급자를 구현하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-106">In this article, you'll learn how to implement a custom configuration provider that relies on a database as its configuration source.</span></span>

## <a name="custom-configuration-provider"></a><span data-ttu-id="6bb43-107">사용자 지정 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="6bb43-107">Custom configuration provider</span></span>

<span data-ttu-id="6bb43-108">샘플 앱에서는 [EF(Entity Framework) Core](/ef/core)를 사용하여 데이터베이스에서 구성 키-값 쌍을 읽는 기본 구성 공급자를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-108">The sample app demonstrates how to create a basic configuration provider that reads configuration key-value pairs from a database using [Entity Framework (EF) Core](/ef/core).</span></span>

<span data-ttu-id="6bb43-109">이 공급자의 특징은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-109">The provider has the following characteristics:</span></span>

- <span data-ttu-id="6bb43-110">데모용으로 EF 메모리 내 데이터베이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-110">The EF in-memory database is used for demonstration purposes.</span></span> <span data-ttu-id="6bb43-111">연결 문자열이 필요한 데이터베이스를 사용하려면 보조 `ConfigurationBuilder`를 구현하여 다른 구성 공급자에서 연결 문자열을 제공하세요.</span><span class="sxs-lookup"><span data-stu-id="6bb43-111">To use a database that requires a connection string, implement a secondary `ConfigurationBuilder` to supply the connection string from another configuration provider.</span></span>
- <span data-ttu-id="6bb43-112">이 공급자는 시작 시 데이터베이스 테이블을 구성으로 읽어 들입니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-112">The provider reads a database table into configuration at startup.</span></span> <span data-ttu-id="6bb43-113">이 공급자는 키별 기준으로 데이터베이스를 쿼리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-113">The provider doesn't query the database on a per-key basis.</span></span>
- <span data-ttu-id="6bb43-114">변경 시 다시 로드가 구현되지 않으므로 앱 시작 후 데이터베이스를 업데이트해도 앱 구성에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-114">Reload-on-change isn't implemented, so updating the database after the app starts has no effect on the app's configuration.</span></span>

<span data-ttu-id="6bb43-115">데이터베이스에 구성 값을 저장하는 `Settings` 레코드 형식 엔터티를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-115">Define a `Settings` record type entity for storing configuration values in the database.</span></span> <span data-ttu-id="6bb43-116">예를 들어 *Models* 폴더에 *Settings.cs* 파일을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-116">For example, you could add a *Settings.cs* file in your *Models* folder:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Models/Settings.cs":::

<span data-ttu-id="6bb43-117">레코드 형식에 관한 자세한 내용은 [C# 9의 레코드 형식](../../csharp/whats-new/csharp-9.md#record-types)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bb43-117">For information on record types, see [Record types in C# 9](../../csharp/whats-new/csharp-9.md#record-types).</span></span>

<span data-ttu-id="6bb43-118">구성된 값을 저장 및 액세스하는 `EntityConfigurationContext`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-118">Add an `EntityConfigurationContext` to store and access the configured values.</span></span>

<span data-ttu-id="6bb43-119">*Providers/EntityConfigurationContext.cs*:</span><span class="sxs-lookup"><span data-stu-id="6bb43-119">*Providers/EntityConfigurationContext.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationContext.cs":::

<span data-ttu-id="6bb43-120"><xref:Microsoft.Extensions.Configuration.IConfigurationSource>를 구현하는 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-120">Create a class that implements <xref:Microsoft.Extensions.Configuration.IConfigurationSource>.</span></span>

<span data-ttu-id="6bb43-121">*Providers/EntityConfigurationSource.cs*:</span><span class="sxs-lookup"><span data-stu-id="6bb43-121">*Providers/EntityConfigurationSource.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationSource.cs":::

<span data-ttu-id="6bb43-122"><xref:Microsoft.Extensions.Configuration.ConfigurationProvider>에서 상속하여 사용자 지정 구성 공급자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-122">Create the custom configuration provider by inheriting from <xref:Microsoft.Extensions.Configuration.ConfigurationProvider>.</span></span> <span data-ttu-id="6bb43-123">구성 공급자는 비어 있는 데이터베이스를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-123">The configuration provider initializes the database when it's empty.</span></span> <span data-ttu-id="6bb43-124">구성 키는 대/소문자를 구분하지 않으므로 데이터베이스를 초기화하는 데 사용되는 사전은 대/소문자를 구분하지 않는 비교자([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase))를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-124">Since configuration keys are case-insensitive, the dictionary used to initialize the database is created with the case-insensitive comparer ([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).</span></span>

<span data-ttu-id="6bb43-125">*Providers/EntityConfigurationProvider.cs*:</span><span class="sxs-lookup"><span data-stu-id="6bb43-125">*Providers/EntityConfigurationProvider.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationProvider.cs":::

<span data-ttu-id="6bb43-126">`AddEntityConfiguration` 확장 메서드를 사용하여 구성 소스를 <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> 인스턴스에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-126">An `AddEntityConfiguration` extension method permits adding the configuration source to a <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> instance.</span></span>

<span data-ttu-id="6bb43-127">*Extensions/ConfigurationBuilderExtensions.cs*:</span><span class="sxs-lookup"><span data-stu-id="6bb43-127">*Extensions/ConfigurationBuilderExtensions.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Extensions/ConfigurationBuilderExtensions.cs":::

<span data-ttu-id="6bb43-128">다음 코드는 *Program.cs* 에서 사용자 지정 `EntityConfigurationProvider`를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bb43-128">The following code shows how to use the custom `EntityConfigurationProvider` in *Program.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Program.cs" highlight="27-28":::

## <a name="see-also"></a><span data-ttu-id="6bb43-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bb43-129">See also</span></span>

- [<span data-ttu-id="6bb43-130">.NET의 구성</span><span class="sxs-lookup"><span data-stu-id="6bb43-130">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="6bb43-131">.NET의 구성 공급자</span><span class="sxs-lookup"><span data-stu-id="6bb43-131">Configuration providers in .NET</span></span>](configuration-providers.md)
