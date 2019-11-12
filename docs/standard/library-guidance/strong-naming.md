---
title: 강력한 이름 지정 및 .NET 라이브러리
description: .NET 라이브러리에 강력한 이름을 지정하는 모범 사례 권장 사항입니다.
author: jamesnk
ms.author: mairaw
ms.date: 10/16/2018
ms.openlocfilehash: 3e7cc9a3a1be05d8fcb02b34f7027126697d15d0
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73196976"
---
# <a name="strong-naming"></a><span data-ttu-id="f07fa-103">강력한 이름 지정</span><span class="sxs-lookup"><span data-stu-id="f07fa-103">Strong naming</span></span>

<span data-ttu-id="f07fa-104">강력한 이름 지정은 키를 사용해서 어셈블리에 서명하여 [강력한 이름의 어셈블리](../assembly/strong-named.md)를 생성하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-104">Strong naming refers to signing an assembly with a key, producing a [strong-named assembly](../assembly/strong-named.md).</span></span> <span data-ttu-id="f07fa-105">어셈블리에 강력한 이름을 지정하면 이름 및 어셈블리 버전 번호를 기준으로 고유 ID가 생성되어 어셈블리 충돌을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-105">When an assembly is strong-named, it creates a unique identity based on the name and assembly version number, and it can help prevent assembly conflicts.</span></span>

<span data-ttu-id="f07fa-106">강력한 이름 지정의 단점은 어셈블리에 강력한 이름이 지정되고 나면 Windows의 .NET Framework에서 어셈블리를 엄격하게 로드한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-106">The downside to strong naming is that the .NET Framework on Windows enables strict loading of assemblies once an assembly is strong named.</span></span> <span data-ttu-id="f07fa-107">강력한 이름의 어셈블리 참조는 어셈블리에서 참조하는 버전과 정확히 일치해야 하므로 개발자가 어셈블리를 사용할 때 [바인딩 리디렉션을 구성](../../framework/configure-apps/redirect-assembly-versions.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-107">A strong-named assembly reference must exactly match the version referenced by an assembly, forcing developers to [configure binding redirects](../../framework/configure-apps/redirect-assembly-versions.md) when using the assembly:</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly" publicKeyToken="32ab4ba45e0a69a1" culture="neutral" />
            <bindingRedirect oldVersion="1.0.0.0" newVersion="2.0.0.0"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

<span data-ttu-id="f07fa-108">.NET 개발자가 강력한 이름 지정에 대해 불만을 제기하는 경우 일반적으로 엄격한 어셈블리 로드와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-108">When .NET developers complain about strong naming, what they're usually complaining about is strict assembly loading.</span></span> <span data-ttu-id="f07fa-109">다행히, 이 문제는 .NET Framework에만 한정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-109">Fortunately, this issue is isolated to the .NET Framework.</span></span> <span data-ttu-id="f07fa-110">.NET Core, Xamarin, UWP 및 대부분의 다른 .NET 구현에서는 엄격한 어셈블리 로드가 필요하지 않으며 강력한 이름 지정의 주요 단점이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-110">.NET Core, Xamarin, UWP, and most other .NET implementations don't have strict assembly loading and removes the main downside of strong naming.</span></span>

<span data-ttu-id="f07fa-111">강력한 이름 지정의 한 가지 중요한 측면은 바이럴이란 것입니다. 강력한 이름의 어셈블리는 다른 강력한 이름의 어셈블리만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-111">One important aspect of strong naming is that it's viral: a strong named assembly can only reference other strong named assemblies.</span></span> <span data-ttu-id="f07fa-112">라이브러리에 강력한 이름을 지정하지 않은 경우, 강력한 이름 지정이 필요한 애플리케이션 또는 라이브러리를 빌드하는 개발자는 해당 라이브러리를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-112">If your library isn't strong named, then you have excluded developers who are building an application or library that needs strong naming from using it.</span></span>

<span data-ttu-id="f07fa-113">강력한 이름 지정의 혜택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-113">The benefits of strong naming are:</span></span>

1. <span data-ttu-id="f07fa-114">다른 강력한 이름의 어셈블리에서 어셈블리를 참조하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-114">The assembly can be referenced and used by other strong-named assemblies.</span></span>
2. <span data-ttu-id="f07fa-115">GAC(전역 어셈블리 캐시)에 어셈블리를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-115">The assembly can be stored in the Global Assembly Cache (GAC).</span></span>
3. <span data-ttu-id="f07fa-116">다른 어셈블리 버전과 나란히 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-116">The assembly can be loaded side by side with other versions of the assembly.</span></span> <span data-ttu-id="f07fa-117">병렬 어셈블리 로드는 일반적으로 플러그 인 아키텍처를 사용하는 애플리케이션에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-117">Side-by-side assembly loading is commonly required by applications with plug-in architectures.</span></span>

## <a name="create-strong-named-net-libraries"></a><span data-ttu-id="f07fa-118">강력한 이름의 .NET 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="f07fa-118">Create strong named .NET libraries</span></span>

