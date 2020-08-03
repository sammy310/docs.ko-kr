---
title: .NET Framework 1.1에서 마이그레이션
description: Windows 7 이상에서 .NET Framework 1.1을 사용하여 컴파일된 애플리케이션을 실행하는 데 필요한 단계에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 4.5, migrating from 1.1
- .NET Framework 1.1, migrating to .NET Framework 4.5
ms.assetid: 7ead0cb3-3b19-414a-8417-a1c1fa198d9e
ms.openlocfilehash: f2b0e21ff5dbeab3395335f52799629859fb2d90
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475270"
---
# <a name="migrate-from-the-net-framework-11"></a><span data-ttu-id="0f02e-103">.NET Framework 1.1에서 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0f02e-103">Migrate from the .NET Framework 1.1</span></span>

<span data-ttu-id="0f02e-104">Windows 7 이상 버전의 Windows 운영 체제는 .NET Framework 1.1을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-104">Windows 7 and later versions of the Windows operating system do not support the .NET Framework 1.1.</span></span> <span data-ttu-id="0f02e-105">따라서 Windows 7 이상 운영 체제 버전에서 수정하지 않으면 .NET Framework 1.1을 대상으로 하는 애플리케이션이 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-105">As a result, applications that target the .NET Framework 1.1 will not run without modification on Windows 7 or later operating system versions.</span></span> <span data-ttu-id="0f02e-106">이 항목에서는 Windows 7 이상 버전의 Windows 운영 체제에서 .NET Framework 1.1을 대상으로 하는 애플리케이션을 실행하는 데 필요한 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-106">This topic discusses the steps required to run an application that targets the .NET Framework 1.1 under Windows 7 and later versions of the Windows operating system.</span></span> <span data-ttu-id="0f02e-107">.NET Framework 1.1 및 Windows 8에 대한 자세한 내용은 [Windows 8 이상 버전에서 .NET Framework 1.1 앱 실행](../install/run-net-framework-1-1-apps.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f02e-107">For more information about the .NET Framework 1.1 and Windows 8, see [Run .NET Framework 1.1 Apps on Windows 8 and later versions](../install/run-net-framework-1-1-apps.md).</span></span>

## <a name="retarget-or-recompile"></a><span data-ttu-id="0f02e-108">대상 변경 또는 다시 컴파일</span><span class="sxs-lookup"><span data-stu-id="0f02e-108">Retarget or recompile</span></span>

<span data-ttu-id="0f02e-109">.NET Framework 1.1을 사용하여 컴파일된 애플리케이션을 가져와서 Windows 7 이상의 Windows 운영 체제에서 실행하는 방법에는 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-109">There are two ways to get an application that was compiled using the .NET Framework 1.1 to run on Windows 7 or a later Windows operating system:</span></span>

- <span data-ttu-id="0f02e-110">.NET Framework 4 이상 버전에서 실행되도록 애플리케이션 대상을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-110">Retarget the application to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="0f02e-111">대상을 변경하려면 애플리케이션을 .NET Framework 4 이상 버전에서 실행하도록 허용하는 애플리케이션의 구성 파일에 [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) 요소를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-111">Retargeting requires that you add a [\<supportedRuntime>](../configure-apps/file-schema/startup/supportedruntime-element.md) element to the application's configuration file that allows it to run under .NET Framework 4 and later versions.</span></span> <span data-ttu-id="0f02e-112">이러한 구성 파일은 다음과 같은 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-112">Such a configuration file takes the following form:</span></span>

    ```xml
    <configuration>
       <startup>
          <supportedRuntime version="v4.0"/>
       </startup>
    </configuration>
    ```

- <span data-ttu-id="0f02e-113">.NET Framework 4 이상 버전을 대상으로 하는 컴파일러를 사용하여 애플리케이션을 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-113">Recompile the application with a compiler that targets the .NET Framework 4 or a later version.</span></span> <span data-ttu-id="0f02e-114">처음에 Visual Studio 2003을 사용하여 솔루션을 개발하고 컴파일한 경우 Visual Studio 2010(가능하면 이상 버전)에서 솔루션을 열 수 있으며 **프로젝트 호환성** 대화 상자를 사용하여 Visual Studio 2003에서 사용된 형식의 솔루션 및 프로젝트 파일을 MSBuild(Microsoft Build Engine) 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-114">If you originally used Visual Studio 2003 to develop and compile your solution, you can open the solution in Visual Studio 2010 (and possibly later versions too) and use the **Project Compatibility** dialog box to convert the solution and project files from the formats used by Visual Studio 2003 to the Microsoft Build Engine (MSBuild) format.</span></span>

