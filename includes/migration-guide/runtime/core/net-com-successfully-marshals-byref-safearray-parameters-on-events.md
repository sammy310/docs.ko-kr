---
ms.openlocfilehash: 2f4f92c8615b328caee2ad0b90028c76048026f4
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802625"
---
### <a name="net-com-successfully-marshals-byref-safearray-parameters-on-events"></a><span data-ttu-id="f61e9-101">.NET COM이 이벤트에 대해 ByRef SafeArray 매개 변수를 성공적으로 마샬링</span><span class="sxs-lookup"><span data-stu-id="f61e9-101">.NET COM successfully marshals ByRef SafeArray parameters on events</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f61e9-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f61e9-102">Details</span></span>|<span data-ttu-id="f61e9-103">.NET Framework 4.7.2 및 이전 버전에서 COM 이벤트에 대한 ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) 매개 변수가 네이티브 코드로 다시 마샬링하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="f61e9-103">In the .NET Framework 4.7.2 and earlier versions, a ByRef [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) parameter on a COM event would fail to marshal back to native code.</span></span>  <span data-ttu-id="f61e9-104">이 변경을 통해 이제 [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray)가 성공적으로 마샬링되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f61e9-104">With this change the [SafeArray](https://docs.microsoft.com/en-us/windows/desktop/api/oaidl/ns-oaidl-safearray) is now marshalled successfully.</span></span><ul><li><span data-ttu-id="f61e9-105">[ x ] Quirked</span><span class="sxs-lookup"><span data-stu-id="f61e9-105">[ x ] Quirked</span></span></li></ul>|
|<span data-ttu-id="f61e9-106">제안</span><span class="sxs-lookup"><span data-stu-id="f61e9-106">Suggestion</span></span>|<span data-ttu-id="f61e9-107">COM 이벤트에 대한 적절한 ByRef SafeArray 매개 변수 마샬링이 실행 중지될 경우 다음 구성 스위치를 애플리케이션 구성에 추가하여 이 코드를 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f61e9-107">If properly marshalling ByRef SafeArray parameters on COM Events breaks execution, you can disable this code by adding the following configuration switch to your application config:</span></span><pre><code class="lang-xml">&lt;appSettings&gt;&#13;&#10;&lt;add key=&quot;Switch.System.Runtime.InteropServices.DoNotMarshalOutByrefSafeArrayOnInvoke&quot; value=&quot;true&quot; /&gt;&#13;&#10;&lt;/appSettings&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="f61e9-108">범위</span><span class="sxs-lookup"><span data-stu-id="f61e9-108">Scope</span></span>|<span data-ttu-id="f61e9-109">부</span><span class="sxs-lookup"><span data-stu-id="f61e9-109">Minor</span></span>|
|<span data-ttu-id="f61e9-110">버전</span><span class="sxs-lookup"><span data-stu-id="f61e9-110">Version</span></span>|<span data-ttu-id="f61e9-111">4.8</span><span class="sxs-lookup"><span data-stu-id="f61e9-111">4.8</span></span>|
|<span data-ttu-id="f61e9-112">Type</span><span class="sxs-lookup"><span data-stu-id="f61e9-112">Type</span></span>|<span data-ttu-id="f61e9-113">런타임</span><span class="sxs-lookup"><span data-stu-id="f61e9-113">Runtime</span></span>|

