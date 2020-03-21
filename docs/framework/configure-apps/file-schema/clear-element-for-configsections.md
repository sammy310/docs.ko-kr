---
title: <configSections>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 77f1d761-ff45-4001-8f36-3a3e5c41fa63
ms.openlocfilehash: 66abd7f057bc6d060e50a889a945281d07c97592
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155429"
---
# <a name="clear-element-for-configsections"></a><span data-ttu-id="68c4c-102">\<구성에 대한 \<명확한> 요소></span><span class="sxs-lookup"><span data-stu-id="68c4c-102">\<clear> element for \<configSections></span></span>

<span data-ttu-id="68c4c-103">이전에 정의된 모든 단면 및 단면 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-103">Clears all previously defined sections and section groups.</span></span>

<span data-ttu-id="68c4c-104">&nbsp; &nbsp; &nbsp; **구성 \<**>&nbsp; &nbsp;구성섹션 &nbsp;>명확한>[\*\* \<\*\*](configuration-element.md) [\*\* \<\*\*](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="68c4c-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) &nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="68c4c-105">구문</span><span class="sxs-lookup"><span data-stu-id="68c4c-105">Syntax</span></span>

```xml
<clear/>
```

## <a name="attribute"></a><span data-ttu-id="68c4c-106">attribute</span><span class="sxs-lookup"><span data-stu-id="68c4c-106">Attribute</span></span>

|           | <span data-ttu-id="68c4c-107">Description</span><span class="sxs-lookup"><span data-stu-id="68c4c-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="68c4c-108">**(이름)**</span><span class="sxs-lookup"><span data-stu-id="68c4c-108">**name**</span></span>  | <span data-ttu-id="68c4c-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-109">Required attribute.</span></span><br><br><span data-ttu-id="68c4c-110">제거할 단면 또는 단면 그룹의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-110">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="68c4c-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="68c4c-111">Parent element</span></span>

|     | <span data-ttu-id="68c4c-112">Description</span><span class="sxs-lookup"><span data-stu-id="68c4c-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="68c4c-113">\*\* \<>구성섹션\*\* 요소</span><span class="sxs-lookup"><span data-stu-id="68c4c-113">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="68c4c-114">구성 섹션 및 네임스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-114">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="68c4c-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="68c4c-115">Child elements</span></span>

<span data-ttu-id="68c4c-116">None</span><span class="sxs-lookup"><span data-stu-id="68c4c-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="68c4c-117">설명</span><span class="sxs-lookup"><span data-stu-id="68c4c-117">Remarks</span></span>

<span data-ttu-id="68c4c-118">명확한>요소는 현재 구성 파일의 이전 또는 구성 파일 계층 구조의 상위 수준에서 정의된 응용 프로그램에서 모든 섹션 및 단면 그룹을 제거합니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="68c4c-118">The **\<clear>** element removes all sections and section groups from your application that were defined earlier in the current configuration file or at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="68c4c-119">예제</span><span class="sxs-lookup"><span data-stu-id="68c4c-119">Example</span></span>

<span data-ttu-id="68c4c-120">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의하고 응용 프로그램 구성 파일에서 \*\* \<clear>\*\* 요소를 사용하여 이전에 컴퓨터 구성 파일에 정의된 섹션을 지우는 방법을 보여 주며 이 예제를 보여 주며, 응용 프로그램 구성 파일에서 미리 정의된 섹션을 지우는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-120">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="68c4c-121">다음 컴퓨터 구성 파일 코드는 \*\* \<sampleSection>\*\* 및 \*\* \<응용 \*\*프로그램 구성 파일 앞에 읽히는 다른SampleSection>두 섹션을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-121">The following machine configuration file code declares two sections, **\<sampleSection>** and **\<anotherSampleSection>**, which are read before the application configuration file:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
    <section name="anotherSampleSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

<span data-ttu-id="68c4c-122">다음 응용 프로그램 구성 파일 코드는 이전에 선언된 모든 섹션을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-122">The following application configuration file code clears all previously declared sections.</span></span> <span data-ttu-id="68c4c-123">응용 프로그램은 컴퓨터 구성 파일에 선언된 섹션 중 하나에서 설정을 사용하거나 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-123">The application cannot use or retrieve settings in either of the sections that were declared in the machine configuration file.</span></span> <span data-ttu-id="68c4c-124">그러나, 그것은 \*\* \<다른에서\*\* 설정을 사용할 수 \*\* \<있습니다명확한>\*\* 요소 후 제공되기 때문에>섹션.</span><span class="sxs-lookup"><span data-stu-id="68c4c-124">However, it can use settings from **\<anotherSection>** because it comes after the **\<clear>** element.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <clear/>
    <section name="anotherSection"
             type="System.Configuration.NameValueSectionHandler" />
  </configSections>
  <anotherSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="68c4c-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="68c4c-125">Configuration file</span></span>

<span data-ttu-id="68c4c-126">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68c4c-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="68c4c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68c4c-127">See also</span></span>

- [<span data-ttu-id="68c4c-128">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="68c4c-128">Configuration file schema for the .NET Framework</span></span>](index.md)
