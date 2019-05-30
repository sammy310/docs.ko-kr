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
ms.openlocfilehash: 750708483f9680745eef4531d86fa7ecaa329f51
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301187"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="7be4b-102">\<sectionGroup > 요소에 대 한 \<configSections ></span><span class="sxs-lookup"><span data-stu-id="7be4b-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="7be4b-103">구성 섹션에 대 한 네임 스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="7be4b-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="7be4b-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="7be4b-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="7be4b-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="7be4b-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup>**</span><span class="sxs-lookup"><span data-stu-id="7be4b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="7be4b-107">구문</span><span class="sxs-lookup"><span data-stu-id="7be4b-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="7be4b-108">특성</span><span class="sxs-lookup"><span data-stu-id="7be4b-108">Attribute</span></span>

|           | <span data-ttu-id="7be4b-109">설명</span><span class="sxs-lookup"><span data-stu-id="7be4b-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="7be4b-110">**name**</span><span class="sxs-lookup"><span data-stu-id="7be4b-110">**name**</span></span>  | <span data-ttu-id="7be4b-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-111">Required attribute.</span></span><br><br><span data-ttu-id="7be4b-112">정의 하는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="7be4b-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7be4b-113">Parent element</span></span>

|     | <span data-ttu-id="7be4b-114">설명</span><span class="sxs-lookup"><span data-stu-id="7be4b-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7be4b-115"> *\*\<configSections >** 요소</span><span class="sxs-lookup"><span data-stu-id="7be4b-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="7be4b-116">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="7be4b-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7be4b-117">Child elements</span></span>

|     | <span data-ttu-id="7be4b-118">설명</span><span class="sxs-lookup"><span data-stu-id="7be4b-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="7be4b-119"> *\*\<section>** </span><span class="sxs-lookup"><span data-stu-id="7be4b-119">**\<section>**</span></span>](~/docs/framework/configure-apps/file-schema/section-element.md) | <span data-ttu-id="7be4b-120">구성 섹션 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7be4b-121">설명</span><span class="sxs-lookup"><span data-stu-id="7be4b-121">Remarks</span></span>

<span data-ttu-id="7be4b-122">구성 섹션에 대 한 컨테이너 태그를 만들고 하면 다른 사용자가 정의 하는 구성 섹션 이름과 충돌 하지 않습니다 섹션 그룹을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="7be4b-123">중첩할 수 있습니다  **\<sectionGroup >** 서로의 내부 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="7be4b-124">예제</span><span class="sxs-lookup"><span data-stu-id="7be4b-124">Example</span></span>

<span data-ttu-id="7be4b-125">다음 예제에서는 섹션 그룹 내의 섹션을 선언 하 고 섹션 그룹을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="7be4b-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="7be4b-126">Configuration file</span></span>

<span data-ttu-id="7be4b-127">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7be4b-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="7be4b-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="7be4b-128">See also</span></span>

- [<span data-ttu-id="7be4b-129">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7be4b-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
