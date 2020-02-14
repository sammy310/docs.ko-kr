---
title: <configSections>에 대한 <configuration> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 5b71eb81769db1188f97b1646a608df172ff56c5
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214819"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="b6899-102">\<구성에 대 한 configSections > 요소를 \<></span><span class="sxs-lookup"><span data-stu-id="b6899-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="b6899-103">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="b6899-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="b6899-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="b6899-105">**configSections을\<** &nbsp;&nbsp;></span><span class="sxs-lookup"><span data-stu-id="b6899-105">&nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="b6899-106">특성</span><span class="sxs-lookup"><span data-stu-id="b6899-106">Attributes</span></span>

<span data-ttu-id="b6899-107">None</span><span class="sxs-lookup"><span data-stu-id="b6899-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="b6899-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="b6899-108">Parent element</span></span>

|     | <span data-ttu-id="b6899-109">Description</span><span class="sxs-lookup"><span data-stu-id="b6899-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b6899-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="b6899-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="b6899-111">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="b6899-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="b6899-112">Child elements</span></span>

|     | <span data-ttu-id="b6899-113">Description</span><span class="sxs-lookup"><span data-stu-id="b6899-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="b6899-114"> **\<섹션 >** </span><span class="sxs-lookup"><span data-stu-id="b6899-114">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="b6899-115">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-115">Contains a configuration section declaration.</span></span> |
| [<span data-ttu-id="b6899-116"> **\<sectionGroup >** </span><span class="sxs-lookup"><span data-stu-id="b6899-116">**\<sectionGroup>**</span></span>](sectiongroup-element-for-configsections.md) | <span data-ttu-id="b6899-117">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-117">Defines a namespace for configuration sections.</span></span> |
| [<span data-ttu-id="b6899-118"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="b6899-118">**\<remove>**</span></span>](remove-element-for-configsections.md) | <span data-ttu-id="b6899-119">미리 정의 된 섹션 또는 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-119">Removes a predefined section or section group.</span></span> |
| [<span data-ttu-id="b6899-120"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="b6899-120">**\<clear>**</span></span>](clear-element-for-configsections.md) | <span data-ttu-id="b6899-121">이전에 정의 된 모든 섹션과 섹션 그룹을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-121">Clears all previously defined sections and section groups.</span></span> |

## <a name="remarks"></a><span data-ttu-id="b6899-122">설명</span><span class="sxs-lookup"><span data-stu-id="b6899-122">Remarks</span></span>

<span data-ttu-id="b6899-123">이 요소는 구성 파일에 있는 경우 **\<configuration >** 요소의 첫 번째 자식 요소 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-123">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="b6899-124">예제</span><span class="sxs-lookup"><span data-stu-id="b6899-124">Example</span></span>

<span data-ttu-id="b6899-125">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-125">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="b6899-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="b6899-126">Configuration file</span></span>

<span data-ttu-id="b6899-127">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6899-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6899-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6899-128">See also</span></span>

- [<span data-ttu-id="b6899-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="b6899-129">Configuration file schema for the .NET Framework</span></span>](index.md)
