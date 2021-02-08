---
description: '다음에 대 한 자세한 정보:: <add><backupList>'
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 9855d93be011b4eaa2890c4d24392fde3b65d05a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99804077"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="014fc-103">\<backupList>의 \<add></span><span class="sxs-lookup"><span data-stu-id="014fc-103">\<add> of \<backupList></span></span>

<span data-ttu-id="014fc-104">백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="014fc-104">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="014fc-105">구문</span><span class="sxs-lookup"><span data-stu-id="014fc-105">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="014fc-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="014fc-106">Attributes and Elements</span></span>  

 <span data-ttu-id="014fc-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="014fc-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="014fc-108">특성</span><span class="sxs-lookup"><span data-stu-id="014fc-108">Attributes</span></span>  
  
|<span data-ttu-id="014fc-109">attribute</span><span class="sxs-lookup"><span data-stu-id="014fc-109">Attribute</span></span>|<span data-ttu-id="014fc-110">설명</span><span class="sxs-lookup"><span data-stu-id="014fc-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="014fc-111">name</span><span class="sxs-lookup"><span data-stu-id="014fc-111">name</span></span>|<span data-ttu-id="014fc-112">백업 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="014fc-112">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="014fc-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="014fc-113">Child Elements</span></span>  

 <span data-ttu-id="014fc-114">없음</span><span class="sxs-lookup"><span data-stu-id="014fc-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="014fc-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="014fc-115">Parent Elements</span></span>  
  
|<span data-ttu-id="014fc-116">요소</span><span class="sxs-lookup"><span data-stu-id="014fc-116">Element</span></span>|<span data-ttu-id="014fc-117">설명</span><span class="sxs-lookup"><span data-stu-id="014fc-117">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="014fc-118">라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트의 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="014fc-118">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="014fc-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="014fc-119">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
