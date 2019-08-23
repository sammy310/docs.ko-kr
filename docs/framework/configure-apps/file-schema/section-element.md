---
title: <section> element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 94f7709f4bd273515d9fcdd727354ec579c46207
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927221"
---
# <a name="section-element"></a><span data-ttu-id="989a2-102">\<section > 요소</span><span class="sxs-lookup"><span data-stu-id="989a2-102">\<section> element</span></span>

<span data-ttu-id="989a2-103">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="989a2-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="989a2-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="989a2-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="989a2-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="989a2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="989a2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="989a2-107">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="989a2-107">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="989a2-108">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="989a2-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="989a2-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup>** ](sectiongroup-element-for-configsections.md) </span><span class="sxs-lookup"><span data-stu-id="989a2-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md) </span></span>  
<span data-ttu-id="989a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<section>**</span><span class="sxs-lookup"><span data-stu-id="989a2-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="989a2-111">구문</span><span class="sxs-lookup"><span data-stu-id="989a2-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="989a2-112">필수 특성</span><span class="sxs-lookup"><span data-stu-id="989a2-112">Required attributes</span></span>

|           | <span data-ttu-id="989a2-113">설명</span><span class="sxs-lookup"><span data-stu-id="989a2-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="989a2-114">**name**</span><span class="sxs-lookup"><span data-stu-id="989a2-114">**name**</span></span>  | <span data-ttu-id="989a2-115">구성 섹션의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="989a2-116">**type**</span><span class="sxs-lookup"><span data-stu-id="989a2-116">**type**</span></span>  | <span data-ttu-id="989a2-117">구성 파일에서 섹션을 읽는 구성 섹션 처리기 클래스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="989a2-118">형식 값의 구문은 "정규화 된 섹션-클래스 이름, 단순 어셈블리 이름"입니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="989a2-119">단순 어셈블리 이름은 *.dll* 파일 확장명이 없는 루트 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="989a2-120">선택적 특성</span><span class="sxs-lookup"><span data-stu-id="989a2-120">Optional attributes</span></span>

<span data-ttu-id="989a2-121">다음 특성은 ASP.NET 응용 프로그램에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="989a2-122">구성 시스템에서는 다른 응용 프로그램 유형에 대 한 이러한 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="989a2-123">Description</span><span class="sxs-lookup"><span data-stu-id="989a2-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="989a2-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="989a2-124">**allowDefinition**</span></span> | <span data-ttu-id="989a2-125">섹션을 사용할 수 있는 구성 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="989a2-126">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-126">Use one of the following values:</span></span><br><br><span data-ttu-id="989a2-127">**마다**</span><span class="sxs-lookup"><span data-stu-id="989a2-127">**Everywhere**</span></span><br><span data-ttu-id="989a2-128">섹션을 모든 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="989a2-129">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-129">This is the default.</span></span><br><span data-ttu-id="989a2-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="989a2-130">**MachineOnly**</span></span><br><span data-ttu-id="989a2-131">컴퓨터 구성 파일 (machine.config) 에서만 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="989a2-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="989a2-132">**MachineToApplication**</span></span><br><span data-ttu-id="989a2-133">컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에서 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="989a2-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="989a2-134">**allowLocation**</span></span>   | <span data-ttu-id="989a2-135">위치 > 요소 내에서  **\<** 섹션을 사용할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="989a2-136">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-136">Use one of the following values:</span></span><br><br><span data-ttu-id="989a2-137">**true**</span><span class="sxs-lookup"><span data-stu-id="989a2-137">**true**</span></span><br><span data-ttu-id="989a2-138">Location > 요소 내  **\<** 에 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="989a2-139">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-139">This is the default.</span></span><br><span data-ttu-id="989a2-140">**false**</span><span class="sxs-lookup"><span data-stu-id="989a2-140">**false**</span></span><br><span data-ttu-id="989a2-141">에서는  **\<location >** 요소 내에서 섹션을 사용 하는 것을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="989a2-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="989a2-142">Parent elements</span></span>

|     | <span data-ttu-id="989a2-143">Description</span><span class="sxs-lookup"><span data-stu-id="989a2-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="989a2-144">configsections > 요소  **\<** </span><span class="sxs-lookup"><span data-stu-id="989a2-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="989a2-145">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="989a2-146"> **sectionGroup>\<** 요소</span><span class="sxs-lookup"><span data-stu-id="989a2-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="989a2-147">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="989a2-148">섹션 > 요소는  **\<configsections >** 또는  **\<sectionGroup >** 의 자식 요소 이지만 둘 다는 아닙니다.  **\<**</span><span class="sxs-lookup"><span data-stu-id="989a2-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="989a2-149">자식 요소</span><span class="sxs-lookup"><span data-stu-id="989a2-149">Child elements</span></span>

<span data-ttu-id="989a2-150">없음</span><span class="sxs-lookup"><span data-stu-id="989a2-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="989a2-151">설명</span><span class="sxs-lookup"><span data-stu-id="989a2-151">Remarks</span></span>

<span data-ttu-id="989a2-152">구성 섹션을 선언 하는 것은 기본적으로 구성 파일에 대 한 새 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="989a2-153">새 요소는 구성 섹션 처리기 (즉, <xref:System.Configuration.IConfigurationSectionHandler> 인터페이스를 구현 하는 클래스)가 읽는 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="989a2-154">사용자가 정의 하는 섹션의 특성 및 자식 요소는 설정을 읽는 데 사용 하는 섹션 처리기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="989a2-155">Machine.config 파일에서 구성 섹션 처리기를 선언 하면 **allowDefinition** 특성이 달리 지정 되지 않는 한 해당 컴퓨터의 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="989a2-156">예제</span><span class="sxs-lookup"><span data-stu-id="989a2-156">Example</span></span>

<span data-ttu-id="989a2-157">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" 
             allowLocation="false" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="989a2-158">구성 파일</span><span class="sxs-lookup"><span data-stu-id="989a2-158">Configuration file</span></span>

<span data-ttu-id="989a2-159">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (machine.config) 및응용 프로그램 디렉터리 수준에 없는 web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="989a2-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="989a2-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="989a2-160">See also</span></span>

- [<span data-ttu-id="989a2-161">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="989a2-161">Configuration file schema for the .NET Framework</span></span>](index.md)
