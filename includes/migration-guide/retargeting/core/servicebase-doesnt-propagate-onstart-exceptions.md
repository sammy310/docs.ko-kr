---
ms.openlocfilehash: 519de92ca4201d199941afe6382ddf9fc480fbbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614779"
---
### <a name="servicebase-doesnt-propagate-onstart-exceptions"></a><span data-ttu-id="74937-101">ServiceBase는 OnStart 예외를 전파하지 않음</span><span class="sxs-lookup"><span data-stu-id="74937-101">ServiceBase doesn't propagate OnStart exceptions</span></span>

#### <a name="details"></a><span data-ttu-id="74937-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="74937-102">Details</span></span>

<span data-ttu-id="74937-103">.NET Framework 4.7 및 이전 버전에서 서비스 시작 시 throw되는 예외는 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>의 호출자에게 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="74937-103">In the .NET Framework 4.7 and earlier versions, exceptions thrown on service startup are not propagated to the caller of <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>.</span></span><br/><span data-ttu-id="74937-104">.NET Framework 4.7.1을 대상으로 하는 애플리케이션을 시작으로 런타임은 시작에 실패하는 서비스에 대해 <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType>에 예외를 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="74937-104">Starting with applications that target the .NET Framework 4.7.1, the runtime propagates exceptions to <xref:System.ServiceProcess.ServiceBase.Run%2A?displayProperty=nameWithType> for services that fail to start.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="74937-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="74937-105">Suggestion</span></span>

<span data-ttu-id="74937-106">서비스 시작 시 예외가 있는 경우 해당 예외가 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="74937-106">On service start, if there is an exception, that exception will be propagated.</span></span> <span data-ttu-id="74937-107">이는 서비스가 시작에 실패하는 사례를 진단하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74937-107">This should help diagnose cases where services fail to start.</span></span> <br/><span data-ttu-id="74937-108">이 동작을 원치 않을 경우 애플리케이션 구성 파일의 &lt;runtime&gt; 섹션에 다음 &lt;AppContextSwitchOverrides&gt; 요소를 추가하여 옵트아웃할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74937-108">If this behavior is undesirable, you can opt out of it by adding the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=true" />
```

<span data-ttu-id="74937-109">애플리케이션이 4.7.1 이전 버전을 대상으로 하지만 이 동작을 원할 경우 애플리케이션 구성 파일의 &lt;runtime&gt; 섹션에 다음 &lt;AppContextSwitchOverrides&gt; 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="74937-109">If your application targets an earlier version than 4.7.1 but you want to have this behavior, add the following &lt;AppContextSwitchOverrides&gt; element to the &lt;runtime&gt; section of your application configuration file:</span></span>

```xml
<AppContextSwitchOverrides value="Switch.System.ServiceProcess.DontThrowExceptionsOnStart=false" />
```

| <span data-ttu-id="74937-110">이름</span><span class="sxs-lookup"><span data-stu-id="74937-110">Name</span></span>    | <span data-ttu-id="74937-111">값</span><span class="sxs-lookup"><span data-stu-id="74937-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="74937-112">Scope</span><span class="sxs-lookup"><span data-stu-id="74937-112">Scope</span></span>   | <span data-ttu-id="74937-113">부</span><span class="sxs-lookup"><span data-stu-id="74937-113">Minor</span></span>       |
| <span data-ttu-id="74937-114">버전</span><span class="sxs-lookup"><span data-stu-id="74937-114">Version</span></span> | <span data-ttu-id="74937-115">4.7.1</span><span class="sxs-lookup"><span data-stu-id="74937-115">4.7.1</span></span>       |
| <span data-ttu-id="74937-116">형식</span><span class="sxs-lookup"><span data-stu-id="74937-116">Type</span></span>    | <span data-ttu-id="74937-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="74937-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="74937-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="74937-118">Affected APIs</span></span>

- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase)?displayProperty=nameWithType>
- <xref:System.ServiceProcess.ServiceBase.Run(System.ServiceProcess.ServiceBase[])?displayProperty=nameWithType>
