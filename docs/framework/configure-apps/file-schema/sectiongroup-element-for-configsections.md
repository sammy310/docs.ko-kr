---
title: <sectionGroup>에 대한 <configSections> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/sectionGroup
helpviewer_keywords:
- sectionGroup Element
- <sectionGroup> Element
ms.assetid: 6c27f9e2-809c-4bc9-aca9-72f90360e7a3
ms.openlocfilehash: eb221027470fe6e485f8fcc4b939b71e4f219712
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215255"
---
# <a name="sectiongroup-element-for-configsections"></a><span data-ttu-id="d9769-102">\<configSections에 대 한 \<sectionGroup > 요소 ></span><span class="sxs-lookup"><span data-stu-id="d9769-102">\<sectionGroup> element for \<configSections></span></span>

<span data-ttu-id="d9769-103">구성 섹션에 대 한 네임 스페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-103">Defines a namespace for configuration sections.</span></span>

<span data-ttu-id="d9769-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d9769-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="d9769-105">[**configSections >\<** ](configsections-element-for-configuration.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="d9769-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="d9769-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<sectionGroup >**</span><span class="sxs-lookup"><span data-stu-id="d9769-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sectionGroup>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d9769-107">구문</span><span class="sxs-lookup"><span data-stu-id="d9769-107">Syntax</span></span>

```xml
<sectionGroup name="section group name">
  <!-- Configuration sections -->
</sectionGroup>
```

## <a name="attribute"></a><span data-ttu-id="d9769-108">attribute</span><span class="sxs-lookup"><span data-stu-id="d9769-108">Attribute</span></span>

|           | <span data-ttu-id="d9769-109">Description</span><span class="sxs-lookup"><span data-stu-id="d9769-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d9769-110">**name**</span><span class="sxs-lookup"><span data-stu-id="d9769-110">**name**</span></span>  | <span data-ttu-id="d9769-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-111">Required attribute.</span></span><br><br><span data-ttu-id="d9769-112">정의 하는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-112">Specifies the name of the section group you are defining.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d9769-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d9769-113">Parent element</span></span>

|     | <span data-ttu-id="d9769-114">Description</span><span class="sxs-lookup"><span data-stu-id="d9769-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d9769-115">**configSections을\<>** 요소인</span><span class="sxs-lookup"><span data-stu-id="d9769-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="d9769-116">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d9769-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d9769-117">Child elements</span></span>

|     | <span data-ttu-id="d9769-118">Description</span><span class="sxs-lookup"><span data-stu-id="d9769-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d9769-119"> **\<섹션 >** </span><span class="sxs-lookup"><span data-stu-id="d9769-119">**\<section>**</span></span>](section-element.md) | <span data-ttu-id="d9769-120">구성 섹션 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-120">Contains a configuration section declaration.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d9769-121">설명</span><span class="sxs-lookup"><span data-stu-id="d9769-121">Remarks</span></span>

<span data-ttu-id="d9769-122">섹션 그룹을 선언 하면 구성 섹션에 대 한 컨테이너 태그가 생성 되며 다른 사용자가 정의한 구성 섹션과 이름이 충돌 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-122">Declaring a section group creates a container tag for configuration sections and ensures that there are no naming conflicts with configuration sections defined by someone else.</span></span> <span data-ttu-id="d9769-123">**\<sectionGroup >** 요소를 서로 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-123">You can nest **\<sectionGroup>** elements within each other.</span></span>

## <a name="example"></a><span data-ttu-id="d9769-124">예제</span><span class="sxs-lookup"><span data-stu-id="d9769-124">Example</span></span>

<span data-ttu-id="d9769-125">다음 예제에서는 섹션 그룹을 선언 하 고 섹션 그룹 내에서 섹션을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-125">The following example shows how to declare a section group and declare sections within a section group:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d9769-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d9769-126">Configuration file</span></span>

<span data-ttu-id="d9769-127">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9769-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d9769-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9769-128">See also</span></span>

- [<span data-ttu-id="d9769-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d9769-129">Configuration file schema for the .NET Framework</span></span>](index.md)
