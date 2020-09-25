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
ms.openlocfilehash: ddcabb831193baee30016f663f32d8562283d936
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205024"
---
# <a name="developmentmode-element"></a><span data-ttu-id="b47ce-102">\<developmentMode> 요소</span><span class="sxs-lookup"><span data-stu-id="b47ce-102">\<developmentMode> Element</span></span>

<span data-ttu-id="b47ce-103">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-103">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<developmentMode>**  
  
## <a name="syntax"></a><span data-ttu-id="b47ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="b47ce-104">Syntax</span></span>  
  
```xml  
<developmentMode developerInstallation="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b47ce-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="b47ce-105">Attributes and Elements</span></span>  

 <span data-ttu-id="b47ce-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b47ce-107">특성</span><span class="sxs-lookup"><span data-stu-id="b47ce-107">Attributes</span></span>  
  
|<span data-ttu-id="b47ce-108">attribute</span><span class="sxs-lookup"><span data-stu-id="b47ce-108">Attribute</span></span>|<span data-ttu-id="b47ce-109">설명</span><span class="sxs-lookup"><span data-stu-id="b47ce-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b47ce-110">**developerInstallation**</span><span class="sxs-lookup"><span data-stu-id="b47ce-110">**developerInstallation**</span></span>|<span data-ttu-id="b47ce-111">런타임이 DEVPATH 환경 변수로 지정된 디렉터리에서 어셈블리를 검색할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-111">Specifies whether the runtime searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
  
## <a name="developerinstallation-attribute"></a><span data-ttu-id="b47ce-112">developerInstallation 특성</span><span class="sxs-lookup"><span data-stu-id="b47ce-112">developerInstallation Attribute</span></span>  
  
|<span data-ttu-id="b47ce-113">Value</span><span class="sxs-lookup"><span data-stu-id="b47ce-113">Value</span></span>|<span data-ttu-id="b47ce-114">설명</span><span class="sxs-lookup"><span data-stu-id="b47ce-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b47ce-115">**true**</span><span class="sxs-lookup"><span data-stu-id="b47ce-115">**true**</span></span>|<span data-ttu-id="b47ce-116">DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-116">Searches for assemblies in directories specified by the DEVPATH environment variable.</span></span>|  
|<span data-ttu-id="b47ce-117">**false**</span><span class="sxs-lookup"><span data-stu-id="b47ce-117">**false**</span></span>|<span data-ttu-id="b47ce-118">는 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-118">Does not search for assemblies in directories specified by the DEVPATH environment variable.</span></span> <span data-ttu-id="b47ce-119">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-119">This is the default</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b47ce-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b47ce-120">Child Elements</span></span>  

 <span data-ttu-id="b47ce-121">없음</span><span class="sxs-lookup"><span data-stu-id="b47ce-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b47ce-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b47ce-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b47ce-123">요소</span><span class="sxs-lookup"><span data-stu-id="b47ce-123">Element</span></span>|<span data-ttu-id="b47ce-124">설명</span><span class="sxs-lookup"><span data-stu-id="b47ce-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b47ce-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b47ce-126">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-126">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b47ce-127">설명</span><span class="sxs-lookup"><span data-stu-id="b47ce-127">Remarks</span></span>  

 <span data-ttu-id="b47ce-128">이 설정은 개발 시에만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-128">Use this setting only at development time.</span></span> <span data-ttu-id="b47ce-129">런타임은 DEVPATH에서 찾은 강력한 이름의 어셈블리에 대 한 버전을 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-129">The runtime does not check the versions on strong-named assemblies found in the DEVPATH.</span></span> <span data-ttu-id="b47ce-130">단순히 찾은 첫 번째 어셈블리를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-130">It simply uses the first assembly it finds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b47ce-131">예제</span><span class="sxs-lookup"><span data-stu-id="b47ce-131">Example</span></span>  

 <span data-ttu-id="b47ce-132">다음 예제에서는 런타임이 DEVPATH 환경 변수로 지정 된 디렉터리에서 어셈블리를 검색 하도록 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b47ce-132">The following example shows how to cause the runtime to search for assemblies in directories specified by the DEVPATH environment variable.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <developmentMode developerInstallation="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b47ce-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b47ce-133">See also</span></span>

- [<span data-ttu-id="b47ce-134">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="b47ce-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b47ce-135">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b47ce-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="b47ce-136">방법: DEVPATH를 사용하여 어셈블리 찾기</span><span class="sxs-lookup"><span data-stu-id="b47ce-136">How to: Locate Assemblies by Using DEVPATH</span></span>](../../how-to-locate-assemblies-by-using-devpath.md)
