---
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 80726cc22cb56013c85c7704c28579b1337666c9
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850548"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="540a4-102">\<\<backupList > > 추가</span><span class="sxs-lookup"><span data-stu-id="540a4-102">\<add> of \<backupList></span></span>
<span data-ttu-id="540a4-103">백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="540a4-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
<span data-ttu-id="540a4-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="540a4-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="540a4-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="540a4-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="540a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<라우팅 >** ](routing.md)</span><span class="sxs-lookup"><span data-stu-id="540a4-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)</span></span>\
<span data-ttu-id="540a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupLists >** ](backuplists.md)</span><span class="sxs-lookup"><span data-stu-id="540a4-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)</span></span>\
<span data-ttu-id="540a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<backupList >** ](backuplist.md)</span><span class="sxs-lookup"><span data-stu-id="540a4-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)</span></span>\
<span data-ttu-id="540a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> 추가**</span><span class="sxs-lookup"><span data-stu-id="540a4-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="540a4-110">구문</span><span class="sxs-lookup"><span data-stu-id="540a4-110">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="540a4-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="540a4-111">Attributes and Elements</span></span>  
 <span data-ttu-id="540a4-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="540a4-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="540a4-113">특성</span><span class="sxs-lookup"><span data-stu-id="540a4-113">Attributes</span></span>  
  
|<span data-ttu-id="540a4-114">특성</span><span class="sxs-lookup"><span data-stu-id="540a4-114">Attribute</span></span>|<span data-ttu-id="540a4-115">Description</span><span class="sxs-lookup"><span data-stu-id="540a4-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="540a4-116">name</span><span class="sxs-lookup"><span data-stu-id="540a4-116">name</span></span>|<span data-ttu-id="540a4-117">백업 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="540a4-117">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="540a4-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="540a4-118">Child Elements</span></span>  
 <span data-ttu-id="540a4-119">없음</span><span class="sxs-lookup"><span data-stu-id="540a4-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="540a4-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="540a4-120">Parent Elements</span></span>  
  
|<span data-ttu-id="540a4-121">요소</span><span class="sxs-lookup"><span data-stu-id="540a4-121">Element</span></span>|<span data-ttu-id="540a4-122">Description</span><span class="sxs-lookup"><span data-stu-id="540a4-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="540a4-123">\<routing></span><span class="sxs-lookup"><span data-stu-id="540a4-123">\<routing></span></span>](routing.md)|<span data-ttu-id="540a4-124">기본 끝점에 연결할 수 없는 경우 라우팅 서비스에서 사용할 끝점 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="540a4-124">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="540a4-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="540a4-125">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
