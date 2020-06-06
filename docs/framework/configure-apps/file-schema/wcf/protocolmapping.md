---
title: <protocolMapping>
ms.date: 03/30/2017
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
ms.openlocfilehash: be4224ef1a8b17653df8123aaf89e105a496355a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70400016"
---
# \<protocolMapping>
<span data-ttu-id="77e74-101">전송 프로토콜 체계(예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-101">Represents a configuration section for defining a set of default protocol mapping between transport protocol schemes (e.g., http, net.tcp, net.pipe, etc.) and WCF bindings.</span></span> <span data-ttu-id="77e74-102">런타임에 기본 끝점을 만들 때 WCF (Windows Communication Foundation)는 구성 된 매핑을 보고 특정 기반 주소에 사용할 바인딩을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-102">When creating default endpoints at runtime, Windows Communication Foundation (WCF) looks at the configured mappings and decides on which binding to use for a particular based address.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<protocolMapping>**  
  
## <a name="syntax"></a><span data-ttu-id="77e74-103">구문</span><span class="sxs-lookup"><span data-stu-id="77e74-103">Syntax</span></span>  
  
```xml  
<protocolMapping>
  <add binding="String"
       bindingConfiguration="String"
       scheme="http/net.msmq/net.pipe/net.tcp" />
</protocolMapping>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="77e74-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="77e74-104">Attributes and Elements</span></span>  
 <span data-ttu-id="77e74-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="77e74-106">특성</span><span class="sxs-lookup"><span data-stu-id="77e74-106">Attributes</span></span>  
 <span data-ttu-id="77e74-107">없음</span><span class="sxs-lookup"><span data-stu-id="77e74-107">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="77e74-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="77e74-108">Child Elements</span></span>  
  
|<span data-ttu-id="77e74-109">요소</span><span class="sxs-lookup"><span data-stu-id="77e74-109">Element</span></span>|<span data-ttu-id="77e74-110">Description</span><span class="sxs-lookup"><span data-stu-id="77e74-110">Description</span></span>|  
|-------------|-----------------|  
|[\<filters>](filters-of-routing.md)|<span data-ttu-id="77e74-111">전송 프로토콜 체계(예: http, net.tcp, net.pipe 등) 및 WCF 바인딩 간의 기본 프로토콜 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-111">Contains a default protocol mapping between a transport protocol scheme (e.g., http, net.tcp, net.pipe, etc.) and a WCF binding.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="77e74-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="77e74-112">Parent Elements</span></span>  
  
|<span data-ttu-id="77e74-113">요소</span><span class="sxs-lookup"><span data-stu-id="77e74-113">Element</span></span>|<span data-ttu-id="77e74-114">Description</span><span class="sxs-lookup"><span data-stu-id="77e74-114">Description</span></span>|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|<span data-ttu-id="77e74-115">모든 WCF 구성 요소의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-115">The root element of all WCF configuration elements.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="77e74-116">예제</span><span class="sxs-lookup"><span data-stu-id="77e74-116">Example</span></span>  
 <span data-ttu-id="77e74-117">다음 구성 예제는 machine.config 파일의 기본 프로토콜 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-117">The following configuration example shows the default protocol mapping in the machine.config file.</span></span> <span data-ttu-id="77e74-118">machine.config 파일을 수정하여 컴퓨터 수준에서 기본 매핑을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-118">You can override this default mapping at the machine level by modifying the machine.config file.</span></span> <span data-ttu-id="77e74-119">또는 애플리케이션 범위 내에서 기본 매핑을 재정의하려는 경우 해당 애플리케이션 구성 파일 내에서 이 섹션을 재정의하고 개별 프로토콜 체계에 대한 매핑을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e74-119">Or if you would only like to override it within the scope of an application, you can override this section within your application configuration file and change the mapping for individual protocol schemes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="77e74-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77e74-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>
- <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>
