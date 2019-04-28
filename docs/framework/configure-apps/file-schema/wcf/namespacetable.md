---
title: <namespaceTable>
ms.date: 03/30/2017
ms.assetid: 64801766-01b7-4c65-9ce6-70ad5af67689
ms.openlocfilehash: ee7a0c23adca883af279addf9d1f221bd4056d00
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772413"
---
# <a name="namespacetable"></a><span data-ttu-id="27cbd-101">\<namespaceTable></span><span class="sxs-lookup"><span data-stu-id="27cbd-101">\<namespaceTable></span></span>

<span data-ttu-id="27cbd-102">매핑을 앞에 붙인 다음 XPath 필터에서 라우팅에 사용할 수 있는 네임스페이스를 포함하는 요소 집합을 정의하기 위한 구성 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="27cbd-102">Represents a configuration section for defining a set of elements that contain namespace to prefix mappings that can then be used in XPath filters for routing.</span></span>

<span data-ttu-id="27cbd-103">**\<system.serviceModel>** </span><span class="sxs-lookup"><span data-stu-id="27cbd-103">**\<system.serviceModel>** </span></span>  
<span data-ttu-id="27cbd-104">&nbsp;&nbsp;**\<routing>** </span><span class="sxs-lookup"><span data-stu-id="27cbd-104">&nbsp;&nbsp;**\<routing>** </span></span>  
<span data-ttu-id="27cbd-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span><span class="sxs-lookup"><span data-stu-id="27cbd-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<namespaceTable>**</span></span>
  
## <a name="syntax"></a><span data-ttu-id="27cbd-106">구문</span><span class="sxs-lookup"><span data-stu-id="27cbd-106">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27cbd-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="27cbd-107">Attributes and elements</span></span>

<span data-ttu-id="27cbd-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27cbd-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="27cbd-109">특성</span><span class="sxs-lookup"><span data-stu-id="27cbd-109">Attributes</span></span>

<span data-ttu-id="27cbd-110">없음</span><span class="sxs-lookup"><span data-stu-id="27cbd-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="27cbd-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="27cbd-111">Child elements</span></span>

|     | <span data-ttu-id="27cbd-112">설명</span><span class="sxs-lookup"><span data-stu-id="27cbd-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="27cbd-113">**\<filter>**</span><span class="sxs-lookup"><span data-stu-id="27cbd-113">**\<filter>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md) | <span data-ttu-id="27cbd-114">XPath 식에 사용되는 네임스페이스 접두사 매핑을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="27cbd-114">Defines a namespace prefix mapping used for XPath expressions.</span></span> |

### <a name="parent-elements"></a><span data-ttu-id="27cbd-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="27cbd-115">Parent elements</span></span>

|     | <span data-ttu-id="27cbd-116">설명</span><span class="sxs-lookup"><span data-stu-id="27cbd-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="27cbd-117">**\<routing>**</span><span class="sxs-lookup"><span data-stu-id="27cbd-117">**\<routing>**</span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md) | <span data-ttu-id="27cbd-118">Windows Communication Foundation (WCF)의 형식을 결정 하는 라우팅 필터 집합을 정의 하기 위한 구성 섹션을 나타냅니다<xref:System.ServiceModel.Dispatcher.MessageFilter> 사용할 대상 끝점을 정의 하는 들어오는 메시지를 평가할 수 있을 뿐만 아니라 라우팅 테이블 필터가 일치할 때에 메시지를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="27cbd-118">Represents a configuration section for defining a set of routing filters, which determine the type of Windows Communication Foundation (WCF)<xref:System.ServiceModel.Dispatcher.MessageFilter> to be used when evaluating incoming messages, as well as routing tables that define the target endpoints to send messages to when a filter matches.</span></span> |

## <a name="see-also"></a><span data-ttu-id="27cbd-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="27cbd-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.NamespaceElementCollection?displayProperty=nameWithType>
