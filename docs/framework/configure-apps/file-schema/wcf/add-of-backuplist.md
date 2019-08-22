---
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 53af01a519c244376b262db1f6515a438dcc554f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663366"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="6b2d4-102">\<\<backupList > > 추가</span><span class="sxs-lookup"><span data-stu-id="6b2d4-102">\<add> of \<backupList></span></span>
<span data-ttu-id="6b2d4-103">백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6b2d4-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
 <span data-ttu-id="6b2d4-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="6b2d4-104">\<system.serviceModel></span></span>  
<span data-ttu-id="6b2d4-105">\<라우팅 ></span><span class="sxs-lookup"><span data-stu-id="6b2d4-105">\<routing></span></span>  
<span data-ttu-id="6b2d4-106">\<backupLists></span><span class="sxs-lookup"><span data-stu-id="6b2d4-106">\<backupLists></span></span>  
<span data-ttu-id="6b2d4-107">\<backupList></span><span class="sxs-lookup"><span data-stu-id="6b2d4-107">\<backupList></span></span>  
<span data-ttu-id="6b2d4-108">\<add></span><span class="sxs-lookup"><span data-stu-id="6b2d4-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b2d4-109">구문</span><span class="sxs-lookup"><span data-stu-id="6b2d4-109">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b2d4-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6b2d4-110">Attributes and Elements</span></span>  
 <span data-ttu-id="6b2d4-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2d4-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b2d4-112">특성</span><span class="sxs-lookup"><span data-stu-id="6b2d4-112">Attributes</span></span>  
  
|<span data-ttu-id="6b2d4-113">특성</span><span class="sxs-lookup"><span data-stu-id="6b2d4-113">Attribute</span></span>|<span data-ttu-id="6b2d4-114">Description</span><span class="sxs-lookup"><span data-stu-id="6b2d4-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6b2d4-115">name</span><span class="sxs-lookup"><span data-stu-id="6b2d4-115">name</span></span>|<span data-ttu-id="6b2d4-116">백업 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6b2d4-116">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6b2d4-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b2d4-117">Child Elements</span></span>  
 <span data-ttu-id="6b2d4-118">없음</span><span class="sxs-lookup"><span data-stu-id="6b2d4-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6b2d4-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b2d4-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6b2d4-120">요소</span><span class="sxs-lookup"><span data-stu-id="6b2d4-120">Element</span></span>|<span data-ttu-id="6b2d4-121">설명</span><span class="sxs-lookup"><span data-stu-id="6b2d4-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6b2d4-122">\<routing></span><span class="sxs-lookup"><span data-stu-id="6b2d4-122">\<routing></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|<span data-ttu-id="6b2d4-123">기본 끝점에 연결할 수 없는 경우 라우팅 서비스에서 사용할 끝점 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b2d4-123">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b2d4-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b2d4-124">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
