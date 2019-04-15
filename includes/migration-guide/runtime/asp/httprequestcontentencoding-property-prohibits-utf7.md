---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235428"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="45868-101">HttpRequest.ContentEncoding 속성에 UTF7이 금지됨</span><span class="sxs-lookup"><span data-stu-id="45868-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="45868-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="45868-102">Details</span></span>|<span data-ttu-id="45868-103">.NET Framework 4.5부터 <xref:System.Web.HttpRequest?displayProperty=name>의 본문에 UTF-7 인코딩이 금지됩니다.</span><span class="sxs-lookup"><span data-stu-id="45868-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="45868-104">경우에 따라 UTF-7 수신 데이터에 종속되는 애플리케이션 데이터가 제대로 디코딩되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="45868-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="45868-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="45868-105">Suggestion</span></span>|<span data-ttu-id="45868-106">이상적으로는 <xref:System.Web.HttpRequest?displayProperty=name>에서 인코딩 UTF-7을 사용하지 않도록 애플리케이션을 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45868-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="45868-107">대신에 [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) 요소의 <code>aspnet:AllowUtf7RequestContentEncoding</code> 특성을 사용하여 레거시 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45868-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="45868-108">범위</span><span class="sxs-lookup"><span data-stu-id="45868-108">Scope</span></span>|<span data-ttu-id="45868-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="45868-109">Edge</span></span>|
|<span data-ttu-id="45868-110">버전</span><span class="sxs-lookup"><span data-stu-id="45868-110">Version</span></span>|<span data-ttu-id="45868-111">4.5</span><span class="sxs-lookup"><span data-stu-id="45868-111">4.5</span></span>|
|<span data-ttu-id="45868-112">형식</span><span class="sxs-lookup"><span data-stu-id="45868-112">Type</span></span>|<span data-ttu-id="45868-113">런타임</span><span class="sxs-lookup"><span data-stu-id="45868-113">Runtime</span></span>|
|<span data-ttu-id="45868-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="45868-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
