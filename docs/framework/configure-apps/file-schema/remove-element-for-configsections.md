---
title: <configSections>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efc7208aa51cbf6abdb2fe151d48071c0aa95b5c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089045"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="21038-102">\<configSections에 대 한 > 요소 \<제거 ></span><span class="sxs-lookup"><span data-stu-id="21038-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="21038-103">미리 정의 된 섹션 또는 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="21038-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="21038-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="21038-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="21038-105">[**configSections >\<** ](configsections-element-for-configuration.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="21038-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="21038-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<제거**</span><span class="sxs-lookup"><span data-stu-id="21038-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="21038-107">구문</span><span class="sxs-lookup"><span data-stu-id="21038-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="21038-108">특성</span><span class="sxs-lookup"><span data-stu-id="21038-108">Attribute</span></span>

|           | <span data-ttu-id="21038-109">설명</span><span class="sxs-lookup"><span data-stu-id="21038-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="21038-110">**name**</span><span class="sxs-lookup"><span data-stu-id="21038-110">**name**</span></span>  | <span data-ttu-id="21038-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="21038-111">Required attribute.</span></span><br><br><span data-ttu-id="21038-112">제거할 섹션 또는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="21038-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="21038-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="21038-113">Parent element</span></span>

|     | <span data-ttu-id="21038-114">설명</span><span class="sxs-lookup"><span data-stu-id="21038-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="21038-115">**configSections을\<** 요소인</span><span class="sxs-lookup"><span data-stu-id="21038-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="21038-116">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21038-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="21038-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="21038-117">Child elements</span></span>

<span data-ttu-id="21038-118">없음</span><span class="sxs-lookup"><span data-stu-id="21038-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="21038-119">주의</span><span class="sxs-lookup"><span data-stu-id="21038-119">Remarks</span></span>

<span data-ttu-id="21038-120">**\<> 요소 제거** 를 사용 하 여 구성 파일 계층 구조에서 더 높은 수준으로 정의 된 섹션 및 섹션 그룹을 응용 프로그램에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21038-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="21038-121">예제</span><span class="sxs-lookup"><span data-stu-id="21038-121">Example</span></span>

<span data-ttu-id="21038-122">다음 예제에서는 응용 프로그램 구성 파일에서 **\<제거 >** 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 섹션을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21038-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="21038-123">다음 컴퓨터 구성 파일 코드는 **sampleSection >\<** 섹션을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="21038-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
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

<span data-ttu-id="21038-124">다음 응용 프로그램 구성 파일 코드는 **\<sampleSection >** 섹션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="21038-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="21038-125">제거 후 응용 프로그램은 **\<sampleSection >** 에서 설정을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21038-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="21038-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="21038-126">Configuration file</span></span>

<span data-ttu-id="21038-127">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21038-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="21038-128">참조</span><span class="sxs-lookup"><span data-stu-id="21038-128">See also</span></span>

- [<span data-ttu-id="21038-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="21038-129">Configuration file schema for the .NET Framework</span></span>](index.md)
