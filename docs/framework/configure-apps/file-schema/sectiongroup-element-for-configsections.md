---
title: <configSections>에 대한 <sectionGroup> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215255"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="0a304-102">\<configSections>에 대한 \<sectionGroup> 요소</span><span class="sxs-lookup"><span data-stu-id="0a304-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="0a304-103">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-103">Defines a namespace for configuration sections.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**

## <a name="syntax"></a><span data-ttu-id="0a304-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a304-104">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="0a304-105">attribute</span><span class="sxs-lookup"><span data-stu-id="0a304-105">Attribute</span></span>

|           | <span data-ttu-id="0a304-106">Description</span><span class="sxs-lookup"><span data-stu-id="0a304-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="0a304-107">**name**</span><span class="sxs-lookup"><span data-stu-id="0a304-107">**name**</span></span>  | <span data-ttu-id="0a304-108">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-108">Required attribute.</span></span><br><br><span data-ttu-id="0a304-109">정의 하는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-109">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="0a304-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0a304-110">Parent element</span></span>

|     | <span data-ttu-id="0a304-111">Description</span><span class="sxs-lookup"><span data-stu-id="0a304-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0a304-112">**\<configSections>** 요소인</span><span class="sxs-lookup"><span data-stu-id="0a304-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="0a304-113">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0a304-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0a304-114">Child elements</span></span>

|     | <span data-ttu-id="0a304-115">Description</span><span class="sxs-lookup"><span data-stu-id="0a304-115">Description</span></span> |
| --- | ----------- |
| [**\<section>**](section-element.md) | <span data-ttu-id="0a304-116">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-116">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="0a304-117">설명</span><span class="sxs-lookup"><span data-stu-id="0a304-117">Remarks</span></span>

<span data-ttu-id="0a304-118">섹션 그룹을 선언 하면 구성 섹션에 대 한 컨테이너 태그가 생성 되며 다른 사용자가 정의한 구성 섹션과 이름이 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-118">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="0a304-119">요소를 서로 중첩할 수 있습니다 **\<sectionGroup>** .</span><span class="sxs-lookup"><span data-stu-id="0a304-119">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="0a304-120">예제</span><span class="sxs-lookup"><span data-stu-id="0a304-120">Example</span></span>

<span data-ttu-id="0a304-121">다음 예제에서는 섹션 그룹을 선언 하 고 섹션 그룹 내에서 섹션을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-121">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="0a304-122">구성 파일</span><span class="sxs-lookup"><span data-stu-id="0a304-122">Configuration file</span></span>

<span data-ttu-id="0a304-123">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a304-123">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a304-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a304-124">See also</span></span>

- [<span data-ttu-id="0a304-125">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="0a304-125">Configuration file schema for the .NET Framework</span></span>](index.md)
