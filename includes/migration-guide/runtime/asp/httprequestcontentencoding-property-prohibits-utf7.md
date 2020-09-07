---
ms.openlocfilehash: cf34c5df1badcfd86d8a07bafdf1b759234712e0
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496554"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="150be-101">HttpRequest.ContentEncoding 속성에 UTF7이 금지됨</span><span class="sxs-lookup"><span data-stu-id="150be-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

#### <a name="details"></a><span data-ttu-id="150be-102">설명</span><span class="sxs-lookup"><span data-stu-id="150be-102">Details</span></span>

<span data-ttu-id="150be-103">.NET Framework 4.5부터 <xref:System.Web.HttpRequest?displayProperty=fullName>의 본문에 UTF-7 인코딩이 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="150be-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=fullName>s' bodies.</span></span> <span data-ttu-id="150be-104">경우에 따라 UTF-7 수신 데이터에 종속되는 애플리케이션 데이터가 제대로 디코딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="150be-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="150be-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="150be-105">Suggestion</span></span>

<span data-ttu-id="150be-106">이상적으로는 <xref:System.Web.HttpRequest?displayProperty=fullName>에서 인코딩 UTF-7을 사용하지 않도록 애플리케이션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="150be-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=fullName>s.</span></span> <span data-ttu-id="150be-107">대신에 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 요소의 <code>aspnet:AllowUtf7RequestContentEncoding</code> 특성을 사용하여 레거시 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="150be-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>

| <span data-ttu-id="150be-108">이름</span><span class="sxs-lookup"><span data-stu-id="150be-108">Name</span></span>    | <span data-ttu-id="150be-109">값</span><span class="sxs-lookup"><span data-stu-id="150be-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="150be-110">Scope</span><span class="sxs-lookup"><span data-stu-id="150be-110">Scope</span></span>   |<span data-ttu-id="150be-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="150be-111">Edge</span></span>|
|<span data-ttu-id="150be-112">버전</span><span class="sxs-lookup"><span data-stu-id="150be-112">Version</span></span>|<span data-ttu-id="150be-113">4.5</span><span class="sxs-lookup"><span data-stu-id="150be-113">4.5</span></span>|
|<span data-ttu-id="150be-114">형식</span><span class="sxs-lookup"><span data-stu-id="150be-114">Type</span></span>|<span data-ttu-id="150be-115">런타임</span><span class="sxs-lookup"><span data-stu-id="150be-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="150be-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="150be-116">Affected APIs</span></span>

- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.ContentEncoding`

-->
