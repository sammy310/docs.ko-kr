---
ms.openlocfilehash: 57f68c10d5d1edc9b8deaca2f4fe7edda2dd69b0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620396"
---
### <a name="systemservicemodelwebwebservicehost-object-no-longer-adds-a-default-endpoint"></a><span data-ttu-id="6239b-101">System.ServiceModel.Web.WebServiceHost 개체는 더 이상 기본 엔드포인트를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6239b-101">System.ServiceModel.Web.WebServiceHost object no longer adds a default endpoint</span></span>

#### <a name="details"></a><span data-ttu-id="6239b-102">설명</span><span class="sxs-lookup"><span data-stu-id="6239b-102">Details</span></span>

<span data-ttu-id="6239b-103">애플리케이션 코드를 통해 명시적 엔드포인트를 추가한 경우에는 <xref:System.ServiceModel.Web.WebServiceHost> 개체가 더 이상 기본 엔드포인트를 추가하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6239b-103">The <xref:System.ServiceModel.Web.WebServiceHost> object no longer adds a default endpoint if an explicit endpoint has been added by application code.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6239b-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="6239b-104">Suggestion</span></span>

<span data-ttu-id="6239b-105">사용자가 기본 엔드포인트에 연결할 수 있어야 하고 다른 명시적 엔드포인트가 <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>에 추가된 경우, 기본 엔드포인트를 명시적으로(<xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName> 사용) 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6239b-105">If users will expect to be able to connect to a default endpoint and other explicit endpoints have been added to the <xref:System.ServiceModel.Web.WebServiceHost?displayProperty=fullName>, default endpoints should also be added explicitly (using <xref:System.ServiceModel.ServiceHostBase.AddDefaultEndpoints?displayProperty=fullName>).</span></span>

| <span data-ttu-id="6239b-106">이름</span><span class="sxs-lookup"><span data-stu-id="6239b-106">Name</span></span>    | <span data-ttu-id="6239b-107">값</span><span class="sxs-lookup"><span data-stu-id="6239b-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6239b-108">Scope</span><span class="sxs-lookup"><span data-stu-id="6239b-108">Scope</span></span>   |<span data-ttu-id="6239b-109">부</span><span class="sxs-lookup"><span data-stu-id="6239b-109">Minor</span></span>|
|<span data-ttu-id="6239b-110">버전</span><span class="sxs-lookup"><span data-stu-id="6239b-110">Version</span></span>|<span data-ttu-id="6239b-111">4.5</span><span class="sxs-lookup"><span data-stu-id="6239b-111">4.5</span></span>|
|<span data-ttu-id="6239b-112">형식</span><span class="sxs-lookup"><span data-stu-id="6239b-112">Type</span></span>|<span data-ttu-id="6239b-113">런타임</span><span class="sxs-lookup"><span data-stu-id="6239b-113">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6239b-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="6239b-114">Affected APIs</span></span>

-<xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHost.AddServiceEndpoint(System.Type,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.ServiceModel.Description.ServiceEndpoint)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.String,System.Uri)?displayProperty=nameWithType></li><li><xref:System.ServiceModel.ServiceHostBase.AddServiceEndpoint(System.String,System.ServiceModel.Channels.Binding,System.Uri,System.Uri)?displayProperty=nameWithType></li></ul>|
