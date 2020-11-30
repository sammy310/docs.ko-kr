---
ms.openlocfilehash: 92c03328414410d56a2ff5f445639757367b42c7
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032059"
---
### <a name="processstartinfo-throws-invalidoperationexception-for-processes-you-didnt-start"></a><span data-ttu-id="a89cf-101">Process.StartInfo는 코드가 시작하지 않은 프로세스에 대해 InvalidOperationException을 throw함</span><span class="sxs-lookup"><span data-stu-id="a89cf-101">Process.StartInfo throws InvalidOperationException for processes you didn't start</span></span>

<span data-ttu-id="a89cf-102">코드가 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성을 읽으면 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a89cf-102">Reading the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start throws an <xref:System.InvalidOperationException>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a89cf-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="a89cf-103">Change description</span></span>

<span data-ttu-id="a89cf-104">.NET Framework에서는 코드가 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성에 액세스하면 더미 <xref:System.Diagnostics.ProcessStartInfo> 개체가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a89cf-104">In .NET Framework, accessing the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start returns a dummy <xref:System.Diagnostics.ProcessStartInfo> object.</span></span> <span data-ttu-id="a89cf-105">더미 개체는 <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>를 제외하고 모든 속성에 대한 기본값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a89cf-105">The dummy object contains default values for all of its properties except <xref:System.Diagnostics.ProcessStartInfo.EnvironmentVariables>.</span></span>

<span data-ttu-id="a89cf-106">.NET Core 1.0부터 코드가 (<xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>를 호출하여) 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성을 읽는 경우 <xref:System.InvalidOperationException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a89cf-106">Starting in .NET Core 1.0, if you read the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for a process that you didn't start (that is, by calling <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>), an <xref:System.InvalidOperationException> is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a89cf-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="a89cf-107">Version introduced</span></span>

<span data-ttu-id="a89cf-108">1.0</span><span class="sxs-lookup"><span data-stu-id="a89cf-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a89cf-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="a89cf-109">Recommended action</span></span>

<span data-ttu-id="a89cf-110">코드가 시작하지 않은 프로세스의 <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> 속성에 액세스하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a89cf-110">Do not access the <xref:System.Diagnostics.Process.StartInfo?displayProperty=nameWithType> property for processes that your code didn't start.</span></span> <span data-ttu-id="a89cf-111">예를 들어 <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>에서 반환하는 프로세스에 대해서는 이 속성을 읽지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a89cf-111">For example, don't read this property for processes returned by <xref:System.Diagnostics.Process.GetProcesses%2A?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="a89cf-112">범주</span><span class="sxs-lookup"><span data-stu-id="a89cf-112">Category</span></span>

<span data-ttu-id="a89cf-113">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="a89cf-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a89cf-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a89cf-114">Affected APIs</span></span>

- <xref:System.Diagnostics.Process.StartInfo?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Process.StartInfo`

-->
