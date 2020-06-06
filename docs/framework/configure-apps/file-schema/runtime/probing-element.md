---
title: <probing> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/probing
- http://schemas.microsoft.com/.NetConfiguration/v2.0#probing
helpviewer_keywords:
- <probing> element
- container tags, <probing> element
- probing element
ms.assetid: 09c80fc9-1ba5-4192-89f7-3a79b2e4b024
ms.openlocfilehash: e9e48ea97e1b70fef7fcc78a113e18c5fec23b7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115859"
---
# <a name="probing-element"></a><span data-ttu-id="c3a57-102">\<probing> 요소</span><span class="sxs-lookup"><span data-stu-id="c3a57-102">\<probing> Element</span></span>
<span data-ttu-id="c3a57-103">어셈블리를 로드할 때 검색할 공용 언어 런타임에 대 한 응용 프로그램 기본 하위 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-103">Specifies application base subdirectories for the common language runtime to search when loading assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<probing>**  
  
## <a name="syntax"></a><span data-ttu-id="c3a57-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3a57-104">Syntax</span></span>  
  
```xml  
<probing privatePath="paths"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c3a57-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c3a57-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c3a57-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c3a57-107">특성</span><span class="sxs-lookup"><span data-stu-id="c3a57-107">Attributes</span></span>  
  
|<span data-ttu-id="c3a57-108">attribute</span><span class="sxs-lookup"><span data-stu-id="c3a57-108">Attribute</span></span>|<span data-ttu-id="c3a57-109">Description</span><span class="sxs-lookup"><span data-stu-id="c3a57-109">Description</span></span>|  
|---------------|-----------------|  
|`privatePath`|<span data-ttu-id="c3a57-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="c3a57-111">어셈블리를 포함할 수 있는 응용 프로그램 기본 디렉터리의 하위 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-111">Specifies subdirectories of the application's base directory that might contain assemblies.</span></span> <span data-ttu-id="c3a57-112">각 하위 디렉터리를 세미콜론으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-112">Delimit each subdirectory with a semicolon.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c3a57-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c3a57-113">Child Elements</span></span>  

<span data-ttu-id="c3a57-114">없음</span><span class="sxs-lookup"><span data-stu-id="c3a57-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c3a57-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c3a57-115">Parent Elements</span></span>  
  
|<span data-ttu-id="c3a57-116">요소</span><span class="sxs-lookup"><span data-stu-id="c3a57-116">Element</span></span>|<span data-ttu-id="c3a57-117">Description</span><span class="sxs-lookup"><span data-stu-id="c3a57-117">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="c3a57-118">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-118">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="c3a57-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="c3a57-120">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-120">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c3a57-121">예제</span><span class="sxs-lookup"><span data-stu-id="c3a57-121">Example</span></span>  
 <span data-ttu-id="c3a57-122">다음 예제에서는 런타임에서 어셈블리를 검색 해야 하는 응용 프로그램 기본 하위 디렉터리를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3a57-122">The following example shows how to specify application base subdirectories the runtime should search for assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3a57-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3a57-123">See also</span></span>

- [<span data-ttu-id="c3a57-124">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c3a57-124">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="c3a57-125">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c3a57-125">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="c3a57-126">어셈블리 위치 지정</span><span class="sxs-lookup"><span data-stu-id="c3a57-126">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="c3a57-127">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="c3a57-127">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
