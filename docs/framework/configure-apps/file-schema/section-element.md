---
title: <section> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/section
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup/section
helpviewer_keywords:
- section Element
- <section> Element
ms.assetid: ec7d4110-2403-47ac-8218-499bfe9d5ddb
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8c1675540df6844f98572c11cfb140bff23b31a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089027"
---
# <a name="section-element"></a><span data-ttu-id="8c5c8-102">\<section > 요소</span><span class="sxs-lookup"><span data-stu-id="8c5c8-102">\<section> element</span></span>

<span data-ttu-id="8c5c8-103">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="8c5c8-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c8-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8c5c8-105">[**configSections >\<** ](configsections-element-for-configuration.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="8c5c8-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="8c5c8-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<섹션 >**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="8c5c8-107">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c8-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="8c5c8-108">[**configSections >\<** ](configsections-element-for-configuration.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="8c5c8-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="8c5c8-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sectionGroup >** ](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="8c5c8-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="8c5c8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<섹션 >**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8c5c8-111">구문</span><span class="sxs-lookup"><span data-stu-id="8c5c8-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication" 
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="8c5c8-112">필수 특성</span><span class="sxs-lookup"><span data-stu-id="8c5c8-112">Required attributes</span></span>

|           | <span data-ttu-id="8c5c8-113">설명</span><span class="sxs-lookup"><span data-stu-id="8c5c8-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8c5c8-114">**name**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-114">**name**</span></span>  | <span data-ttu-id="8c5c8-115">구성 섹션의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="8c5c8-116">**type**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-116">**type**</span></span>  | <span data-ttu-id="8c5c8-117">구성 파일에서 섹션을 읽는 구성 섹션 처리기 클래스의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="8c5c8-118">형식 값의 구문은 "정규화 된 섹션-클래스 이름, 단순 어셈블리 이름"입니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="8c5c8-119">단순 어셈블리 이름은 *.dll* 파일 확장명이 없는 루트 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="8c5c8-120">선택적 특성</span><span class="sxs-lookup"><span data-stu-id="8c5c8-120">Optional attributes</span></span>

<span data-ttu-id="8c5c8-121">다음 특성은 ASP.NET 응용 프로그램에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="8c5c8-122">구성 시스템에서는 다른 응용 프로그램 유형에 대 한 이러한 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="8c5c8-123">설명</span><span class="sxs-lookup"><span data-stu-id="8c5c8-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="8c5c8-124">**allowDefinition**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-124">**allowDefinition**</span></span> | <span data-ttu-id="8c5c8-125">섹션을 사용할 수 있는 구성 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="8c5c8-126">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-126">Use one of the following values:</span></span><br><br><span data-ttu-id="8c5c8-127">**마다**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-127">**Everywhere**</span></span><br><span data-ttu-id="8c5c8-128">섹션을 모든 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="8c5c8-129">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-129">This is the default.</span></span><br><span data-ttu-id="8c5c8-130">**MachineOnly**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-130">**MachineOnly**</span></span><br><span data-ttu-id="8c5c8-131">*컴퓨터 구성 파일 (machine.config*) 에서만 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="8c5c8-132">**MachineToApplication**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-132">**MachineToApplication**</span></span><br><span data-ttu-id="8c5c8-133">컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에서 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="8c5c8-134">**allowLocation**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-134">**allowLocation**</span></span>   | <span data-ttu-id="8c5c8-135">**\<location >** 요소 내에서 섹션을 사용할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="8c5c8-136">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-136">Use one of the following values:</span></span><br><br><span data-ttu-id="8c5c8-137">**true**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-137">**true**</span></span><br><span data-ttu-id="8c5c8-138">**\<location >** 요소 내에 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="8c5c8-139">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-139">This is the default.</span></span><br><span data-ttu-id="8c5c8-140">**false**</span><span class="sxs-lookup"><span data-stu-id="8c5c8-140">**false**</span></span><br><span data-ttu-id="8c5c8-141">에서는 **\<location >** 요소 내에서 섹션을 사용 하는 것을 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="8c5c8-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8c5c8-142">Parent elements</span></span>

|     | <span data-ttu-id="8c5c8-143">설명</span><span class="sxs-lookup"><span data-stu-id="8c5c8-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8c5c8-144">**configSections을\<** 요소인</span><span class="sxs-lookup"><span data-stu-id="8c5c8-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="8c5c8-145">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="8c5c8-146"> **\<sectionGroup >** 요소인</span><span class="sxs-lookup"><span data-stu-id="8c5c8-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="8c5c8-147">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="8c5c8-148">**\<section >** 요소는 **\<configsections >** 또는 **\<sectionGroup >** 의 자식 요소 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="8c5c8-149">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8c5c8-149">Child elements</span></span>

<span data-ttu-id="8c5c8-150">없음</span><span class="sxs-lookup"><span data-stu-id="8c5c8-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="8c5c8-151">주의</span><span class="sxs-lookup"><span data-stu-id="8c5c8-151">Remarks</span></span>

<span data-ttu-id="8c5c8-152">구성 섹션을 선언 하는 것은 기본적으로 구성 파일에 대 한 새 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="8c5c8-153">새 요소에는 구성 섹션 처리기 (즉, <xref:System.Configuration.IConfigurationSectionHandler> 인터페이스를 구현 하는 클래스)가 읽는 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="8c5c8-154">사용자가 정의 하는 섹션의 특성 및 자식 요소는 설정을 읽는 데 사용 하는 섹션 처리기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="8c5c8-155">*Machine.config 파일에서* 구성 섹션 처리기를 선언 하면 **allowDefinition** 특성이 달리 지정 되지 않는 한 해당 컴퓨터의 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="8c5c8-156">예제</span><span class="sxs-lookup"><span data-stu-id="8c5c8-156">Example</span></span>

<span data-ttu-id="8c5c8-157">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="8c5c8-158">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8c5c8-158">Configuration file</span></span>

<span data-ttu-id="8c5c8-159">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c5c8-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c5c8-160">참조</span><span class="sxs-lookup"><span data-stu-id="8c5c8-160">See also</span></span>

- [<span data-ttu-id="8c5c8-161">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8c5c8-161">Configuration file schema for the .NET Framework</span></span>](index.md)
