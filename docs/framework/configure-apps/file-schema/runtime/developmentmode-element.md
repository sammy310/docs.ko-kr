---
description: '다음에 대 한 자세한 정보: <developmentMode> 요소'
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
ms.openlocfilehash: 668461d13c8a1767268692804e9783bb6d4b9a56
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787125"
---
# <a name="developmentmode-element"></a><span data-ttu-id="eafdb-103">\<developmentMode> 요소</span><span class="sxs-lookup"><span data-stu-id="eafdb-103">\<developmentMode> Element</span></span>

<span data-ttu-id="eafdb-104">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-104">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="eafdb-105">구문</span><span class="sxs-lookup"><span data-stu-id="eafdb-105">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eafdb-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eafdb-106">Attributes and Elements</span></span>  

 <span data-ttu-id="eafdb-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eafdb-108">특성</span><span class="sxs-lookup"><span data-stu-id="eafdb-108">Attributes</span></span>  
  
|<span data-ttu-id="eafdb-109">attribute</span><span class="sxs-lookup"><span data-stu-id="eafdb-109">Attribute</span></span>|<span data-ttu-id="eafdb-110">설명</span><span class="sxs-lookup"><span data-stu-id="eafdb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eafdb-111">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="eafdb-111">**developerInstallation**</span></span>|<span data-ttu-id="eafdb-112">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-112">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="eafdb-113">developerInstallation 특성</span><span class="sxs-lookup"><span data-stu-id="eafdb-113">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="eafdb-114">값</span><span class="sxs-lookup"><span data-stu-id="eafdb-114">Value</span></span>|<span data-ttu-id="eafdb-115">설명</span><span class="sxs-lookup"><span data-stu-id="eafdb-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eafdb-116">**true**</span><span class="sxs-lookup"><span data-stu-id="eafdb-116">**true**</span></span>|<span data-ttu-id="eafdb-117">DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-117">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="eafdb-118">**false**</span><span class="sxs-lookup"><span data-stu-id="eafdb-118">**false**</span></span>|<span data-ttu-id="eafdb-119">는 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-119">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="eafdb-120">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-120">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eafdb-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eafdb-121">Child Elements</span></span>  

 <span data-ttu-id="eafdb-122">없음</span><span class="sxs-lookup"><span data-stu-id="eafdb-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eafdb-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eafdb-123">Parent Elements</span></span>  
  
|<span data-ttu-id="eafdb-124">요소</span><span class="sxs-lookup"><span data-stu-id="eafdb-124">Element</span></span>|<span data-ttu-id="eafdb-125">설명</span><span class="sxs-lookup"><span data-stu-id="eafdb-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eafdb-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="eafdb-127">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eafdb-128">설명</span><span class="sxs-lookup"><span data-stu-id="eafdb-128">Remarks</span></span>  

 <span data-ttu-id="eafdb-129">이 설정은 개발 시에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-129">Use this setting only at development time.</span></span> <span data-ttu-id="eafdb-130">런타임은 DEVPATH에서 찾은 강력한 이름의 어셈블리에 대 한 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-130">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="eafdb-131">단순히 찾은 첫 번째 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-131">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eafdb-132">예제</span><span class="sxs-lookup"><span data-stu-id="eafdb-132">Example</span></span>  

 <span data-ttu-id="eafdb-133">다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eafdb-133">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eafdb-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eafdb-134">See also</span></span>

- [<span data-ttu-id="eafdb-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="eafdb-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eafdb-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="eafdb-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="eafdb-137">방법: DEVPATH를 사용하여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="eafdb-137">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
