---
title: <protocolMapping>의 <add>
ms.date: 03/30/2017
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
ms.openlocfilehash: 6197d01665d49a7c97ac9e44251abf15faf80a8f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850383"
---
# <a name="add-of-protocolmapping"></a><span data-ttu-id="890d1-102">\<protocolMapping>의 \<add></span><span class="sxs-lookup"><span data-stu-id="890d1-102">\<add> of \<protocolMapping></span></span>
<span data-ttu-id="890d1-103">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등)와 WCF (Windows Communication Foundation) 바인딩 간의 기본 프로토콜 매핑을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-103">Represents a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a Windows Communication Foundation (WCF) binding.</span></span> <span data-ttu-id="890d1-104">런타임에 기본 끝점을 만들 때 WCF는 구성 된 매핑을 살펴보고 특정 기반 주소에 사용할 바인딩을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-104">When creating default endpoints at runtime, WCF looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<protocolMapping>**](protocolmapping.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="890d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="890d1-105">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="890d1-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="890d1-106">Attributes and Elements</span></span>  
 <span data-ttu-id="890d1-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="890d1-108">특성</span><span class="sxs-lookup"><span data-stu-id="890d1-108">Attributes</span></span>  
  
|<span data-ttu-id="890d1-109">요소</span><span class="sxs-lookup"><span data-stu-id="890d1-109">Element</span></span>|<span data-ttu-id="890d1-110">Description</span><span class="sxs-lookup"><span data-stu-id="890d1-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="890d1-111">바인딩</span><span class="sxs-lookup"><span data-stu-id="890d1-111">binding</span></span>|<span data-ttu-id="890d1-112">기본 엔드포인트를 만드는 중에 엔드포인트로 사용할 바인딩 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-112">A string that specifies the type of binding to be used for an endpoint during default endpoint creation.</span></span>|  
|<span data-ttu-id="890d1-113">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="890d1-113">bindingConfiguration</span></span>|<span data-ttu-id="890d1-114">참조할 바인딩 구성 섹션의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-114">A string that specifies the name of the binding configuration section to be referenced.</span></span>|  
|<span data-ttu-id="890d1-115">scheme</span><span class="sxs-lookup"><span data-stu-id="890d1-115">scheme</span></span>|<span data-ttu-id="890d1-116">기본 엔드포인트로 사용될 전송 프로토콜 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-116">The transport protocol scheme to be used for the default endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="890d1-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="890d1-117">Child Elements</span></span>  
 <span data-ttu-id="890d1-118">없음</span><span class="sxs-lookup"><span data-stu-id="890d1-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="890d1-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="890d1-119">Parent Elements</span></span>  
  
|<span data-ttu-id="890d1-120">요소</span><span class="sxs-lookup"><span data-stu-id="890d1-120">Element</span></span>|<span data-ttu-id="890d1-121">Description</span><span class="sxs-lookup"><span data-stu-id="890d1-121">Description</span></span>|  
|-------------|-----------------|  
|[\<protocolMapping>](protocolmapping.md)|<span data-ttu-id="890d1-122">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등)와 WCF (Windows Communication Foundation) 바인딩 간의 기본 프로토콜 매핑을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-122">Represents a configuration section for defining default protocol mappings between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and Windows Communication Foundation (WCF) bindings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="890d1-123">예제</span><span class="sxs-lookup"><span data-stu-id="890d1-123">Example</span></span>  
 <span data-ttu-id="890d1-124">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-124">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="890d1-125">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-125">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="890d1-126">또는 애플리케이션 범위 내에서 기본 매핑을 재정의하려는 경우 해당 애플리케이션 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="890d1-126">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
```xml  
<protocolMapping>
  <add scheme="http"
       binding="basicHttpBinding" />
  <add scheme="net.tcp"
       binding="netTcpBinding" />
  <add scheme="net.pipe"
       binding="netNamedPipeBinding" />
  <add scheme="net.msmq"
       binding="netMsmqBinding" />
</protocolMapping>
```  
  
## <a name="see-also"></a><span data-ttu-id="890d1-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="890d1-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
