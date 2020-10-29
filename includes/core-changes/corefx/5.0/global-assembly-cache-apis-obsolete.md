---
ms.openlocfilehash: 959d8cb6d3e52916f6777054f3e9b327dc8edb4e
ms.sourcegitcommit: 98d20cb038669dca4a195eb39af37d22ea9d008e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "92434934"
---
### <a name="global-assembly-cache-apis-are-obsolete"></a><span data-ttu-id="377b1-101">전역 어셈블리 캐시 API가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="377b1-101">Global assembly cache APIs are obsolete</span></span>

<span data-ttu-id="377b1-102">.NET Core 및 .NET 5.0 이상 버전에서는 .NET Framework에 있었던 GAC(전역 어셈블리 캐시) 개념이 사라집니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-102">.NET Core and .NET 5.0 and later versions eliminate the concept of the global assembly cache (GAC) that was present in .NET Framework.</span></span> <span data-ttu-id="377b1-103">따라서 GAC를 처리하는 모든 .NET Core 및 .NET 5+ API가 실패하거나 작업을 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-103">As such, all .NET Core and .NET 5+ APIs that deal with the GAC either fail or perform no operation.</span></span>

<span data-ttu-id="377b1-104">개발자가 이러한 API를 사용하지 않도록 하기 위해 일부 GAC 관련 API는 사용되지 않는 것으로 표시되고 컴파일 시간에 `SYSLIB0005` 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-104">To help steer developers away from these APIs, some GAC-related APIs are marked as obsolete, and generate a `SYSLIB0005` warning at compile time.</span></span> <span data-ttu-id="377b1-105">이러한 API는 향후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-105">These APIs may be removed in a future version of .NET.</span></span>

#### <a name="change-description"></a><span data-ttu-id="377b1-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="377b1-106">Change description</span></span>

<span data-ttu-id="377b1-107">다음은 사용되지 않는 것으로 표시되는 API입니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-107">The following APIs are marked obsolete.</span></span>

| <span data-ttu-id="377b1-108">API</span><span class="sxs-lookup"><span data-stu-id="377b1-108">API</span></span> | <span data-ttu-id="377b1-109">사용되지 않음으로 표시...</span><span class="sxs-lookup"><span data-stu-id="377b1-109">Marked obsolete in...</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType> | <span data-ttu-id="377b1-110">5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="377b1-110">5.0 RC1</span></span> |

<span data-ttu-id="377b1-111">.NET Framework 2.x - 4.x에서 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성은 쿼리된 어셈블리가 GAC에서 로드되면 `true`를 반환하고, 디스크의 다른 위치에서 로드되면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-111">In .NET Framework 2.x - 4.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property returns `true` if the queried assembly was loaded from the GAC, and `false` if it was loaded from a different location on disk.</span></span> <span data-ttu-id="377b1-112">.NET Core 2.x - 3.x에서 <xref:System.Reflection.Assembly.GlobalAssemblyCache>는 항상 `false`를 반환하여 GAC가 .NET Core에 없음을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-112">In .NET Core 2.x - 3.x, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> always returns `false`, reflecting that the GAC does not exist in .NET Core.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'True' on .NET Framework, 'False' on .NET Core.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="377b1-113">.NET 5.0 이상 버전에서 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성은 항상 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-113">In .NET 5.0 and later versions, the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property continues to always return `false`.</span></span> <span data-ttu-id="377b1-114">그러나 속성 getter도 사용되지 않는 것으로 표시되어 속성 액세스를 중지해야 함을 호출자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-114">However, the property getter is also marked as obsolete to indicate to callers that they should stop accessing the property.</span></span> <span data-ttu-id="377b1-115">라이브러리와 앱은 런타임 동작에 대한 결정을 내릴 때 <xref:System.Reflection.Assembly.GlobalAssemblyCache> API를 사용하면 안 됩니다. 이 API는 .NET Core 및 .NET 5.0 이상 버전에서 항상 `false`를 반환하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-115">Libraries and apps should not use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> API to make determinations about run-time behavior, as it always returns `false` in .NET Core and .NET 5.0 and later versions.</span></span>

