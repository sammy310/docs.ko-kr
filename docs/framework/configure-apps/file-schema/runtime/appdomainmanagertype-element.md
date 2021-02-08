---
description: '다음에 대 한 자세한 정보: <appDomainManagerType> 요소'
title: <appDomainManagerType> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 633dcce2e370bda96efc61447611519d0ed04a3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787138"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="42b9e-103">\<appDomainManagerType> 요소</span><span class="sxs-lookup"><span data-stu-id="42b9e-103">\<appDomainManagerType> Element</span></span>

<span data-ttu-id="42b9e-104">기본 애플리케이션 도메인용 애플리케이션 도메인 관리자로 사용되는 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-104">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**  
  
## <a name="syntax"></a><span data-ttu-id="42b9e-105">구문</span><span class="sxs-lookup"><span data-stu-id="42b9e-105">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="42b9e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="42b9e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="42b9e-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="42b9e-108">특성</span><span class="sxs-lookup"><span data-stu-id="42b9e-108">Attributes</span></span>  
  
|<span data-ttu-id="42b9e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="42b9e-109">Attribute</span></span>|<span data-ttu-id="42b9e-110">설명</span><span class="sxs-lookup"><span data-stu-id="42b9e-110">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="42b9e-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-111">Required attribute.</span></span> <span data-ttu-id="42b9e-112">프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 역할을 하는 네임 스페이스를 포함 한 형식의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-112">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="42b9e-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42b9e-113">Child Elements</span></span>  

 <span data-ttu-id="42b9e-114">없음</span><span class="sxs-lookup"><span data-stu-id="42b9e-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="42b9e-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42b9e-115">Parent Elements</span></span>  
  
|<span data-ttu-id="42b9e-116">요소</span><span class="sxs-lookup"><span data-stu-id="42b9e-116">Element</span></span>|<span data-ttu-id="42b9e-117">설명</span><span class="sxs-lookup"><span data-stu-id="42b9e-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="42b9e-118">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="42b9e-119">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-119">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="42b9e-120">설명</span><span class="sxs-lookup"><span data-stu-id="42b9e-120">Remarks</span></span>  

 <span data-ttu-id="42b9e-121">응용 프로그램 도메인 관리자의 유형을 지정 하려면이 요소와 요소를 모두 지정 해야 합니다 [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) .</span><span class="sxs-lookup"><span data-stu-id="42b9e-121">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="42b9e-122">이러한 요소 중 하나를 지정 하지 않으면 다른 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-122">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="42b9e-123">기본 응용 프로그램 도메인이 로드 되 면 <xref:System.TypeLoadException> 지정 된 형식이 요소에 지정 된 어셈블리에 없고 프로세스가 시작 되지 않으면이 throw 됩니다. [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="42b9e-123">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="42b9e-124">기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 유형을 지정 하는 경우 기본 응용 프로그램 도메인에서 만든 다른 응용 프로그램 도메인은 응용 프로그램 도메인 관리자 유형을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-124">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="42b9e-125"><xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>및 속성을 사용 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 하 여 새 응용 프로그램 도메인에 대해 다른 응용 프로그램 도메인 관리자 유형을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-125">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="42b9e-126">응용 프로그램 도메인 관리자 유형을 지정 하려면 응용 프로그램에 완전 신뢰가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-126">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="42b9e-127">(예를 들어, 데스크톱에서 실행 중인 애플리케이션에 완전 신뢰) 애플리케이션에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-127">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="42b9e-128">형식 및 네임 스페이스의 형식은 속성에 사용 되는 형식과 동일 합니다 <xref:System.Type.FullName%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="42b9e-128">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="42b9e-129">이 구성 요소는 .NET Framework 4 이상 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42b9e-129">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="42b9e-130">예제</span><span class="sxs-lookup"><span data-stu-id="42b9e-130">Example</span></span>  

 <span data-ttu-id="42b9e-131">다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자를 어셈블리의 형식으로 지정 하는 방법을 보여 줍니다 `MyMgr` `AdMgrExample` .</span><span class="sxs-lookup"><span data-stu-id="42b9e-131">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="42b9e-132">참조</span><span class="sxs-lookup"><span data-stu-id="42b9e-132">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="42b9e-133">\<appDomainManagerAssembly> 요소</span><span class="sxs-lookup"><span data-stu-id="42b9e-133">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="42b9e-134">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="42b9e-134">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="42b9e-135">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="42b9e-135">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="42b9e-136">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="42b9e-136">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
