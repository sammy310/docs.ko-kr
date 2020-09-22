---
ms.openlocfilehash: aadf5eb85c8736c29639d49bc8baf21545d2467c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606882"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="1b315-101">.NET COM이 이벤트에 대해 ByRef SafeArray 매개 변수를 성공적으로 마샬링</span><span class="sxs-lookup"><span data-stu-id="1b315-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="1b315-102">설명</span><span class="sxs-lookup"><span data-stu-id="1b315-102">Details</span></span>

<span data-ttu-id="1b315-103">.NET Framework 4.7.2 및 이전 버전에서 COM 이벤트에 대한 ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) 매개 변수가 네이티브 코드로 다시 마샬링하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="1b315-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="1b315-104">이 변경을 통해 이제 [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray)가 성공적으로 마샬링되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b315-104">With this change the [SafeArray](/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="1b315-105">[ x ] Quirked</span><span class="sxs-lookup"><span data-stu-id="1b315-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="1b315-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="1b315-106">Suggestion</span></span>

<span data-ttu-id="1b315-107">COM 이벤트에 대한 적절한 ByRef SafeArray 매개 변수 마샬링이 실행 중지될 경우 다음 구성 스위치를 애플리케이션 구성에 추가하여 이 코드를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b315-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="1b315-108">이름</span><span class="sxs-lookup"><span data-stu-id="1b315-108">Name</span></span>    | <span data-ttu-id="1b315-109">값</span><span class="sxs-lookup"><span data-stu-id="1b315-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1b315-110">Scope</span><span class="sxs-lookup"><span data-stu-id="1b315-110">Scope</span></span>   |<span data-ttu-id="1b315-111">부</span><span class="sxs-lookup"><span data-stu-id="1b315-111">Minor</span></span>|
|<span data-ttu-id="1b315-112">버전</span><span class="sxs-lookup"><span data-stu-id="1b315-112">Version</span></span>|<span data-ttu-id="1b315-113">4.8</span><span class="sxs-lookup"><span data-stu-id="1b315-113">4.8</span></span>|
|<span data-ttu-id="1b315-114">형식</span><span class="sxs-lookup"><span data-stu-id="1b315-114">Type</span></span>|<span data-ttu-id="1b315-115">런타임</span><span class="sxs-lookup"><span data-stu-id="1b315-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="1b315-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1b315-116">Affected APIs</span></span>

<span data-ttu-id="1b315-117">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b315-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
