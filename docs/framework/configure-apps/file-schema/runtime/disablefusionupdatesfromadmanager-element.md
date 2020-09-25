---
title: <disableFusionUpdatesFromADManager> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- disableFusionUpdatesFromADManager element
- <disableFusionUpdatesFromADManager> element
ms.assetid: 58d2866c-37bd-4ffa-abaf-ff35926a2939
ms.openlocfilehash: c3971379b358ae16fc463df2b8d6288cf8881391
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91205037"
---
# <a name="disablefusionupdatesfromadmanager-element"></a><span data-ttu-id="9b366-102">\<disableFusionUpdatesFromADManager> 요소</span><span class="sxs-lookup"><span data-stu-id="9b366-102">\<disableFusionUpdatesFromADManager> Element</span></span>

<span data-ttu-id="9b366-103">런타임 호스트가 애플리케이션 도메인에 대한 구성 설정을 재정의할 수 있도록 허용하는 기본 동작을 사용하지 않도록 설정할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-103">Specifies whether the default behavior, which is to allow the runtime host to override configuration settings for an application domain, is disabled.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableFusionUpdatesFromADManager>**  
  
## <a name="syntax"></a><span data-ttu-id="9b366-104">구문</span><span class="sxs-lookup"><span data-stu-id="9b366-104">Syntax</span></span>  
  