```csharp
Assembly asm = typeof(object).Assembly;
// Prints 'False' on .NET 5.0+; also produces warning SYSLIB0005 at compile time.
Console.WriteLine(asm.GlobalAssemblyCache);
```

<span data-ttu-id="377b1-116">이는 컴파일 시간 전용 변경입니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-116">This is a compile-time only change.</span></span> <span data-ttu-id="377b1-117">.NET Core의 이전 버전에서 런타임 변경은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-117">There is no run-time change from previous versions of .NET Core.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="377b1-118">변경 이유</span><span class="sxs-lookup"><span data-stu-id="377b1-118">Reason for change</span></span>

<span data-ttu-id="377b1-119">GAC(전역 어셈블리 캐시)는 .NET Core 및 .NET 5.0 이상 버전에서 개념으로 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-119">The global assembly cache (GAC) does not exist as a concept in .NET Core and .NET 5.0 and later versions.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="377b1-120">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="377b1-120">Version introduced</span></span>

<span data-ttu-id="377b1-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="377b1-121">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="377b1-122">권장 조치</span><span class="sxs-lookup"><span data-stu-id="377b1-122">Recommended action</span></span>

- <span data-ttu-id="377b1-123">애플리케이션이 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 속성을 쿼리하는 경우 호출을 제거하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-123">If your application queries the <xref:System.Reflection.Assembly.GlobalAssemblyCache> property, consider removing the call.</span></span> <span data-ttu-id="377b1-124"><xref:System.Reflection.Assembly.GlobalAssemblyCache> 값을 사용하여 런타임에 “GAC에 있는 어셈블리” 흐름과 “GAC에 없는 어셈블리” 흐름을 선택하는 경우 이 흐름이 .NET Core 또는 .NET 5.0+ 애플리케이션에 적합한지를 재고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-124">If you use the <xref:System.Reflection.Assembly.GlobalAssemblyCache> value to choose between an "assembly in the GAC"-flow vs. an "assembly not in the GAC"-flow at run time, reconsider whether the flow still makes sense for a .NET Core or .NET 5.0+ application.</span></span>

- <span data-ttu-id="377b1-125">사용되지 않는 API를 계속 사용해야 하는 경우 코드에서 `SYSLIB0005` 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-125">If you must continue to use the obsolete APIs, you can suppress the `SYSLIB0005` warning in code.</span></span>

  ```csharp
  Assembly asm = typeof(object).Assembly;
  #pragma warning disable SYSLIB0005 // Disable the warning.
  // Prints 'False' on .NET 5.0+.
  Console.WriteLine(asm.GlobalAssemblyCache);
  #pragma warning restore SYSLIB0005 // Re-enable the warning.
  ```

  <span data-ttu-id="377b1-126">프로젝트 파일에서 경고를 표시하지 않고 프로젝트의 모든 소스 파일에 대해 경고를 사용하지 않도록 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-126">You can also suppress the warning in your project file, which disables the warning for all source files in the project.</span></span>

  ```xml
  <Project Sdk="Microsoft.NET.Sdk">
    <PropertyGroup>
     <TargetFramework>net5.0</TargetFramework>
     <!-- NoWarn below will suppress SYSLIB0005 project-wide -->
     <NoWarn>$(NoWarn);SYSLIB0005</NoWarn>
    </PropertyGroup>
  </Project>
  ```

  <span data-ttu-id="377b1-127">`SYSLIB0005`를 표시하지 않으면 <xref:System.Reflection.Assembly.GlobalAssemblyCache> 사용되지 않음 경고만 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-127">Suppressing `SYSLIB0005` disables only the <xref:System.Reflection.Assembly.GlobalAssemblyCache> obsoletion warning.</span></span> <span data-ttu-id="377b1-128">다른 경고를 사용하지 않도록 설정하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="377b1-128">It does not disable any other warnings.</span></span>

#### <a name="category"></a><span data-ttu-id="377b1-129">범주</span><span class="sxs-lookup"><span data-stu-id="377b1-129">Category</span></span>

<span data-ttu-id="377b1-130">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="377b1-130">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="377b1-131">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="377b1-131">Affected APIs</span></span>

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Reflection.Assembly.GlobalAssemblyCache`

-->
