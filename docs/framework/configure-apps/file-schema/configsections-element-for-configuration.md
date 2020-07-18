---
title: <configuration>에 대한 <configSections> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 1e4bb7a7cfb0b140ca6d13c162708c3c30bd496d
ms.sourcegitcommit: 2543a78be6e246aa010a01decf58889de53d1636
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/17/2020
ms.locfileid: "86441689"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="43eae-102">\<configuration>에 대한 \<configSections> 요소</span><span class="sxs-lookup"><span data-stu-id="43eae-102">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="43eae-103">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43eae-103">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="43eae-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="43eae-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="43eae-105">특성</span><span class="sxs-lookup"><span data-stu-id="43eae-105">Attributes</span></span>

<span data-ttu-id="43eae-106">없음</span><span class="sxs-lookup"><span data-stu-id="43eae-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="43eae-107">부모 요소</span><span class="sxs-lookup"><span data-stu-id="43eae-107">Parent element</span></span>

|     | <span data-ttu-id="43eae-108">설명</span><span class="sxs-lookup"><span data-stu-id="43eae-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="43eae-109">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="43eae-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="43eae-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="43eae-110">Child elements</span></span>

|     | <span data-ttu-id="43eae-111">설명</span><span class="sxs-lookup"><span data-stu-id="43eae-111">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="43eae-112">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="43eae-112">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="43eae-113">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="43eae-113">Defines a namespace for configuration sections.</span></span> |

## <a name="remarks"></a><span data-ttu-id="43eae-114">설명</span><span class="sxs-lookup"><span data-stu-id="43eae-114">Remarks</span></span>

<span data-ttu-id="43eae-115">이 요소가 구성 파일에 있으면 요소의 첫 번째 자식 요소 여야 합니다 **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="43eae-115">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="43eae-116">예제</span><span class="sxs-lookup"><span data-stu-id="43eae-116">Example</span></span>

<span data-ttu-id="43eae-117">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43eae-117">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="43eae-118">구성 파일</span><span class="sxs-lookup"><span data-stu-id="43eae-118">Configuration file</span></span>

<span data-ttu-id="43eae-119">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43eae-119">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="43eae-120">참조</span><span class="sxs-lookup"><span data-stu-id="43eae-120">See also</span></span>

- [<span data-ttu-id="43eae-121">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="43eae-121">Configuration file schema for the .NET Framework</span></span>](index.md)
