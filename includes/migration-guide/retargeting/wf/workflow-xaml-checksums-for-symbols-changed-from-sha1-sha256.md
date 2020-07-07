---
ms.openlocfilehash: 946e71f2f466664c8f9fcf4811288ce693a872eb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85616278"
---
### <a name="workflow-xaml-checksums-for-symbols-changed-from-sha1-to-sha256"></a><span data-ttu-id="14a7f-101">SHA1에서 SHA256으로 변경된 기호에 대한 워크플로 XAML 체크섬</span><span class="sxs-lookup"><span data-stu-id="14a7f-101">Workflow XAML checksums for symbols changed from SHA1 to SHA256</span></span>

#### <a name="details"></a><span data-ttu-id="14a7f-102">설명</span><span class="sxs-lookup"><span data-stu-id="14a7f-102">Details</span></span>

<span data-ttu-id="14a7f-103">Visual Studio로 디버깅을 지원하기 위해 워크플로 런타임은 해싱 알고리즘을 사용하여 워크플로 XAML 파일에 대한 체크섬을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="14a7f-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow XAML file using a hashing algorithm.</span></span> <span data-ttu-id="14a7f-104">.NET Framework 4.6.2 이전 버전에서 워크플로 체크섬 해시는 MD5 알고리즘을 사용하여 FIPS 지원 시스템에 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="14a7f-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="14a7f-105">.NET Framework 4.7부터 기본 알고리즘이 SHA1로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14a7f-105">Starting with the .NET Framework 4.7, the default algorithm was changed to SHA1.</span></span> <span data-ttu-id="14a7f-106">.NET Framework 4.8부터 기본 알고리즘이 SHA256으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="14a7f-106">Starting with the .NET Framework 4.8, the default algorithm was changed to SHA256.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="14a7f-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="14a7f-107">Suggestion</span></span>

<span data-ttu-id="14a7f-108">체크섬 오류로 인해 코드가 워크플로 인스턴스를 로드할 수 없거나 적절한 기호를 찾을 수 없는 경우 `AppContext` 스위치 "Switch.System.Activities.UseSHA1HashForDebuggerSymbols"를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="14a7f-108">If your code is unable to load workflow instances or to find appropriate symbols due to a checksum failure, try setting the `AppContext` switch "Switch.System.Activities.UseSHA1HashForDebuggerSymbols" to `true`.</span></span> <span data-ttu-id="14a7f-109">코드</span><span class="sxs-lookup"><span data-stu-id="14a7f-109">In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseSHA1HashForDebuggerSymbols", true);
```

<span data-ttu-id="14a7f-110">또는 다음 구성을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a7f-110">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseSHA1HashForDebuggerSymbols=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="14a7f-111">이름</span><span class="sxs-lookup"><span data-stu-id="14a7f-111">Name</span></span>    | <span data-ttu-id="14a7f-112">값</span><span class="sxs-lookup"><span data-stu-id="14a7f-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="14a7f-113">Scope</span><span class="sxs-lookup"><span data-stu-id="14a7f-113">Scope</span></span>   | <span data-ttu-id="14a7f-114">부</span><span class="sxs-lookup"><span data-stu-id="14a7f-114">Minor</span></span>       |
| <span data-ttu-id="14a7f-115">버전</span><span class="sxs-lookup"><span data-stu-id="14a7f-115">Version</span></span> | <span data-ttu-id="14a7f-116">4.8</span><span class="sxs-lookup"><span data-stu-id="14a7f-116">4.8</span></span>         |
| <span data-ttu-id="14a7f-117">형식</span><span class="sxs-lookup"><span data-stu-id="14a7f-117">Type</span></span>    | <span data-ttu-id="14a7f-118">대상 변경</span><span class="sxs-lookup"><span data-stu-id="14a7f-118">Retargeting</span></span> |
