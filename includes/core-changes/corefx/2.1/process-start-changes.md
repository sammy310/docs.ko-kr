---
ms.openlocfilehash: 7c0930f6606aa96d2863dc740aef8e9cab724b37
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75344855"
---
### <a name="change-in-default-value-of-useshellexecute"></a><span data-ttu-id="420f8-101">UseShellExecute의 기본값 변경</span><span class="sxs-lookup"><span data-stu-id="420f8-101">Change in default value of UseShellExecute</span></span>

<span data-ttu-id="420f8-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>의 기본값은 .NET Core에서 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-102"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> has a default value of `false` on .NET Core.</span></span> <span data-ttu-id="420f8-103">.NET Framework에서의 기본값은 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-103">On .NET Framework, its default value is `true`.</span></span>

#### <a name="change-description"></a><span data-ttu-id="420f8-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="420f8-104">Change description</span></span>

<span data-ttu-id="420f8-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 사용을 통해 애플리케이션을 직접 실행할 수 있습니다. 예를 들어 `Process.Start("mspaint.exe")`와 같은 코드를 사용하면 그림판이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-105"><xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> lets you launch an application directly, for example, with code such as `Process.Start("mspaint.exe")` that launches Paint.</span></span> <span data-ttu-id="420f8-106"><xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>이 `true`로 설정된 경우 연결된 애플리케이션을 간접적으로 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-106">It also lets you indirectly launch an associated application if <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is set to `true`.</span></span> <span data-ttu-id="420f8-107">.NET Framework에서 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>의 기본값은 `true`입니다. 따라서 해당 편집기를 사용하여 *.txt*과 연결한 경우 `Process.Start("mytextfile.txt")`와 같은 코드로 메모장이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-107">On .NET Framework, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `true`, meaning that code such as `Process.Start("mytextfile.txt")` would launch Notepad, if you've associated *.txt* files with that editor.</span></span> <span data-ttu-id="420f8-108">.NET Framework에서 간접적으로 앱을 시작하는 것을 방지하려면 명시적으로 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>을 `false`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-108">To prevent indirectly launching an app on .NET Framework, you must explicitly set <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="420f8-109">.NET Core에서 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>의 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-109">On .NET Core, the default value for <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> is `false`.</span></span> <span data-ttu-id="420f8-110">따라서 기본적으로 `Process.Start`를 호출할 때 연결된 애플리케이션이 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-110">This means that, by default, associated applications are not launched when you call `Process.Start`.</span></span>

<span data-ttu-id="420f8-111">이 변경 사항은 성능 사유로 인해 .NET Core에 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-111">This change was introduced in .NET Core for performance reasons.</span></span> <span data-ttu-id="420f8-112">일반적으로 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>은 애플리케이션을 직접 시작하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-112">Typically, <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> is used to launch an application directly.</span></span> <span data-ttu-id="420f8-113">앱을 직접 시작하는 경우 Windows 셸을 포함하지 않아도 되며 관련된 성능 비용도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-113">Launching an app directly does not need to involve the Windows shell and incur the associated performance cost.</span></span> <span data-ttu-id="420f8-114">이 기본 사례를 더욱 빠르게 하도록 .NET Core는 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType>의 기본값을 `false`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-114">To make this default case faster, .NET Core changes the default value of <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute?displayProperty=nameWithType> to `false`.</span></span> <span data-ttu-id="420f8-115">필요한 경우 느린 경로로 옵트인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-115">You can opt in to the slower path if you need it.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="420f8-116">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="420f8-116">Version introduced</span></span>

<span data-ttu-id="420f8-117">2.1</span><span class="sxs-lookup"><span data-stu-id="420f8-117">2.1</span></span>

> [!NOTE]
> <span data-ttu-id="420f8-118">이전 버전의 .NET Core에서 `UseShellExecute`는 Windows에 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-118">In earlier versions of .NET Core, `UseShellExecute` was not implemented for Windows.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="420f8-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="420f8-119">Recommended action</span></span>

<span data-ttu-id="420f8-120">앱이 이전 동작에 의존하는 경우 <xref:System.Diagnostics.ProcessStartInfo> 개체에서 <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute>가 `true`로 설정된 상태에서 <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="420f8-120">If your app relies on the old behavior, call <xref:System.Diagnostics.Process.Start(System.Diagnostics.ProcessStartInfo)?displayProperty=nameWithType> with <xref:System.Diagnostics.ProcessStartInfo.UseShellExecute> set to `true` on the <xref:System.Diagnostics.ProcessStartInfo> object.</span></span>

#### <a name="category"></a><span data-ttu-id="420f8-121">범주</span><span class="sxs-lookup"><span data-stu-id="420f8-121">Category</span></span>

<span data-ttu-id="420f8-122">CoreFx</span><span class="sxs-lookup"><span data-stu-id="420f8-122">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="420f8-123">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="420f8-123">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.ProcessStartInfo?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Diagnostics.Process.Start`
- `M:System.Diagnostics.ProcessStartInfo`

-->
