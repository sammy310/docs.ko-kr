---
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850548"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="229b7-102">\<backupList>의 \<add></span><span class="sxs-lookup"><span data-stu-id="229b7-102">\<add> of \<backupList></span></span>
<span data-ttu-id="229b7-103">백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="229b7-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="229b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="229b7-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="229b7-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="229b7-105">Attributes and Elements</span></span>  
 <span data-ttu-id="229b7-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="229b7-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="229b7-107">특성</span><span class="sxs-lookup"><span data-stu-id="229b7-107">Attributes</span></span>  
  
|<span data-ttu-id="229b7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="229b7-108">Attribute</span></span>|<span data-ttu-id="229b7-109">Description</span><span class="sxs-lookup"><span data-stu-id="229b7-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="229b7-110">name</span><span class="sxs-lookup"><span data-stu-id="229b7-110">name</span></span>|<span data-ttu-id="229b7-111">백업 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="229b7-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="229b7-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="229b7-112">Child Elements</span></span>  
 <span data-ttu-id="229b7-113">없음</span><span class="sxs-lookup"><span data-stu-id="229b7-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="229b7-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="229b7-114">Parent Elements</span></span>  
  
|<span data-ttu-id="229b7-115">요소</span><span class="sxs-lookup"><span data-stu-id="229b7-115">Element</span></span>|<span data-ttu-id="229b7-116">Description</span><span class="sxs-lookup"><span data-stu-id="229b7-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="229b7-117">라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트의 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="229b7-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="229b7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="229b7-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
