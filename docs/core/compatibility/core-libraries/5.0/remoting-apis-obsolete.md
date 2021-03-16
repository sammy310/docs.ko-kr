---
title: '호환성이 손상되는 변경: 원격 API가 사용되지 않음'
description: 일부 원격 관련 API가 사용되지 않는 것으로 표시되고 사용자 지정 진단 ID를 사용하여 경고를 생성하는 핵심 .NET 라이브러리의 .NET 5 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/01/2020
ms.openlocfilehash: 3c4f7cd200cadd11321da60f2b4a0d191497aae8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257171"
---
# <a name="remoting-apis-are-obsolete"></a><span data-ttu-id="756f2-103">원격 API가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="756f2-103">Remoting APIs are obsolete</span></span>

<span data-ttu-id="756f2-104">일부 원격 관련 API는 사용되지 않는 것으로 표시되고 컴파일 시간에 `SYSLIB0010` 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-104">Some remoting-related APIs are marked as obsolete and generate a `SYSLIB0010` warning at compile time.</span></span> <span data-ttu-id="756f2-105">이러한 API는 향후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-105">These APIs may be removed in a future version of .NET.</span></span>

## <a name="change-description"></a><span data-ttu-id="756f2-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="756f2-106">Change description</span></span>

<span data-ttu-id="756f2-107">다음은 사용되지 않는 것으로 표시되는 원격 API입니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-107">The following remoting APIs are marked obsolete.</span></span>

| <span data-ttu-id="756f2-108">API</span><span class="sxs-lookup"><span data-stu-id="756f2-108">API</span></span> | <span data-ttu-id="756f2-109">사용되지 않음으로 표시...</span><span class="sxs-lookup"><span data-stu-id="756f2-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="756f2-110">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="756f2-110">5.0 RC1</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="756f2-111">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="756f2-111">5.0 RC1</span></span> |

<span data-ttu-id="756f2-112">.NET Framework 2.x - 4.x에서 <xref:System.MarshalByRefObject.GetLifetimeService> 및 <xref:System.MarshalByRefObject.InitializeLifetimeService> 메서드는 .NET Remoting과 관련된 인스턴스의 수명을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-112">In .NET Framework 2.x - 4.x, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods control the lifetime of instances involved with .NET remoting.</span></span> <span data-ttu-id="756f2-113">.NET Core 2.x- 3.x에서 이러한 메서드는 런타임에 항상 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-113">In .NET Core 2.x- 3.x, these methods always throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

<span data-ttu-id="756f2-114">.NET 5 이상 버전에서 <xref:System.MarshalByRefObject.GetLifetimeService> 및 <xref:System.MarshalByRefObject.InitializeLifetimeService> 메서드는 경고로 표시되며 사용되지 않지만 런타임에 <xref:System.PlatformNotSupportedException>을 계속 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-114">In .NET 5 and later versions, the <xref:System.MarshalByRefObject.GetLifetimeService> and <xref:System.MarshalByRefObject.InitializeLifetimeService> methods are marked obsolete as warning, but continue to throw a <xref:System.PlatformNotSupportedException> at run time.</span></span>

```csharp
// MemoryStream, like all Stream instances, subclasses MarshalByRefObject.
MemoryStream stream = new MemoryStream();
// Throws PlatformNotSupportedException; also produces warning SYSLIB0010.
obj.InitializeLifetimeService();
```

<span data-ttu-id="756f2-115">이는 컴파일 시간 전용 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-115">This is a compile-time only change.</span></span> <span data-ttu-id="756f2-116">.NET Core의 이전 버전에서 런타임 변경은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-116">There is no run-time change from previous versions of .NET Core.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="756f2-117">변경 이유</span><span class="sxs-lookup"><span data-stu-id="756f2-117">Reason for change</span></span>

<span data-ttu-id="756f2-118">[.NET Remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))은 레거시 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-118">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology.</span></span> <span data-ttu-id="756f2-119">다른 프로세스(잠재적으로 다른 머신에서도 가능)에서 개체를 인스턴스화하고 일반 in-process .NET 개체 인스턴스인 경우 해당 개체와 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-119">It allows instantiating an object in another process (potentially even on a different machine) and interacting with that object as if it were an ordinary, in-process .NET object instance.</span></span> <span data-ttu-id="756f2-120">.NET Remoting 인프라는 .NET Framework 2.x - 4.x에만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-120">The .NET remoting infrastructure only exists in .NET Framework 2.x - 4.x.</span></span> <span data-ttu-id="756f2-121">.NET Core 및 .NET 5 이상 버전은 .NET Remoting을 지원하지 않으며 원격 API는 없거나 런타임에 대해 항상 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-121">.NET Core and .NET 5 and later versions don't have support for .NET remoting, and the remoting APIs either don't exist or always throw exceptions on these runtimes.</span></span>

<span data-ttu-id="756f2-122">개발자가 이러한 API를 사용하지 않도록 하기 위해 선택한 원격 관련 API를 사용되지 않는 것으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-122">To help steer developers away from these APIs, we are obsoleting selected remoting-related APIs.</span></span> <span data-ttu-id="756f2-123">이러한 API는 향후 .NET 버전에서 완전히 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-123">These APIs may be removed entirely in a future version of .NET.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="756f2-124">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="756f2-124">Version introduced</span></span>

<span data-ttu-id="756f2-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="756f2-125">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="756f2-126">권장 조치</span><span class="sxs-lookup"><span data-stu-id="756f2-126">Recommended action</span></span>

- <span data-ttu-id="756f2-127">WCF 또는 HTTP 기반 REST 서비스를 사용하여 다른 애플리케이션이나 머신에서 개체와 통신하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-127">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="756f2-128">자세한 내용은 [.NET Core에서 사용할 수 없는 .NET Framework 기술](../../../porting/net-framework-tech-unavailable.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="756f2-128">For more information, see [.NET Framework technologies unavailable on .NET Core](../../../porting/net-framework-tech-unavailable.md).</span></span>

- <span data-ttu-id="756f2-129">사용되지 않는 API를 계속 사용해야 하는 경우 코드에서 `SYSLIB0010` 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-129">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0010` warning in code.</span></span>

  ```csharp
  MarshalByRefObject obj = GetMarshalByRefObj();
  #pragma warning disable SYSLIB0010 // Disable the warning.
  obj.InitializeLifetimeService(); // Still throws PNSE.
  obj.GetLifetimeService(); // Still throws PNSE.
  #pragma warning restore SYSLIB0010 // Reenable the warning.
  ```

  <span data-ttu-id="756f2-130">프로젝트 파일에서 경고를 표시하지 않고 프로젝트의 모든 소스 파일에 대해 경고를 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-130">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0010 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0010</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="756f2-131">`SYSLIB0010`을 표시하지 않으면 원격 API 사용되지 않음 경고만 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-131">Suppressing `SYSLIB0010` disables only the remoting API obsoletion warnings.</span></span> <span data-ttu-id="756f2-132">다른 경고를 사용하지 않도록 설정하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-132">It does not disable any other warnings.</span></span> <span data-ttu-id="756f2-133">또한 항상 <xref:System.PlatformNotSupportedException>을 throw하는 하드 코드된 런타임 동작을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="756f2-133">Additionally, it doesn't change the hardcoded run-time behavior of always throwing <xref:System.PlatformNotSupportedException>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="756f2-134">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="756f2-134">Affected APIs</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=fullName>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `M:System.MarshalByRefObject.GetLifetimeService`
- `M:System.MarshalByRefObject.InitializeLifetimeService`

-->
