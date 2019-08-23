---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: 0316e983446644671ead2f8f843dc91b493b29c9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933167"
---
# <a name="namespacetable"></a><span data-ttu-id="c3205-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="c3205-101">\<namespaceTable></span></span>

<span data-ttu-id="c3205-102">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3205-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="c3205-103">**\<system.serviceModel>**  </span><span class="sxs-lookup"><span data-stu-id="c3205-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="c3205-104">&nbsp;&nbsp; **\<routing>**  </span><span class="sxs-lookup"><span data-stu-id="c3205-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="c3205-105">&nbsp;&nbsp;&nbsp;&nbsp; **\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="c3205-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="c3205-106">구문</span><span class="sxs-lookup"><span data-stu-id="c3205-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3205-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c3205-107">Attributes and elements</span></span>

<span data-ttu-id="c3205-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3205-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c3205-109">특성</span><span class="sxs-lookup"><span data-stu-id="c3205-109">Attributes</span></span>

<span data-ttu-id="c3205-110">없음</span><span class="sxs-lookup"><span data-stu-id="c3205-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="c3205-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c3205-111">Child elements</span></span>

|     | <span data-ttu-id="c3205-112">설명</span><span class="sxs-lookup"><span data-stu-id="c3205-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c3205-113"> **\<filter>** </span><span class="sxs-lookup"><span data-stu-id="c3205-113">**\<filter>**</span></span>](filter.md) | <span data-ttu-id="c3205-114">XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c3205-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="c3205-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c3205-115">Parent elements</span></span>

|     | <span data-ttu-id="c3205-116">Description</span><span class="sxs-lookup"><span data-stu-id="c3205-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="c3205-117"> **\<routing>** </span><span class="sxs-lookup"><span data-stu-id="c3205-117">**\<routing>**</span></span>](routing.md) | <span data-ttu-id="c3205-118">들어오는 메시지를 평가할 때 사용 되는 WCF<xref:System.ServiceModel.Dispatcher.MessageFilter> (Windows Communication Foundation 형식 및 대상 끝점을 정의 하는 라우팅 테이블을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다. 필터가 일치 하는 경우에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3205-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="c3205-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3205-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
