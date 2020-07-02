---
ms.openlocfilehash: 72d48d1daa85b6891c122f2fcc5279642253b926
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614837"
---
### <a name="workflow-checksums-changed-from-md5-to-sha1"></a><span data-ttu-id="e5beb-101">워크플로 체크섬이 MD5에서 SHA1로 변경됨</span><span class="sxs-lookup"><span data-stu-id="e5beb-101">Workflow checksums changed from MD5 to SHA1</span></span>

#### <a name="details"></a><span data-ttu-id="e5beb-102">설명</span><span class="sxs-lookup"><span data-stu-id="e5beb-102">Details</span></span>

<span data-ttu-id="e5beb-103">Visual Studio로 디버깅을 지원하기 위해 워크플로 런타임은 해싱 알고리즘을 사용하여 워크플로 인스턴스에 대한 체크섬을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e5beb-103">To support debugging with Visual Studio, the Workflow runtime generates a checksum for a workflow instance using a hashing algorithm.</span></span> <span data-ttu-id="e5beb-104">.NET Framework 4.6.2 이전 버전에서 워크플로 체크섬 해시는 MD5 알고리즘을 사용하여 FIPS 지원 시스템에 문제가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="e5beb-104">In the .NET Framework 4.6.2 and earlier versions, workflow checksum hashing used the MD5 algorithm, which caused issues on FIPS-enabled systems.</span></span> <span data-ttu-id="e5beb-105">.NET Framework 4.7부터 알고리즘은 SHA1입니다.</span><span class="sxs-lookup"><span data-stu-id="e5beb-105">Starting with the .NET Framework 4.7, the algorithm is SHA1.</span></span> <span data-ttu-id="e5beb-106">코드가 이러한 체크섬을 지속하면 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5beb-106">If your code has persisted these checksums, they will be incompatible.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e5beb-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e5beb-107">Suggestion</span></span>

<span data-ttu-id="e5beb-108">체크섬 오류로 인해 코드가 워크플로 인스턴스를 로드할 수 없는 경우 `AppContext` switch &quot; Switch.System.Activities.UseMD5ForWFDebugger &quot;을 true.In code로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5beb-108">If your code is unable to load workflow instances due to a checksum failure, try setting the `AppContext` switch &quot;Switch.System.Activities.UseMD5ForWFDebugger&quot; to true.In code:</span></span>

```csharp
System.AppContext.SetSwitch("Switch.System.Activities.UseMD5ForWFDebugger", true);
```

<span data-ttu-id="e5beb-109">또는 다음 구성을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5beb-109">Or in configuration:</span></span>

```xml
<configuration>
  <runtime>
    <AppContextSwitchOverrides value="Switch.System.Activities.UseMD5ForWFDebugger=true" />
  </runtime>
</configuration>
```

| <span data-ttu-id="e5beb-110">이름</span><span class="sxs-lookup"><span data-stu-id="e5beb-110">Name</span></span>    | <span data-ttu-id="e5beb-111">값</span><span class="sxs-lookup"><span data-stu-id="e5beb-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e5beb-112">Scope</span><span class="sxs-lookup"><span data-stu-id="e5beb-112">Scope</span></span>   | <span data-ttu-id="e5beb-113">부</span><span class="sxs-lookup"><span data-stu-id="e5beb-113">Minor</span></span>       |
| <span data-ttu-id="e5beb-114">버전</span><span class="sxs-lookup"><span data-stu-id="e5beb-114">Version</span></span> | <span data-ttu-id="e5beb-115">4.7</span><span class="sxs-lookup"><span data-stu-id="e5beb-115">4.7</span></span>         |
| <span data-ttu-id="e5beb-116">형식</span><span class="sxs-lookup"><span data-stu-id="e5beb-116">Type</span></span>    | <span data-ttu-id="e5beb-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="e5beb-117">Retargeting</span></span> |