<span data-ttu-id="f07fa-119">오픈 소스 .NET 라이브러리에 강력한 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-119">You should strong name your open-source .NET libraries.</span></span> <span data-ttu-id="f07fa-120">어셈블리에 강력한 이름을 지정하면 대부분의 사용자가 사용할 수 있으며, 엄격한 어셈블리 로드는 .NET Framework에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-120">Strong naming an assembly ensures the most people can use it, and strict assembly loading only affects the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="f07fa-121">이 지침은 NuGet.org에 게시된 .NET 라이브러리와 같은 공개적으로 배포된 .NET 라이브러리에만 해당합니다. 대부분의 .NET 애플리케이션에는 강력한 이름 지정이 필요하지 않으므로 기본적으로 수행해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-121">This guidance is specific to publicly distributed .NET libraries, such as .NET libraries published on NuGet.org. Strong naming is not required by most .NET applications and should not be done by default.</span></span>

<span data-ttu-id="f07fa-122">**✔️** 라이브러리 어셈블리에 강력한 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-122">**✔️ CONSIDER** strong naming your library's assemblies.</span></span>

<span data-ttu-id="f07fa-123">**✔️** 소스 제어 시스템에 강력한 이름 지정키를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-123">**✔️ CONSIDER** adding the strong naming key to your source control system.</span></span>

> <span data-ttu-id="f07fa-124">공개적으로 사용 가능한 키를 통해 개발자는 라이브러리 소스 코드를 수정하고 동일한 키로 다시 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-124">A publicly available key lets developers modify and recompile your library source code with the same key.</span></span>
> 
> <span data-ttu-id="f07fa-125">[부분 신뢰 시나리오](../../framework/misc/using-libraries-from-partially-trusted-code.md)에서 특별한 사용 권한을 제공하기 위해 이전에 사용된 경우에는 강력한 이름 지정 키를 공개해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-125">You shouldn't make the strong naming key public if it has been used in the past to give special permissions in [partial-trust scenarios](../../framework/misc/using-libraries-from-partially-trusted-code.md).</span></span> <span data-ttu-id="f07fa-126">공개하면 기존 환경이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-126">Otherwise, you might compromise existing environments.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f07fa-127">코드 게시자 ID를 원하는 경우 [Authenticode](/windows-hardware/drivers/install/authenticode) 및 [NuGet 패키지 서명](/nuget/create-packages/sign-a-package)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-127">When the identity of the publisher of the code is desired, [Authenticode](/windows-hardware/drivers/install/authenticode) and [NuGet Package Signing](/nuget/create-packages/sign-a-package) are recommended.</span></span> <span data-ttu-id="f07fa-128">CAS(코드 액세스 보안)를 보안 완화로 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-128">Code Access Security (CAS) should not be used as a security mitigation.</span></span>

<span data-ttu-id="f07fa-129">**✔️** 사용자가 바인딩 리디렉션 및 업데이트 빈도를 줄일 수 있도록 주 버전 변경 시에만 어셈블리 버전을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-129">**✔️ CONSIDER** incrementing the assembly version on only major version changes to help users reduce binding redirects, and how often they're updated.</span></span>

> <span data-ttu-id="f07fa-130">[버전 관리 및 어셈블리 버전](./versioning.md#assembly-version)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f07fa-130">Read more about [versioning and the assembly version](./versioning.md#assembly-version).</span></span>

<span data-ttu-id="f07fa-131">**❌** 강력한 이름 지정 키를 추가, 제거 또는 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-131">**❌ DO NOT** add, remove, or change the strong naming key.</span></span>

> <span data-ttu-id="f07fa-132">어셈블리의 강력한 이름 지정 키를 수정하면 어셈블리 ID가 변경되고, 어셈블리 ID를 사용하는 컴파일된 코드가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-132">Modifying an assembly's strong naming key changes the assembly's identity and breaks compiled code that uses it.</span></span> <span data-ttu-id="f07fa-133">자세한 내용은 [호환성이 손상되는 이진 변경](./breaking-changes.md#binary-breaking-change)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f07fa-133">For more information, see [binary breaking changes](./breaking-changes.md#binary-breaking-change).</span></span>

<span data-ttu-id="f07fa-134">**❌** 강력한 이름 및 강력하지 않은 이름이 지정된 버전의 라이브러리를 게시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-134">**❌ DO NOT** publish strong-named and non-strong-named versions of your library.</span></span> <span data-ttu-id="f07fa-135">예를 들어 `Contoso.Api` 또는 `Contoso.Api.StrongNamed`입니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-135">For example, `Contoso.Api` and `Contoso.Api.StrongNamed`.</span></span>

> <span data-ttu-id="f07fa-136">두 패키지를 게시하면 개발자 에코시스템이 포크됩니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-136">Publishing two packages forks your developer eco-system.</span></span> <span data-ttu-id="f07fa-137">또한 애플리케이션이 두 패키지에 모두 종속하게 되면 개발자가 형식 이름 충돌을 발견할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-137">Also, if an application ends up depending on both packages the developer can encounter type name conflicts.</span></span> <span data-ttu-id="f07fa-138">적어도 .NET의 경우 어셈블리마다 형식이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f07fa-138">As far as .NET is concerned they are different types in different assemblies.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f07fa-139">[이전](cross-platform-targeting.md)
>[다음](nuget.md)</span><span class="sxs-lookup"><span data-stu-id="f07fa-139">[Previous](cross-platform-targeting.md)
[Next](nuget.md)</span></span>