```xml  
<disableFusionUpdatesFromADManager enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9b366-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9b366-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9b366-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9b366-107">특성</span><span class="sxs-lookup"><span data-stu-id="9b366-107">Attributes</span></span>  
  
|<span data-ttu-id="9b366-108">attribute</span><span class="sxs-lookup"><span data-stu-id="9b366-108">Attribute</span></span>|<span data-ttu-id="9b366-109">설명</span><span class="sxs-lookup"><span data-stu-id="9b366-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9b366-110">사용</span><span class="sxs-lookup"><span data-stu-id="9b366-110">enabled</span></span>|<span data-ttu-id="9b366-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="9b366-112">Fusion 설정을 재정의 하는 기본 기능을 사용할 수 없는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-112">Specifies whether the default ability to override Fusion settings is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="9b366-113">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="9b366-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="9b366-114">Value</span><span class="sxs-lookup"><span data-stu-id="9b366-114">Value</span></span>|<span data-ttu-id="9b366-115">설명</span><span class="sxs-lookup"><span data-stu-id="9b366-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9b366-116">0</span><span class="sxs-lookup"><span data-stu-id="9b366-116">0</span></span>|<span data-ttu-id="9b366-117">Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="9b366-117">Do not disable the ability to override Fusion settings.</span></span> <span data-ttu-id="9b366-118">이는 .NET Framework 4부터 시작 하는 기본 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-118">This is the default behavior, starting with the .NET Framework 4.</span></span>|  
|<span data-ttu-id="9b366-119">1</span><span class="sxs-lookup"><span data-stu-id="9b366-119">1</span></span>|<span data-ttu-id="9b366-120">Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-120">Disable the ability to override Fusion settings.</span></span> <span data-ttu-id="9b366-121">이는 이전 버전의 .NET Framework 동작으로 되돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-121">This reverts to the behavior of earlier versions of the .NET Framework.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9b366-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9b366-122">Child Elements</span></span>  

 <span data-ttu-id="9b366-123">없음</span><span class="sxs-lookup"><span data-stu-id="9b366-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9b366-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9b366-124">Parent Elements</span></span>  
  
|<span data-ttu-id="9b366-125">요소</span><span class="sxs-lookup"><span data-stu-id="9b366-125">Element</span></span>|<span data-ttu-id="9b366-126">설명</span><span class="sxs-lookup"><span data-stu-id="9b366-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9b366-127">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9b366-128">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-128">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9b366-129">설명</span><span class="sxs-lookup"><span data-stu-id="9b366-129">Remarks</span></span>  

 <span data-ttu-id="9b366-130">.NET Framework 4부터 기본 동작은 <xref:System.AppDomainManager> <xref:System.AppDomainSetup.ConfigurationFile%2A> <xref:System.AppDomainSetup.SetConfigurationBytes%2A> <xref:System.AppDomainSetup> <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> 의 서브 클래스에서 메서드 구현에 전달 되는 개체의 속성이 나 메서드를 사용 하 여 개체가 구성 설정을 재정의할 수 있도록 하는 것입니다 <xref:System.AppDomainManager> .</span><span class="sxs-lookup"><span data-stu-id="9b366-130">Starting with the .NET Framework 4, the default behavior is to allow the <xref:System.AppDomainManager> object to override configuration settings by using the <xref:System.AppDomainSetup.ConfigurationFile%2A> property or the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method of the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method, in your subclass of <xref:System.AppDomainManager>.</span></span> <span data-ttu-id="9b366-131">기본 응용 프로그램 도메인의 경우 변경 하는 설정이 응용 프로그램 구성 파일에 지정 된 설정을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-131">For the default application domain, the settings you change override the settings that were specified by the application configuration file.</span></span> <span data-ttu-id="9b366-132">다른 응용 프로그램 도메인의 경우 또는 메서드에 전달 된 구성 설정을 재정의 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-132">For other application domains, they override the configuration settings that were passed to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9b366-133">새 구성 정보를 전달 하거나 null (Visual Basic)을 전달 `Nothing` 하 여 전달 된 구성 정보를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-133">You can either pass new configuration information, or pass null (`Nothing` in Visual Basic) to eliminate configuration information that was passed in.</span></span>  
  
 <span data-ttu-id="9b366-134">구성 정보를 속성과 메서드에 전달 하지 마십시오 <xref:System.AppDomainSetup.ConfigurationFile%2A> <xref:System.AppDomainSetup.SetConfigurationBytes%2A> .</span><span class="sxs-lookup"><span data-stu-id="9b366-134">Do not pass configuration information to both the <xref:System.AppDomainSetup.ConfigurationFile%2A> property and the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method.</span></span> <span data-ttu-id="9b366-135">구성 정보를 둘 다에 전달 하는 경우 <xref:System.AppDomainSetup.ConfigurationFile%2A> <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 메서드가 응용 프로그램 구성 파일에서 구성 정보를 재정의 하기 때문에 속성에 전달 하는 정보는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-135">If you pass configuration information to both, the information you pass to the <xref:System.AppDomainSetup.ConfigurationFile%2A> property is ignored, because the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method overrides configuration information from the application configuration file.</span></span> <span data-ttu-id="9b366-136">속성을 사용 하는 경우 <xref:System.AppDomainSetup.ConfigurationFile%2A> 메서드에 null (Visual Basic)을 전달 하 여 `Nothing` <xref:System.AppDomainSetup.SetConfigurationBytes%2A> 또는 메서드에 대 한 호출에 지정 된 모든 구성 바이트를 제거할 수 있습니다 <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9b366-136">If you use the <xref:System.AppDomainSetup.ConfigurationFile%2A> property, you can pass null (`Nothing` in Visual Basic) to the <xref:System.AppDomainSetup.SetConfigurationBytes%2A> method to eliminate any configuration bytes that were specified in the call to the <xref:System.AppDomainManager.CreateDomain%2A?displayProperty=nameWithType> or <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="9b366-137">구성 정보 외에,,,,,,,,,,,, <xref:System.AppDomainSetup> <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> <xref:System.AppDomainSetup.ApplicationBase%2A> <xref:System.AppDomainSetup.ApplicationName%2A> <xref:System.AppDomainSetup.CachePath%2A> <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A> <xref:System.AppDomainSetup.DisallowBindingRedirects%2A> <xref:System.AppDomainSetup.DisallowCodeDownload%2A> <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A> <xref:System.AppDomainSetup.DynamicBase%2A> <xref:System.AppDomainSetup.LoaderOptimization%2A> <xref:System.AppDomainSetup.PrivateBinPath%2A> <xref:System.AppDomainSetup.PrivateBinPathProbe%2A> <xref:System.AppDomainSetup.ShadowCopyDirectories%2A> 및 <xref:System.AppDomainSetup.ShadowCopyFiles%2A> 메서드의 구현에 전달 되는 개체에 대 한 다음 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-137">In addition to configuration information, you can change the following settings on the <xref:System.AppDomainSetup> object that is passed to your implementation of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method: <xref:System.AppDomainSetup.ApplicationBase%2A>, <xref:System.AppDomainSetup.ApplicationName%2A>, <xref:System.AppDomainSetup.CachePath%2A>, <xref:System.AppDomainSetup.DisallowApplicationBaseProbing%2A>, <xref:System.AppDomainSetup.DisallowBindingRedirects%2A>, <xref:System.AppDomainSetup.DisallowCodeDownload%2A>, <xref:System.AppDomainSetup.DisallowPublisherPolicy%2A>, <xref:System.AppDomainSetup.DynamicBase%2A>, <xref:System.AppDomainSetup.LoaderOptimization%2A>, <xref:System.AppDomainSetup.PrivateBinPath%2A>, <xref:System.AppDomainSetup.PrivateBinPathProbe%2A>, <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, and <xref:System.AppDomainSetup.ShadowCopyFiles%2A>.</span></span>  
  
 <span data-ttu-id="9b366-138">요소를 사용 하는 대신 `<disableFusionUpdatesFromADManager>` 레지스트리 설정을 만들거나 환경 변수를 설정 하 여 기본 동작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-138">As an alternative to using the `<disableFusionUpdatesFromADManager>` element, you can disable the default behavior by creating a registry setting or by setting an environment variable.</span></span> <span data-ttu-id="9b366-139">레지스트리에서 또는 아래에 라는 DWORD 값을 만들고 `COMPLUS_disableFusionUpdatesFromADManager` `HKCU\Software\Microsoft\.NETFramework` 값을 `HKLM\Software\Microsoft\.NETFramework` 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b366-139">In the registry, create a DWORD value named `COMPLUS_disableFusionUpdatesFromADManager` under `HKCU\Software\Microsoft\.NETFramework` or `HKLM\Software\Microsoft\.NETFramework`, and set the value to 1.</span></span> <span data-ttu-id="9b366-140">명령줄에서 환경 변수를 1로 설정 합니다 `COMPLUS_disableFusionUpdatesFromADManager` .</span><span class="sxs-lookup"><span data-stu-id="9b366-140">At the command line, set the environment variable `COMPLUS_disableFusionUpdatesFromADManager` to 1.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b366-141">예제</span><span class="sxs-lookup"><span data-stu-id="9b366-141">Example</span></span>  

 <span data-ttu-id="9b366-142">다음 예제에서는 요소를 사용 하 여 Fusion 설정을 재정의 하는 기능을 사용 하지 않도록 설정 하는 방법을 보여 줍니다 `<disableFusionUpdatesFromADManager>` .</span><span class="sxs-lookup"><span data-stu-id="9b366-142">The following example shows how to disable the ability to override Fusion settings by using the `<disableFusionUpdatesFromADManager>` element.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableFusionUpdatesFromADManager enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b366-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b366-143">See also</span></span>

- [<span data-ttu-id="9b366-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9b366-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9b366-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9b366-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9b366-146">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="9b366-146">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
