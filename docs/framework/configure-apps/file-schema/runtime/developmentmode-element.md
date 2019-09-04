---
title: <developmentMode> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/developmentMode
- http://schemas.microsoft.com/.NetConfiguration/v2.0#developmentMode
helpviewer_keywords:
- developmentMode element
- container tags, <developmentMode> element
- <developmentMode> element
ms.assetid: 60e79a8c-415a-497d-be29-b9d0fd9bdee3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0253c3ced52b575097fe5d18abb8ce188c0164fb
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252692"
---
# <a name="developmentmode-element"></a><span data-ttu-id="a3477-102">\<developmentMode > 요소</span><span class="sxs-lookup"><span data-stu-id="a3477-102">\<developmentMode> Element</span></span>
<span data-ttu-id="a3477-103">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
<span data-ttu-id="a3477-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3477-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="a3477-105">&nbsp;&nbsp;[ **\<런타임 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="a3477-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="a3477-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<developmentMode>**</span><span class="sxs-lookup"><span data-stu-id="a3477-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3477-107">구문</span><span class="sxs-lookup"><span data-stu-id="a3477-107">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3477-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a3477-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a3477-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3477-110">특성</span><span class="sxs-lookup"><span data-stu-id="a3477-110">Attributes</span></span>  
  
|<span data-ttu-id="a3477-111">특성</span><span class="sxs-lookup"><span data-stu-id="a3477-111">Attribute</span></span>|<span data-ttu-id="a3477-112">설명</span><span class="sxs-lookup"><span data-stu-id="a3477-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3477-113">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="a3477-113">**developerInstallation**</span></span>|<span data-ttu-id="a3477-114">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-114">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="a3477-115">developerInstallation 특성</span><span class="sxs-lookup"><span data-stu-id="a3477-115">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="a3477-116">값</span><span class="sxs-lookup"><span data-stu-id="a3477-116">Value</span></span>|<span data-ttu-id="a3477-117">설명</span><span class="sxs-lookup"><span data-stu-id="a3477-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a3477-118">**true**</span><span class="sxs-lookup"><span data-stu-id="a3477-118">**true**</span></span>|<span data-ttu-id="a3477-119">DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-119">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="a3477-120">**false**</span><span class="sxs-lookup"><span data-stu-id="a3477-120">**false**</span></span>|<span data-ttu-id="a3477-121">는 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-121">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="a3477-122">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-122">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3477-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a3477-123">Child Elements</span></span>  
 <span data-ttu-id="a3477-124">없음</span><span class="sxs-lookup"><span data-stu-id="a3477-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3477-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a3477-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a3477-126">요소</span><span class="sxs-lookup"><span data-stu-id="a3477-126">Element</span></span>|<span data-ttu-id="a3477-127">설명</span><span class="sxs-lookup"><span data-stu-id="a3477-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a3477-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a3477-129">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3477-130">설명</span><span class="sxs-lookup"><span data-stu-id="a3477-130">Remarks</span></span>  
 <span data-ttu-id="a3477-131">이 설정은 개발 시에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-131">Use this setting only at development time.</span></span> <span data-ttu-id="a3477-132">런타임은 DEVPATH에서 찾은 강력한 이름의 어셈블리에 대 한 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-132">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="a3477-133">단순히 찾은 첫 번째 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-133">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3477-134">예제</span><span class="sxs-lookup"><span data-stu-id="a3477-134">Example</span></span>  
 <span data-ttu-id="a3477-135">다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a3477-135">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3477-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3477-136">See also</span></span>

- [<span data-ttu-id="a3477-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="a3477-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a3477-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a3477-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="a3477-139">방법: DEVPATH를 사용 하 여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="a3477-139">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
