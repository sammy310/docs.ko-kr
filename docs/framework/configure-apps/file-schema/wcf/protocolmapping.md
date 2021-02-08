---
description: 다음에 대해 자세히 알아보세요. <protocolMapping>
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: defdf3129122212dac9481dc5d8d48a0dfa94d72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786917"
---
# \<protocolMapping>

<span data-ttu-id="f571f-102">전송 프로토콜 체계(예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-102">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="f571f-103">런타임에 기본 끝점을 만들 때 WCF (Windows Communication Foundation)는 구성 된 매핑을 보고 특정 기반 주소에 사용할 바인딩을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-103">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="f571f-104">구문</span><span class="sxs-lookup"><span data-stu-id="f571f-104">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f571f-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f571f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="f571f-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f571f-107">특성</span><span class="sxs-lookup"><span data-stu-id="f571f-107">Attributes</span></span>  

 <span data-ttu-id="f571f-108">없음</span><span class="sxs-lookup"><span data-stu-id="f571f-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f571f-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f571f-109">Child Elements</span></span>  
  
|<span data-ttu-id="f571f-110">요소</span><span class="sxs-lookup"><span data-stu-id="f571f-110">Element</span></span>|<span data-ttu-id="f571f-111">설명</span><span class="sxs-lookup"><span data-stu-id="f571f-111">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="f571f-112">전송 프로토콜 체계(예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-112">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f571f-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f571f-113">Parent Elements</span></span>  
  
|<span data-ttu-id="f571f-114">요소</span><span class="sxs-lookup"><span data-stu-id="f571f-114">Element</span></span>|<span data-ttu-id="f571f-115">설명</span><span class="sxs-lookup"><span data-stu-id="f571f-115">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="f571f-116">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-116">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f571f-117">예제</span><span class="sxs-lookup"><span data-stu-id="f571f-117">Example</span></span>  

 <span data-ttu-id="f571f-118">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-118">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="f571f-119">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-119">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="f571f-120">또는 애플리케이션 범위 내에서 기본 매핑을 재정의하려는 경우 해당 애플리케이션 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f571f-120">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f571f-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f571f-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
