---
title: <appDomainManagerType> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- appDomainManagerType element
- <appDomainManagerType> element
ms.assetid: ae8d5a7e-e7f7-47f7-98d9-455cc243a322
ms.openlocfilehash: 8eb6129b3fafaeb81a94d5a4078e41a16583a226
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154430"
---
# <a name="appdomainmanagertype-element"></a><span data-ttu-id="23113-102">\<appDomainManagerType> 요소</span><span class="sxs-lookup"><span data-stu-id="23113-102">\<appDomainManagerType> Element</span></span>
<span data-ttu-id="23113-103">기본 애플리케이션 도메인용 애플리케이션 도메인 관리자로 사용되는 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-103">Specifies the type that serves as the application domain manager for the default application domain.</span></span>  
  
<span data-ttu-id="23113-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="23113-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="23113-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="23113-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="23113-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<앱도메인관리자유형>**</span><span class="sxs-lookup"><span data-stu-id="23113-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<appDomainManagerType>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23113-107">구문</span><span class="sxs-lookup"><span data-stu-id="23113-107">Syntax</span></span>  
  
```xml  
<appDomainManagerAssembly
   value="type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23113-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="23113-108">Attributes and Elements</span></span>  
 <span data-ttu-id="23113-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23113-110">특성</span><span class="sxs-lookup"><span data-stu-id="23113-110">Attributes</span></span>  
  
|<span data-ttu-id="23113-111">attribute</span><span class="sxs-lookup"><span data-stu-id="23113-111">Attribute</span></span>|<span data-ttu-id="23113-112">Description</span><span class="sxs-lookup"><span data-stu-id="23113-112">Description</span></span>|  
|---------------|-----------------|  
|`value`|<span data-ttu-id="23113-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="23113-113">Required attribute.</span></span> <span data-ttu-id="23113-114">프로세스의 기본 응용 프로그램 도메인에 대 한 응용 프로그램 도메인 관리자 역할을 하는 네임스페이스를 포함 하 여 형식의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-114">Specifies the name of the type, including the namespace, that serves as the application domain manager for the default application domain in the process.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23113-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="23113-115">Child Elements</span></span>  
 <span data-ttu-id="23113-116">없음</span><span class="sxs-lookup"><span data-stu-id="23113-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="23113-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="23113-117">Parent Elements</span></span>  
  
|<span data-ttu-id="23113-118">요소</span><span class="sxs-lookup"><span data-stu-id="23113-118">Element</span></span>|<span data-ttu-id="23113-119">Description</span><span class="sxs-lookup"><span data-stu-id="23113-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="23113-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="23113-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="23113-121">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-121">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23113-122">설명</span><span class="sxs-lookup"><span data-stu-id="23113-122">Remarks</span></span>  
 <span data-ttu-id="23113-123">응용 프로그램 도메인 관리자의 형식을 지정하려면 이 요소와 [ \<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) 요소를 모두 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-123">To specify the type of the application domain manager, you must specify both this element and the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element.</span></span> <span data-ttu-id="23113-124">이러한 요소 중 하나를 지정하지 않으면 다른 요소는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="23113-124">If either of these elements is not specified, the other is ignored.</span></span>  
  
 <span data-ttu-id="23113-125">기본 응용 프로그램 도메인이 <xref:System.TypeLoadException> 로드될 때 [ \<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) 요소에 의해 지정된 어셈블리에 지정된 형식이 없는 경우 throw됩니다. 프로세스가 시작되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="23113-125">When the default application domain is loaded, <xref:System.TypeLoadException> is thrown if the specified type does not exist in the assembly that is specified by the [\<appDomainManagerAssembly>](appdomainmanagerassembly-element.md) element; and the process fails to start.</span></span>  
  
 <span data-ttu-id="23113-126">기본 응용 프로그램 도메인에 대한 응용 프로그램 도메인 관리자 유형을 지정하면 기본 응용 프로그램 도메인에서 만든 다른 응용 프로그램 도메인은 응용 프로그램 도메인 관리자 유형을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-126">When you specify the application domain manager type for the default application domain, other application domains created from the default application domain inherit the application domain manager type.</span></span> <span data-ttu-id="23113-127"><xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> 및 속성을 <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> 사용하여 새 응용 프로그램 도메인에 대해 다른 응용 프로그램 도메인 관리자 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-127">Use the <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType> and <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType> properties to specify a different application domain manager type for a new application domain.</span></span>  
  
 <span data-ttu-id="23113-128">응용 프로그램 도메인 관리자 유형을 지정하려면 응용 프로그램에 대한 완전한 신뢰가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-128">Specifying the application domain manager type requires the application to have full trust.</span></span> <span data-ttu-id="23113-129">(예를 들어, 데스크톱에서 실행 중인 애플리케이션에 완전 신뢰) 애플리케이션에 완전 신뢰가 없는 경우는 <xref:System.TypeLoadException> throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23113-129">(For example, an application running on the desktop has full trust.) If the application does not have full trust, a <xref:System.TypeLoadException> is thrown.</span></span>  
  
 <span data-ttu-id="23113-130">형식 및 네임스페이스의 형식은 속성에 사용되는 <xref:System.Type.FullName%2A?displayProperty=nameWithType> 형식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="23113-130">The format of the type and namespace is the same format that is used for the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="23113-131">이 구성 요소는 .NET Framework 4 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23113-131">This configuration element is available only in the .NET Framework 4 and later.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23113-132">예제</span><span class="sxs-lookup"><span data-stu-id="23113-132">Example</span></span>  
 <span data-ttu-id="23113-133">다음 예제에서는 프로세스의 기본 응용 프로그램 도메인에 대 한 응용 `MyMgr` 프로그램 `AdMgrExample` 도메인 관리자가 어셈블리의 형식임을 지정 하는 방법을 보여 주면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="23113-133">The following example shows how to specify that the application domain manager for the default application domain of a process is the `MyMgr` type in the `AdMgrExample` assembly.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <appDomainManagerType value="MyMgr" />  
      <appDomainManagerAssembly
         value="AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="23113-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23113-134">See also</span></span>

- <xref:System.AppDomainSetup.AppDomainManagerType%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.AppDomainManagerAssembly%2A?displayProperty=nameWithType>
- [<span data-ttu-id="23113-135">\<app도메인관리자어셈블리> 요소</span><span class="sxs-lookup"><span data-stu-id="23113-135">\<appDomainManagerAssembly> Element</span></span>](appdomainmanagerassembly-element.md)
- [<span data-ttu-id="23113-136">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="23113-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="23113-137">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="23113-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="23113-138">SetAppDomainManagerType 메서드</span><span class="sxs-lookup"><span data-stu-id="23113-138">SetAppDomainManagerType Method</span></span>](../../../unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)
