---
title: <configuration>에 대한 <configSections> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 55116f1fe6fdffffea8f26d8a4de783c7305ada3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155351"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="32101-102">\<구성> 대한 \<구성섹션> 요소</span><span class="sxs-lookup"><span data-stu-id="32101-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="32101-103">구성 섹션 및 네임스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="32101-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="32101-104">구성 &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \*\* \<구성섹션>\*\*</span><span class="sxs-lookup"><span data-stu-id="32101-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="32101-105">특성</span><span class="sxs-lookup"><span data-stu-id="32101-105">Attributes</span></span>

<span data-ttu-id="32101-106">None</span><span class="sxs-lookup"><span data-stu-id="32101-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="32101-107">부모 요소</span><span class="sxs-lookup"><span data-stu-id="32101-107">Parent element</span></span>

|     | <span data-ttu-id="32101-108">Description</span><span class="sxs-lookup"><span data-stu-id="32101-108">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="32101-109">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="32101-109">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="32101-110">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="32101-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="32101-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="32101-111">Child elements</span></span>

|     | <span data-ttu-id="32101-112">Description</span><span class="sxs-lookup"><span data-stu-id="32101-112">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="32101-113">**\<섹션>**</span><span class="sxs-lookup"><span data-stu-id="32101-113">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="32101-114">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="32101-114">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="32101-115">**\<섹션 그룹>**</span><span class="sxs-lookup"><span data-stu-id="32101-115">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="32101-116">구성 섹션에 대한 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="32101-116">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="32101-117">**\<>제거**</span><span class="sxs-lookup"><span data-stu-id="32101-117">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="32101-118">미리 정의된 단면 또는 단면 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="32101-118">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="32101-119">**\<클리어>**</span><span class="sxs-lookup"><span data-stu-id="32101-119">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="32101-120">이전에 정의된 모든 단면 및 단면 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="32101-120">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="32101-121">설명</span><span class="sxs-lookup"><span data-stu-id="32101-121">Remarks</span></span>

<span data-ttu-id="32101-122">이 요소가 구성 파일에 있는 경우 \*\* \<구성>\*\* 요소의 첫 번째 자식 요소여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32101-122">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="32101-123">예제</span><span class="sxs-lookup"><span data-stu-id="32101-123">Example</span></span>

<span data-ttu-id="32101-124">다음 예제에서는 구성 섹션을 정의하고 해당 섹션에 대한 설정을 정의하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32101-124">The following example shows how to define a configuration section and define settings for that section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="sampleSection"
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1"
                 setting2="value two"
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="32101-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="32101-125">Configuration file</span></span>

<span data-ttu-id="32101-126">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32101-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="32101-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="32101-127">See also</span></span>

- [<span data-ttu-id="32101-128">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="32101-128">Configuration file schema for the .NET Framework</span></span>](index.md)
