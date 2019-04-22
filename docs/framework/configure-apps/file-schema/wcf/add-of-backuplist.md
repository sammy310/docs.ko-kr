---
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 03bf1bbb8156e4722d987e171d9034747ac6bb61
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089538"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="851a2-102">\<추가 >의 \<backupList ></span><span class="sxs-lookup"><span data-stu-id="851a2-102">\<add> of \<backupList></span></span>
<span data-ttu-id="851a2-103">백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="851a2-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="851a2-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="851a2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="851a2-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="851a2-105">\<routing></span></span>  
<span data-ttu-id="851a2-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="851a2-106">\<backupLists></span></span>  
<span data-ttu-id="851a2-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="851a2-107">\<backupList></span></span>  
<span data-ttu-id="851a2-108">\<add></span><span class="sxs-lookup"><span data-stu-id="851a2-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="851a2-109">구문</span><span class="sxs-lookup"><span data-stu-id="851a2-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
```csharp  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="851a2-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="851a2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="851a2-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="851a2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="851a2-112">특성</span><span class="sxs-lookup"><span data-stu-id="851a2-112">Attributes</span></span>  
  
|<span data-ttu-id="851a2-113">특성</span><span class="sxs-lookup"><span data-stu-id="851a2-113">Attribute</span></span>|<span data-ttu-id="851a2-114">설명</span><span class="sxs-lookup"><span data-stu-id="851a2-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="851a2-115">name</span><span class="sxs-lookup"><span data-stu-id="851a2-115">name</span></span>|<span data-ttu-id="851a2-116">백업 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="851a2-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="851a2-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="851a2-117">Child Elements</span></span>  
 <span data-ttu-id="851a2-118">없음</span><span class="sxs-lookup"><span data-stu-id="851a2-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="851a2-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="851a2-119">Parent Elements</span></span>  
  
|<span data-ttu-id="851a2-120">요소</span><span class="sxs-lookup"><span data-stu-id="851a2-120">Element</span></span>|<span data-ttu-id="851a2-121">설명</span><span class="sxs-lookup"><span data-stu-id="851a2-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="851a2-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="851a2-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="851a2-123">원하는 경우 기본 끝점에 연결할 수 없습니다를 사용 하도록 라우팅 서비스는 끝점의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="851a2-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="851a2-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="851a2-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
