---
description: 다음에 대해 자세히 알아보세요. <namespaceTable>
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 73bfac93fba3247c02c2d86d1482af2563015a76
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684089"
---
# \<namespaceTable>

<span data-ttu-id="446cd-102">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="446cd-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**  
  
## <a name="syntax"></a><span data-ttu-id="446cd-103">구문</span><span class="sxs-lookup"><span data-stu-id="446cd-103">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <routing>
    <namespaceTable>
      <add namespace="String"
           prefix="String" />
    </namespaceTable>
  </routing>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="446cd-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="446cd-104">Attributes and elements</span></span>

<span data-ttu-id="446cd-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="446cd-105">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="446cd-106">특성</span><span class="sxs-lookup"><span data-stu-id="446cd-106">Attributes</span></span>

<span data-ttu-id="446cd-107">None</span><span class="sxs-lookup"><span data-stu-id="446cd-107">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="446cd-108">자식 요소</span><span class="sxs-lookup"><span data-stu-id="446cd-108">Child elements</span></span>

|     | <span data-ttu-id="446cd-109">설명</span><span class="sxs-lookup"><span data-stu-id="446cd-109">Description</span></span> |
| --- | ----------- |
| [**\<filter>**](filter.md) | <span data-ttu-id="446cd-110">XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="446cd-110">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="446cd-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="446cd-111">Parent elements</span></span>

|     | <span data-ttu-id="446cd-112">설명</span><span class="sxs-lookup"><span data-stu-id="446cd-112">Description</span></span> |
| --- | ----------- |
| [**\<routing>**](routing.md) | <span data-ttu-id="446cd-113"><xref:System.ServiceModel.Dispatcher.MessageFilter>들어오는 메시지를 평가할 때 사용할 WCF (Windows Communication Foundation 유형)와 필터가 일치할 때 메시지를 보낼 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="446cd-113">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="446cd-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="446cd-114">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