<span data-ttu-id="0f02e-115">애플리케이션을 다시 컴파일하는지 또는 대상을 변경하는지에 관계 없이 애플리케이션이 해당 .NET Framework보다 최신 버전에 도입된 변경 사항에 영향을 받는지 여부를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-115">Regardless of whether you prefer to recompile or retarget your application, you must determine whether your application is affected by any changes introduced in later versions of the .NET Framework.</span></span> <span data-ttu-id="0f02e-116">이러한 변경 사항에는 두 가지 종류가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-116">These changes are of two kinds:</span></span>

- <span data-ttu-id="0f02e-117">.NET Framework 1.1 및 해당 .NET Framework보다 최신 버전 사이에서 발생된 호환성이 손상되는 변경.</span><span class="sxs-lookup"><span data-stu-id="0f02e-117">Breaking changes that occurred between the .NET Framework 1.1 and later versions of the .NET Framework.</span></span>

- <span data-ttu-id="0f02e-118">.NET Framework 1.1 및 해당 .NET Framework보다 최신 버전 사이에서 사용되지 않거나 더 이상 사용할 수 없게 표시된 형식 또는 형식 멤버.</span><span class="sxs-lookup"><span data-stu-id="0f02e-118">Types and type members that have been marked as deprecated or obsolete between the .NET Framework 1.1 and later versions of the .NET Framework.</span></span>

<span data-ttu-id="0f02e-119">애플리케이션을 다시 컴파일하거나 애플리케이션 대상을 변경할 때 .NET Framework 1.1 이후에 릴리스된 .NET Framework의 각 버전에 대해 주요 변경 사항 및 사용되지 않는 형식 및 멤버를 모두 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-119">Whether you retarget your application or recompile it, you should review both the breaking changes and the obsolete types and members for each version of the .NET Framework that was released after .NET Framework 1.1.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="0f02e-120">호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="0f02e-120">Breaking changes</span></span>

<span data-ttu-id="0f02e-121">주요 변경 사항이 발생하면 구체적인 변경 사항에 따라 대상이 변경되거나 다시 컴파일된 애플리케이션 모두에 대해 해결 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-121">When a breaking change occurs, depending on the specific change, a workaround may be available both for retargeted and recompiled applications.</span></span> <span data-ttu-id="0f02e-122">이 경우 자식 요소를 애플리케이션의 구성 파일에 있는 [\<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md) 요소에 추가하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-122">In some cases, you can add a child element to the [\<runtime>](../configure-apps/file-schema/startup/supportedruntime-element.md) element of your application's configuration file to restore the previous behavior.</span></span> <span data-ttu-id="0f02e-123">예를 들어 다음 구성 파일에서는 .NET Framework 1.1에서 사용된 문자열 정렬 및 비교 동작을 복원하여 대상이 변경되거나 다시 컴파일된 애플리케이션에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-123">For example, the following configuration file restores the string sorting and comparison behavior used in the .NET Framework 1.1 and can be used either with a retargeted or a recompiled application.</span></span>

```xml
<configuration>
   <runtime>
      <CompatSortNLSVersion enabled="4096"/>
   </runtime>
</configuration>
```

<span data-ttu-id="0f02e-124">그러나 경우에 따라 소스 코드를 수정하고 애플리케이션을 다시 컴파일해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-124">However, in some cases, you may have to modify your source code and recompile your application.</span></span>

<span data-ttu-id="0f02e-125">애플리케이션의 가능한 주요 변경 사항의 영향을 평가하려면 다음 변경 사항 목록을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-125">To assess the impact of possible breaking changes on your application, you must review the following lists of changes:</span></span>

