---
title: <configSections>에 대한 <sectionGroup> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4e28e8ccea1090e6a5704b541e09dc11681278ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920648"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="9898a-102">\<configsections에 대 \<한 sectionGroup > 요소 ></span><span class="sxs-lookup"><span data-stu-id="9898a-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="9898a-103">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="9898a-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="9898a-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="9898a-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="9898a-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="9898a-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="9898a-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="9898a-107">구문</span><span class="sxs-lookup"><span data-stu-id="9898a-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="9898a-108">특성</span><span class="sxs-lookup"><span data-stu-id="9898a-108">Attribute</span></span>

|           | <span data-ttu-id="9898a-109">설명</span><span class="sxs-lookup"><span data-stu-id="9898a-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="9898a-110">**name**</span><span class="sxs-lookup"><span data-stu-id="9898a-110">**name**</span></span>  | <span data-ttu-id="9898a-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-111">Required attribute.</span></span><br><br><span data-ttu-id="9898a-112">정의 하는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="9898a-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9898a-113">Parent element</span></span>

|     | <span data-ttu-id="9898a-114">Description</span><span class="sxs-lookup"><span data-stu-id="9898a-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9898a-115">configsections > 요소  **\<** </span><span class="sxs-lookup"><span data-stu-id="9898a-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="9898a-116">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="9898a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9898a-117">Child elements</span></span>

|     | <span data-ttu-id="9898a-118">설명</span><span class="sxs-lookup"><span data-stu-id="9898a-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="9898a-119"> **\<section>** </span><span class="sxs-lookup"><span data-stu-id="9898a-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="9898a-120">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="9898a-121">설명</span><span class="sxs-lookup"><span data-stu-id="9898a-121">Remarks</span></span>

<span data-ttu-id="9898a-122">섹션 그룹을 선언 하면 구성 섹션에 대 한 컨테이너 태그가 생성 되며 다른 사용자가 정의한 구성 섹션과 이름이 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="9898a-123">**\<SectionGroup >** 요소를 서로 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="9898a-124">예제</span><span class="sxs-lookup"><span data-stu-id="9898a-124">Example</span></span>

<span data-ttu-id="9898a-125">다음 예제에서는 섹션 그룹을 선언 하 고 섹션 그룹 내에서 섹션을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

```xml
<configuration>
  <configSections>
    <sectionGroup name="mySectionGroup">
      <section name="mySection"
               type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="9898a-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="9898a-126">Configuration file</span></span>

<span data-ttu-id="9898a-127">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (machine.config) 및응용 프로그램 디렉터리 수준에 없는 web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9898a-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="9898a-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="9898a-128">See also</span></span>

- [<span data-ttu-id="9898a-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9898a-129">Configuration file schema for the .NET Framework</span></span>](index.md)
