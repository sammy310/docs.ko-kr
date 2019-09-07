---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400016"
---
# <a name="protocolmapping"></a><span data-ttu-id="904dc-101">\<protocolMapping></span><span class="sxs-lookup"><span data-stu-id="904dc-101">\<protocolMapping></span></span>
<span data-ttu-id="904dc-102">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등)와 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="904dc-103">런타임에 기본 끝점을 만들 때 WCF (Windows Communication Foundation)는 구성 된 매핑을 보고 특정 기반 주소에 사용할 바인딩을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
<span data-ttu-id="904dc-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="904dc-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="904dc-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="904dc-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="904dc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<protocolMapping >**</span><span class="sxs-lookup"><span data-stu-id="904dc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="904dc-107">구문</span><span class="sxs-lookup"><span data-stu-id="904dc-107">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="904dc-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="904dc-108">Attributes and Elements</span></span>  
 <span data-ttu-id="904dc-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="904dc-110">특성</span><span class="sxs-lookup"><span data-stu-id="904dc-110">Attributes</span></span>  
 <span data-ttu-id="904dc-111">없음</span><span class="sxs-lookup"><span data-stu-id="904dc-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="904dc-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="904dc-112">Child Elements</span></span>  
  
|<span data-ttu-id="904dc-113">요소</span><span class="sxs-lookup"><span data-stu-id="904dc-113">Element</span></span>|<span data-ttu-id="904dc-114">설명</span><span class="sxs-lookup"><span data-stu-id="904dc-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="904dc-115">\<필터></span><span class="sxs-lookup"><span data-stu-id="904dc-115">\<filters></span></span>](filters-of-routing.md)|<span data-ttu-id="904dc-116">전송 프로토콜 체계 (예: http, net.tcp, net.pipe 등)와 WCF 바인딩 간의 기본 프로토콜 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-116">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="904dc-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="904dc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="904dc-118">요소</span><span class="sxs-lookup"><span data-stu-id="904dc-118">Element</span></span>|<span data-ttu-id="904dc-119">설명</span><span class="sxs-lookup"><span data-stu-id="904dc-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="904dc-120">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="904dc-120">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="904dc-121">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-121">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="904dc-122">예제</span><span class="sxs-lookup"><span data-stu-id="904dc-122">Example</span></span>  
 <span data-ttu-id="904dc-123">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-123">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="904dc-124">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-124">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="904dc-125">또는 애플리케이션 범위 내에서 기본 매핑을 재정의하려는 경우 해당 애플리케이션 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="904dc-125">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="904dc-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="904dc-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
