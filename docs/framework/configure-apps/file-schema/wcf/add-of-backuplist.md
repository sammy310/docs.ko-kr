---
title: <backupList>의 <add>
ms.date: 03/30/2017
ms.assetid: bc5939fc-314a-4ea4-a533-c96958da7173
ms.openlocfilehash: 6d8fd26170059226583a300b1b48b849666db929
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181624"
---
# <a name="add-of-backuplist"></a><span data-ttu-id="1a503-102">\<backupList>의 \<add></span><span class="sxs-lookup"><span data-stu-id="1a503-102">\<add> of \<backupList></span></span>

<span data-ttu-id="1a503-103">백업 엔드포인트 요소를 정의하는 구성 요소를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1a503-103">Represents a configuration element that defines a backup endpoint element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<routing>**](routing.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupLists>**](backuplists.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<backupList>**](backuplist.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  
  
## <a name="syntax"></a><span data-ttu-id="1a503-104">구문</span><span class="sxs-lookup"><span data-stu-id="1a503-104">Syntax</span></span>  
  
```xml  
<routing>
  <backupLists>
    <backupList name="String">
      <add endpointName="String" />
    </backupList>
  </backupLists>
</routing>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a503-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1a503-105">Attributes and Elements</span></span>  

 <span data-ttu-id="1a503-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1a503-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a503-107">특성</span><span class="sxs-lookup"><span data-stu-id="1a503-107">Attributes</span></span>  
  
|<span data-ttu-id="1a503-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1a503-108">Attribute</span></span>|<span data-ttu-id="1a503-109">Description</span><span class="sxs-lookup"><span data-stu-id="1a503-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1a503-110">name</span><span class="sxs-lookup"><span data-stu-id="1a503-110">name</span></span>|<span data-ttu-id="1a503-111">백업 엔드포인트의 이름을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a503-111">A string that specifies the name of the backup endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a503-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1a503-112">Child Elements</span></span>  

 <span data-ttu-id="1a503-113">없음</span><span class="sxs-lookup"><span data-stu-id="1a503-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a503-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1a503-114">Parent Elements</span></span>  
  
|<span data-ttu-id="1a503-115">요소</span><span class="sxs-lookup"><span data-stu-id="1a503-115">Element</span></span>|<span data-ttu-id="1a503-116">설명</span><span class="sxs-lookup"><span data-stu-id="1a503-116">Description</span></span>|  
|-------------|-----------------|  
|[\<routing>](routing.md)|<span data-ttu-id="1a503-117">라우팅 서비스에서 기본 엔드포인트에 도달할 수 없을 때 사용할 수 있도록 할 엔드포인트의 목록을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1a503-117">Contains a list of endpoints that you would like the Routing Service to use in case the primary endpoint can't be reached.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a503-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a503-118">See also</span></span>

- <xref:System.ServiceModel.Routing.Configuration.BackupEndpointElement?displayProperty=nameWithType>
