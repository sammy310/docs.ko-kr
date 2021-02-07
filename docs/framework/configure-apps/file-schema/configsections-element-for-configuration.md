---
description: '에 대 한 자세한 정보: <configSections> 요소 <configuration>'
title: <configuration>에 대한 <configSections> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections
helpviewer_keywords:
- configSections Element
- <configSections> Element
ms.assetid: 9f963c1b-dc3f-4220-a8b6-2dd7a5a8e039
ms.openlocfilehash: 543ceed8d53fd299e8a0b65594592b64d6b833a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698989"
---
# <a name="configsections-element-for-configuration"></a><span data-ttu-id="ce386-103">\<configuration>에 대한 \<configSections> 요소</span><span class="sxs-lookup"><span data-stu-id="ce386-103">\<configSections> element for \<configuration></span></span>

<span data-ttu-id="ce386-104">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce386-104">Contains configuration section and namespace declarations.</span></span>

<span data-ttu-id="ce386-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span><span class="sxs-lookup"><span data-stu-id="ce386-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<configSections>**</span></span>

## <a name="attributes"></a><span data-ttu-id="ce386-106">특성</span><span class="sxs-lookup"><span data-stu-id="ce386-106">Attributes</span></span>

<span data-ttu-id="ce386-107">None</span><span class="sxs-lookup"><span data-stu-id="ce386-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="ce386-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ce386-108">Parent element</span></span>

|     | <span data-ttu-id="ce386-109">설명</span><span class="sxs-lookup"><span data-stu-id="ce386-109">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="ce386-110">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce386-110">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ce386-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ce386-111">Child elements</span></span>

|     | <span data-ttu-id="ce386-112">설명</span><span class="sxs-lookup"><span data-stu-id="ce386-112">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="ce386-113">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce386-113">Contains a configuration section declaration.</span></span> |
| [**\<sectionGroup>**](sectiongroup-element-for-configsections.md) | <span data-ttu-id="ce386-114">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce386-114">Defines a namespace for configuration sections.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ce386-115">설명</span><span class="sxs-lookup"><span data-stu-id="ce386-115">Remarks</span></span>

<span data-ttu-id="ce386-116">이 요소가 구성 파일에 있으면 요소의 첫 번째 자식 요소 여야 합니다 **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="ce386-116">If this element is in a configuration file, it must be the first child element of the **\<configuration>** element.</span></span>

## <a name="example"></a><span data-ttu-id="ce386-117">예제</span><span class="sxs-lookup"><span data-stu-id="ce386-117">Example</span></span>

<span data-ttu-id="ce386-118">다음 예제에서는 구성 섹션을 정의 하 고 해당 섹션에 대 한 설정을 정의 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce386-118">The following example shows how to define a configuration section and define settings for that section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="ce386-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ce386-119">Configuration file</span></span>

<span data-ttu-id="ce386-120">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce386-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce386-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce386-121">See also</span></span>

- [<span data-ttu-id="ce386-122">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ce386-122">Configuration file schema for the .NET Framework</span></span>](index.md)
