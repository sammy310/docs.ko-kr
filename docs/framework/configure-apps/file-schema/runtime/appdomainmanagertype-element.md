---
title: <appDomainManagerType> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154430"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="e125d-102">\<appDomainManagerType> 요소</span><span class="sxs-lookup"><span data-stu-id="e125d-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="e125d-103">기본 애플리케이션 도메인용 애플리케이션 도메인 관리자로 사용되는 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="e125d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e125d-104">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e125d-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e125d-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e125d-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e125d-107">특성</span><span class="sxs-lookup"><span data-stu-id="e125d-107">Attributes</span></span>  
  
|<span data-ttu-id="e125d-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e125d-108">Attribute</span></span>|<span data-ttu-id="e125d-109">Description</span><span class="sxs-lookup"><span data-stu-id="e125d-109">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="e125d-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-110">Required attribute.</span></span> <span data-ttu-id="e125d-111">프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 역할을 하는 네임 스페이스를 포함 한 형식의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-111">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e125d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e125d-112">Child Elements</span></span>  
 <span data-ttu-id="e125d-113">없음</span><span class="sxs-lookup"><span data-stu-id="e125d-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e125d-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e125d-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e125d-115">요소</span><span class="sxs-lookup"><span data-stu-id="e125d-115">Element</span></span>|<span data-ttu-id="e125d-116">Description</span><span class="sxs-lookup"><span data-stu-id="e125d-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e125d-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e125d-118">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-118">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e125d-119">설명</span><span class="sxs-lookup"><span data-stu-id="e125d-119">Remarks</span></span>  
 <span data-ttu-id="e125d-120">응용 프로그램 도메인 관리자의 유형을 지정 하려면이 요소와 요소를 모두 지정 해야 합니다 [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e125d-120">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="e125d-121">이러한 요소 중 하나를 지정 하지 않으면 다른 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-121">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="e125d-122">기본 응용 프로그램 도메인이 로드 되 면 <xref:System.TypeLoadException> 지정 된 형식이 요소에 지정 된 어셈블리에 없고 프로세스가 시작 되지 않으면이 throw 됩니다. [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="e125d-122">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="e125d-123">기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 유형을 지정 하는 경우 기본 응용 프로그램 도메인에서 만든 다른 응용 프로그램 도메인은 응용 프로그램 도메인 관리자 유형을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-123">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="e125d-124"><xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>및 속성을 사용 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 하 여 새 응용 프로그램 도메인에 대해 다른 응용 프로그램 도메인 관리자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-124">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="e125d-125">응용 프로그램 도메인 관리자 유형을 지정 하려면 응용 프로그램에 완전 신뢰가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-125">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="e125d-126">(예를 들어, 데스크톱에서 실행 중인 애플리케이션에 완전 신뢰) 애플리케이션에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-126">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="e125d-127">형식 및 네임 스페이스의 형식은 속성에 사용 되는 형식과 동일 합니다 <xref:System.Type.FullName%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e125d-127">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="e125d-128">이 구성 요소는 .NET Framework 4 이상 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e125d-128">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e125d-129">예제</span><span class="sxs-lookup"><span data-stu-id="e125d-129">Example</span></span>  
 <span data-ttu-id="e125d-130">다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자를 어셈블리의 형식으로 지정 하는 방법을 보여 줍니다 `MyMgr` `AdMgrExample` .</span><span class="sxs-lookup"><span data-stu-id="e125d-130">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e125d-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e125d-131">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e125d-132">\<appDomainManagerAssembly>요소인</span><span class="sxs-lookup"><span data-stu-id="e125d-132">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="e125d-133">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e125d-133">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e125d-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e125d-134">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e125d-135">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="e125d-135">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
