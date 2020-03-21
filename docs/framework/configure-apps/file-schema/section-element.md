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
ms.openlocfilehash: 88f74c02ef627e9136e4437ffa150c36445266a3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153734"
---
# <a name="section-element"></a><span data-ttu-id="97861-102">\<단면> 요소</span><span class="sxs-lookup"><span data-stu-id="97861-102">\<section> element</span></span>

<span data-ttu-id="97861-103">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-103">Contains a configuration section declaration.</span></span>

<span data-ttu-id="97861-104">[**\<구성>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97861-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="97861-105">&nbsp;&nbsp;[**\<>섹션**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="97861-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="97861-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션>**</span><span class="sxs-lookup"><span data-stu-id="97861-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

<span data-ttu-id="97861-107">[**\<구성>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="97861-107">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="97861-108">&nbsp;&nbsp;[**\<>섹션**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="97861-108">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="97861-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<섹션 그룹>**](sectiongroup-element-for-configsections.md)</span><span class="sxs-lookup"><span data-stu-id="97861-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sectionGroup>**](sectiongroup-element-for-configsections.md)</span></span>\
<span data-ttu-id="97861-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<섹션>**</span><span class="sxs-lookup"><span data-stu-id="97861-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<section>**</span></span>

## <a name="syntax"></a><span data-ttu-id="97861-111">구문</span><span class="sxs-lookup"><span data-stu-id="97861-111">Syntax</span></span>

```xml
<section name="section name"
         type="configuration section handler class, assembly"
         allowDefinition="Everywhere|MachineOnly|MachineToApplication"
         allowLocation="true|false" />
```

## <a name="required-attributes"></a><span data-ttu-id="97861-112">필수 특성</span><span class="sxs-lookup"><span data-stu-id="97861-112">Required attributes</span></span>

|           | <span data-ttu-id="97861-113">Description</span><span class="sxs-lookup"><span data-stu-id="97861-113">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="97861-114">**(이름)**</span><span class="sxs-lookup"><span data-stu-id="97861-114">**name**</span></span>  | <span data-ttu-id="97861-115">구성 섹션의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-115">Specifies the name of the configuration section.</span></span> |
| <span data-ttu-id="97861-116">**종류**</span><span class="sxs-lookup"><span data-stu-id="97861-116">**type**</span></span>  | <span data-ttu-id="97861-117">구성 파일에서 섹션을 읽는 구성 섹션 처리기 클래스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-117">Specifies the name of the configuration section handler class that reads the section from the configuration file.</span></span> <span data-ttu-id="97861-118">형식 값에는 "정규화된 섹션-핸들러 클래스 이름, 간단한 어셈블리 이름"이라는 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-118">The type value has the syntax "fully-qualified-section-handler-class-name, simple-assembly-name".</span></span> <span data-ttu-id="97861-119">간단한 어셈블리 이름은 *.dll* 파일 확장자 없이 루트 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="97861-119">The simple assembly name is the root filename without the *.dll* file extension.</span></span> |

## <a name="optional-attributes"></a><span data-ttu-id="97861-120">선택적 특성</span><span class="sxs-lookup"><span data-stu-id="97861-120">Optional attributes</span></span>

<span data-ttu-id="97861-121">다음 특성은 ASP.NET 응용 프로그램에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97861-121">The following attributes are applicable only for ASP.NET applications.</span></span> <span data-ttu-id="97861-122">구성 시스템은 다른 응용 프로그램 형식에 대해 이러한 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-122">The configuration system ignores these attributes for other application types.</span></span>

|                     | <span data-ttu-id="97861-123">Description</span><span class="sxs-lookup"><span data-stu-id="97861-123">Description</span></span> |
| ------------------- | ----------- |
| <span data-ttu-id="97861-124">**허용정의**</span><span class="sxs-lookup"><span data-stu-id="97861-124">**allowDefinition**</span></span> | <span data-ttu-id="97861-125">섹션에서 사용할 수 있는 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-125">Specifies which configuration file the section can be used in.</span></span> <span data-ttu-id="97861-126">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-126">Use one of the following values:</span></span><br><br><span data-ttu-id="97861-127">**모든 범위**</span><span class="sxs-lookup"><span data-stu-id="97861-127">**Everywhere**</span></span><br><span data-ttu-id="97861-128">섹션을 모든 구성 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-128">Allows the section to be used in any configuration file.</span></span> <span data-ttu-id="97861-129">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="97861-129">This is the default.</span></span><br><span data-ttu-id="97861-130">**기계 만**</span><span class="sxs-lookup"><span data-stu-id="97861-130">**MachineOnly**</span></span><br><span data-ttu-id="97861-131">섹션을 컴퓨터 구성*파일(Machine.config)에서만*사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-131">Allows the section to be used only in the machine configuration file (*Machine.config*).</span></span><br><span data-ttu-id="97861-132">**기계 응용 프로그램**</span><span class="sxs-lookup"><span data-stu-id="97861-132">**MachineToApplication**</span></span><br><span data-ttu-id="97861-133">섹션을 컴퓨터 구성 파일 또는 응용 프로그램 구성 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-133">Allows the section to be used in the machine configuration file or the application configuration file.</span></span> |
| <span data-ttu-id="97861-134">**허용위치**</span><span class="sxs-lookup"><span data-stu-id="97861-134">**allowLocation**</span></span>   | <span data-ttu-id="97861-135">위치>요소 내에서 단면을 사용할 수 있는지 여부를 결정합니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="97861-135">Determines whether the section can be used within the **\<location>** element.</span></span> <span data-ttu-id="97861-136">다음 값 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-136">Use one of the following values:</span></span><br><br><span data-ttu-id="97861-137">**true**</span><span class="sxs-lookup"><span data-stu-id="97861-137">**true**</span></span><br><span data-ttu-id="97861-138">위치>요소 내에서 섹션을 사용할 수 있습니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="97861-138">Allows the section to be used within the **\<location>** element.</span></span> <span data-ttu-id="97861-139">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="97861-139">This is the default.</span></span><br><span data-ttu-id="97861-140">**false**</span><span class="sxs-lookup"><span data-stu-id="97861-140">**false**</span></span><br><span data-ttu-id="97861-141">위치>요소 내에서 섹션을 사용할 수 없습니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="97861-141">Does not allow the section to be used within the **\<location>** element.</span></span> |

## <a name="parent-elements"></a><span data-ttu-id="97861-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="97861-142">Parent elements</span></span>

|     | <span data-ttu-id="97861-143">Description</span><span class="sxs-lookup"><span data-stu-id="97861-143">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="97861-144">\*\* \<>구성섹션\*\* 요소</span><span class="sxs-lookup"><span data-stu-id="97861-144">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="97861-145">구성 섹션 및 네임스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-145">Contains configuration section and namespace declarations.</span></span> |
| [<span data-ttu-id="97861-146">\*\* \<섹션그룹>\*\* 요소</span><span class="sxs-lookup"><span data-stu-id="97861-146">**\<sectionGroup>** Element</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="97861-147">구성 섹션에 대한 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-147">Defines a namespace for configuration sections.</span></span> |

> [!NOTE]
> <span data-ttu-id="97861-148">섹션>요소는 \*\* \<구성섹션>\*\* 또는 \*\* \<\*\* \*\* \<섹션그룹>\*\* 하위 요소이지만 둘 다 는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="97861-148">A **\<section>** element is a child element of either **\<configSections>** or **\<sectionGroup>** but not both.</span></span>

## <a name="child-elements"></a><span data-ttu-id="97861-149">자식 요소</span><span class="sxs-lookup"><span data-stu-id="97861-149">Child elements</span></span>

<span data-ttu-id="97861-150">None</span><span class="sxs-lookup"><span data-stu-id="97861-150">None</span></span>

## <a name="remarks"></a><span data-ttu-id="97861-151">설명</span><span class="sxs-lookup"><span data-stu-id="97861-151">Remarks</span></span>

<span data-ttu-id="97861-152">구성 섹션을 선언하는 것은 기본적으로 구성 파일에 대한 새 요소를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="97861-152">Declaring a configuration section essentially defines a new element for the configuration file.</span></span> <span data-ttu-id="97861-153">새 요소에는 구성 섹션 처리기(즉, 인터페이스를 구현하는 <xref:System.Configuration.IConfigurationSectionHandler> 클래스)가 읽는 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-153">The new element contains settings that a configuration section handler (that is, a class that implements the <xref:System.Configuration.IConfigurationSectionHandler> interface) reads.</span></span> <span data-ttu-id="97861-154">정의하는 섹션의 특성 및 자식 요소는 설정을 읽는 데 사용하는 섹션 처리기에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="97861-154">The attributes and child elements of a section you define depend on the section handler you use to read your settings.</span></span>

<span data-ttu-id="97861-155">*Machine.config* 파일에서 구성 섹션 처리기를 선언하면 **allowDefinition** 특성이 달리 지정하지 않는 한 해당 컴퓨터의 모든 응용 프로그램 구성 파일에서 구성 섹션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-155">Declaring a configuration section handler in the *Machine.config* file enables you to use the configuration section in any application configuration file on that computer, unless the **allowDefinition** attribute specifies otherwise.</span></span>

## <a name="example"></a><span data-ttu-id="97861-156">예제</span><span class="sxs-lookup"><span data-stu-id="97861-156">Example</span></span>

<span data-ttu-id="97861-157">다음 예제에서는 구성 섹션을 정의하고 해당 섹션에 대한 설정을 정의하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-157">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="97861-158">구성 파일</span><span class="sxs-lookup"><span data-stu-id="97861-158">Configuration file</span></span>

<span data-ttu-id="97861-159">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97861-159">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="97861-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="97861-160">See also</span></span>

- [<span data-ttu-id="97861-161">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="97861-161">Configuration file schema for the .NET Framework</span></span>](index.md)
