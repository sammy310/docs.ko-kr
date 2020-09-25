---
title: <mexEndpoint>
ms.date: 03/30/2017
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
ms.openlocfilehash: e8f0e0fa2ea1606bf980fd6fa1fcd47f12c3b540
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204751"
---
# \<mexEndpoint>

<span data-ttu-id="615e2-101">이 구성 요소는 고정 IMetadataExchange 계약을 사용하여 표준 엔드포인트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="615e2-101">This configuration element defines a standard endpoint with a fixed IMetadataExchange contract.</span></span> <span data-ttu-id="615e2-102">모든 메타데이터 교환 엔드포인트가 IMetadataExchange를 계약으로 지정하므로 고유의 엔드포인트를 정의하는 대신 이 표준 지점을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="615e2-102">Since all metadata exchange endpoints specify IMetadataExchange as their contract, you can use this standard point instead of defining one for yourself.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<standardEndpoints>**](standardendpoints.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexEndpoint>**  
  
## <a name="syntax"></a><span data-ttu-id="615e2-103">구문</span><span class="sxs-lookup"><span data-stu-id="615e2-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="615e2-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="615e2-104">Attributes and Elements</span></span>  

 <span data-ttu-id="615e2-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="615e2-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="615e2-106">특성</span><span class="sxs-lookup"><span data-stu-id="615e2-106">Attributes</span></span>  
  
|<span data-ttu-id="615e2-107">attribute</span><span class="sxs-lookup"><span data-stu-id="615e2-107">Attribute</span></span>|<span data-ttu-id="615e2-108">Description</span><span class="sxs-lookup"><span data-stu-id="615e2-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="615e2-109">name</span><span class="sxs-lookup"><span data-stu-id="615e2-109">name</span></span>|<span data-ttu-id="615e2-110">표준 엔드포인트의 구성 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="615e2-110">A String that specifies the name of the configuration of the standard endpoint.</span></span> <span data-ttu-id="615e2-111">이 이름은 서비스 엔드포인트의 `endpointConfiguration` 특성에서 표준 엔드포인트를 해당 구성에 연결하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="615e2-111">The name is used in the `endpointConfiguration` attribute of the service endpoint to link a standard endpoint to its configuration.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="615e2-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="615e2-112">Child Elements</span></span>  

 <span data-ttu-id="615e2-113">없음</span><span class="sxs-lookup"><span data-stu-id="615e2-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="615e2-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="615e2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="615e2-115">요소</span><span class="sxs-lookup"><span data-stu-id="615e2-115">Element</span></span>|<span data-ttu-id="615e2-116">설명</span><span class="sxs-lookup"><span data-stu-id="615e2-116">Description</span></span>|  
|-------------|-----------------|  
|[\<standardEndpoints>](standardendpoints.md)|<span data-ttu-id="615e2-117">하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 엔드포인트인 표준 엔드포인트의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="615e2-117">A collection of standard endpoints that are pre-defined endpoints with one or more of their properties (address, binding, contract) fixed.</span></span>|
