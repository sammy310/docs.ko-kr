---
ms.openlocfilehash: 77e9d28d79a92cf1523e4ef5779d78394b00ae80
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622087"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="f21f4-101">.NET COM이 이벤트에 대해 ByRef SafeArray 매개 변수를 성공적으로 마샬링</span><span class="sxs-lookup"><span data-stu-id="f21f4-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

#### <a name="details"></a><span data-ttu-id="f21f4-102">설명</span><span class="sxs-lookup"><span data-stu-id="f21f4-102">Details</span></span>

<span data-ttu-id="f21f4-103">.NET Framework 4.7.2 및 이전 버전에서 COM 이벤트에 대한 ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) 매개 변수가 네이티브 코드로 다시 마샬링하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f21f4-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="f21f4-104">이 변경을 통해 이제 [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray)가 성공적으로 마샬링되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f21f4-104">With this change the [SafeArray](https://docs.microsoft.com/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="f21f4-105">[ x ] Quirked</span><span class="sxs-lookup"><span data-stu-id="f21f4-105">[ x ] Quirked</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="f21f4-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f21f4-106">Suggestion</span></span>

<span data-ttu-id="f21f4-107">COM 이벤트에 대한 적절한 ByRef SafeArray 매개 변수 마샬링이 실행 중지될 경우 다음 구성 스위치를 애플리케이션 구성에 추가하여 이 코드를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f21f4-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="f21f4-108">이름</span><span class="sxs-lookup"><span data-stu-id="f21f4-108">Name</span></span>    | <span data-ttu-id="f21f4-109">값</span><span class="sxs-lookup"><span data-stu-id="f21f4-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f21f4-110">Scope</span><span class="sxs-lookup"><span data-stu-id="f21f4-110">Scope</span></span>   |<span data-ttu-id="f21f4-111">부</span><span class="sxs-lookup"><span data-stu-id="f21f4-111">Minor</span></span>|
|<span data-ttu-id="f21f4-112">버전</span><span class="sxs-lookup"><span data-stu-id="f21f4-112">Version</span></span>|<span data-ttu-id="f21f4-113">4.8</span><span class="sxs-lookup"><span data-stu-id="f21f4-113">4.8</span></span>|
|<span data-ttu-id="f21f4-114">형식</span><span class="sxs-lookup"><span data-stu-id="f21f4-114">Type</span></span>|<span data-ttu-id="f21f4-115">런타임</span><span class="sxs-lookup"><span data-stu-id="f21f4-115">Runtime</span></span>|
