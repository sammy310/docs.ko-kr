---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: 7760ee4d3b118e339944317e8ec8d8217b5d909d
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855116"
---
# <a name="mexendpoint"></a><span data-ttu-id="3faeb-101">\<mexEndpoint></span><span class="sxs-lookup"><span data-stu-id="3faeb-101">\<mexEndpoint></span></span>
<span data-ttu-id="3faeb-102">이 구성 요소는 고정 IMetadataExchange 계약을 사용하여 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3faeb-102">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="3faeb-103">모든 메타데이터 교환 엔드포인트가 IMetadataExchange를 계약으로 지정하므로 고유의 엔드포인트를 정의하는 대신 이 표준 지점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3faeb-103">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
<span data-ttu-id="3faeb-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3faeb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3faeb-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="3faeb-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="3faeb-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<standardEndpoints >** ](standardendpoints.md)</span><span class="sxs-lookup"><span data-stu-id="3faeb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)</span></span>\
<span data-ttu-id="3faeb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexEndpoint >**</span><span class="sxs-lookup"><span data-stu-id="3faeb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3faeb-108">구문</span><span class="sxs-lookup"><span data-stu-id="3faeb-108">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3faeb-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3faeb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="3faeb-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3faeb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3faeb-111">특성</span><span class="sxs-lookup"><span data-stu-id="3faeb-111">Attributes</span></span>  
  
|<span data-ttu-id="3faeb-112">특성</span><span class="sxs-lookup"><span data-stu-id="3faeb-112">Attribute</span></span>|<span data-ttu-id="3faeb-113">설명</span><span class="sxs-lookup"><span data-stu-id="3faeb-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3faeb-114">name</span><span class="sxs-lookup"><span data-stu-id="3faeb-114">name</span></span>|<span data-ttu-id="3faeb-115">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3faeb-115">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="3faeb-116">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3faeb-116">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3faeb-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3faeb-117">Child Elements</span></span>  
 <span data-ttu-id="3faeb-118">없음</span><span class="sxs-lookup"><span data-stu-id="3faeb-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3faeb-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3faeb-119">Parent Elements</span></span>  
  
|<span data-ttu-id="3faeb-120">요소</span><span class="sxs-lookup"><span data-stu-id="3faeb-120">Element</span></span>|<span data-ttu-id="3faeb-121">설명</span><span class="sxs-lookup"><span data-stu-id="3faeb-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3faeb-122">\<standardEndpoints></span><span class="sxs-lookup"><span data-stu-id="3faeb-122">\<standardEndpoints></span></span>](standardendpoints.md)|<span data-ttu-id="3faeb-123">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="3faeb-123">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