- <span data-ttu-id="0f02e-126">[.NET Framework 2.0의 주요 변경 내용](https://docs.microsoft.com/previous-versions/aa570326(v=msdn.10)) 문서의 .NET Framework 1.1을 대상으로 하는 애플리케이션에 영향을 줄 수 있는 .NET Framework 2.0 SP1의 변경 내용.</span><span class="sxs-lookup"><span data-stu-id="0f02e-126">[Breaking Changes in .NET Framework 2.0](https://docs.microsoft.com/previous-versions/aa570326(v=msdn.10)) documents changes in .NET Framework 2.0 SP1 that can affect an application that targets .NET Framework 1.1.</span></span>

- <span data-ttu-id="0f02e-127">[.NET Framework 3.5 SP1의 변경 내용](https://docs.microsoft.com/previous-versions/dotnet/articles/dd310284(v=msdn.10))에서는 .NET Framework 3.5와 .NET Framework 3.5 SP1 사이의 변경 내용을 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-127">[Changes in .NET Framework 3.5 SP1](https://docs.microsoft.com/previous-versions/dotnet/articles/dd310284(v=msdn.10)) documents changes between the .NET Framework 3.5 and the .NET Framework 3.5 SP1.</span></span>

- <span data-ttu-id="0f02e-128">[.NET Framework 4 마이그레이션 문제](net-framework-4-migration-issues.md)에서는 .NET Framework 3.5 SP1과 .NET Framework 4 사이의 변경 내용을 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-128">[.NET Framework 4 Migration Issues](net-framework-4-migration-issues.md) documents changes between the .NET Framework 3.5 SP1 and the .NET Framework 4.</span></span>

## <a name="obsolete-types-and-members"></a><span data-ttu-id="0f02e-129">사용되지 않는 형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="0f02e-129">Obsolete types and members</span></span>

<span data-ttu-id="0f02e-130">사용되지 않는 형식 및 멤버의 영향은 대상이 변경된 애플리케이션 및 다시 컴파일된 애플리케이션에서 다르게 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-130">The impact of deprecated types and members is somewhat different for retargeted applications and recompiled applications.</span></span> <span data-ttu-id="0f02e-131">사용되지 않는 형식 및 멤버를 사용하더라도 해당 어셈블리에서 해당 형식 및 멤버를 물리적으로 제거하지 않는 경우 대상이 변경된 애플리케이션에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-131">The use of obsolete types and members will not affect a retargeted application unless the obsolete type or member has been physically removed from its assembly.</span></span> <span data-ttu-id="0f02e-132">사용되지 않는 형식 및 멤버를 사용하는 애플리케이션을 다시 컴파일하면 일반적으로 컴파일러 오류가 아닌 컴파일러 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-132">Recompiling an application that uses obsolete types or members usually produces a compiler warning rather than a compiler error.</span></span> <span data-ttu-id="0f02e-133">하지만 경우에 따라 컴파일러 오류가 발생되어 사용되지 않는 형식 및 멤버를 사용하는 코드가 성공적으로 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-133">However, in some cases, it produces a compiler error, and code that uses the obsolete type or member does not compile successfully.</span></span> <span data-ttu-id="0f02e-134">이 경우 애플리케이션을 다시 컴파일하기 전에 사용되지 않는 형식 및 멤버를 호출하는 소스 코드를 다시 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-134">In this case, you must rewrite the source code that calls the obsolete type or member before you recompile your application.</span></span> <span data-ttu-id="0f02e-135">사용되지 않는 형식 및 멤버에 대한 자세한 내용은 [클래스 라이브러리의 사용되지 않는 기능](../whats-new/whats-obsolete.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f02e-135">For more information about obsolete types and members, see [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md).</span></span>

<span data-ttu-id="0f02e-136">.NET Framework 2.0 SP1 릴리스 이후 사용되지 않는 형식 및 멤버의 영향을 평가하려면 [클래스 라이브러리의 사용되지 않는 기능](../whats-new/whats-obsolete.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0f02e-136">To assess the impact of types and members that have been deprecated since the release of the .NET Framework 2.0 SP1, see [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md).</span></span> <span data-ttu-id="0f02e-137">사용되지 않는 형식 및 멤버 목록은 .NET Framework 2.0 SP1, .NET Framework 3.5 및 .NET Framework 4에서 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="0f02e-137">Review the lists of obsolete types and member for the .NET Framework 2.0 SP1, the .NET Framework 3.5, and the .NET Framework 4.</span></span>
