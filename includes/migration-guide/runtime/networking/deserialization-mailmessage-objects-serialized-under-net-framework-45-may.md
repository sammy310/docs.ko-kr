---
ms.openlocfilehash: ad953a1562db407c04d7860c60eb5964fe6fe2ca
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620346"
---
### <a name="deserialization-of-mailmessage-objects-serialized-under-the-net-framework-45-may-fail"></a><span data-ttu-id="74fe8-101">.NET Framework 4.5에서 직렬화된 MailMessage 개체의 역직렬화가 실패할 수 있음</span><span class="sxs-lookup"><span data-stu-id="74fe8-101">Deserialization of MailMessage objects serialized under the .NET Framework 4.5 may fail</span></span>

#### <a name="details"></a><span data-ttu-id="74fe8-102">설명</span><span class="sxs-lookup"><span data-stu-id="74fe8-102">Details</span></span>

<span data-ttu-id="74fe8-103">.NET Framework 4.5부터는 <xref:System.Web.Mail.MailMessage> 개체에 비 ASCII 문자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74fe8-103">Starting with the .NET Framework 4.5, <xref:System.Web.Mail.MailMessage> objects can include non-ASCII characters.</span></span> <span data-ttu-id="74fe8-104">.NET Framework 4에서는 ASCII 문자만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="74fe8-104">In the .NET Framework 4, only ASCII characters are supported.</span></span> <span data-ttu-id="74fe8-105">ASCII가 아닌 문자를 포함하고 .NET Framework 4.5 이상에서 직렬화되는 <xref:System.Web.Mail.MailMessage> 개체는 .NET Framework 4에서 역직렬화될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74fe8-105"><xref:System.Web.Mail.MailMessage> objects that contain non-ASCII characters and that are serialized under the .NET Framework 4.5 or later cannot be deserialized under the .NET Framework 4.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="74fe8-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="74fe8-106">Suggestion</span></span>

<span data-ttu-id="74fe8-107"><xref:System.Web.Mail.MailMessage> 개체를 역직렬화할 때 코드가 예외 처리를 제공하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="74fe8-107">Ensure that your code provides exception handling when deserializing a <xref:System.Web.Mail.MailMessage> object.</span></span>

| <span data-ttu-id="74fe8-108">이름</span><span class="sxs-lookup"><span data-stu-id="74fe8-108">Name</span></span>    | <span data-ttu-id="74fe8-109">값</span><span class="sxs-lookup"><span data-stu-id="74fe8-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="74fe8-110">Scope</span><span class="sxs-lookup"><span data-stu-id="74fe8-110">Scope</span></span>   |<span data-ttu-id="74fe8-111">부</span><span class="sxs-lookup"><span data-stu-id="74fe8-111">Minor</span></span>|
|<span data-ttu-id="74fe8-112">버전</span><span class="sxs-lookup"><span data-stu-id="74fe8-112">Version</span></span>|<span data-ttu-id="74fe8-113">4.5</span><span class="sxs-lookup"><span data-stu-id="74fe8-113">4.5</span></span>|
|<span data-ttu-id="74fe8-114">형식</span><span class="sxs-lookup"><span data-stu-id="74fe8-114">Type</span></span>|<span data-ttu-id="74fe8-115">런타임</span><span class="sxs-lookup"><span data-stu-id="74fe8-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="74fe8-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="74fe8-116">Affected APIs</span></span>

-<xref:System.Web.Mail.MailMessage?displayProperty=nameWithType></li></ul>|
