---
title: <configSections>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 4ff9bb537a31e28dbd4b878c1bc04c96262f85ac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927466"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="471ed-102">\<configsections에 대 \<한 > 요소를 제거 ></span><span class="sxs-lookup"><span data-stu-id="471ed-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="471ed-103">미리 정의 된 섹션 또는 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="471ed-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="471ed-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="471ed-105">&nbsp;&nbsp;[ **\<configSections>** ](configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="471ed-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="471ed-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="471ed-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="471ed-107">구문</span><span class="sxs-lookup"><span data-stu-id="471ed-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="471ed-108">특성</span><span class="sxs-lookup"><span data-stu-id="471ed-108">Attribute</span></span>

|           | <span data-ttu-id="471ed-109">설명</span><span class="sxs-lookup"><span data-stu-id="471ed-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="471ed-110">**name**</span><span class="sxs-lookup"><span data-stu-id="471ed-110">**name**</span></span>  | <span data-ttu-id="471ed-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-111">Required attribute.</span></span><br><br><span data-ttu-id="471ed-112">제거할 섹션 또는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="471ed-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="471ed-113">Parent element</span></span>

|     | <span data-ttu-id="471ed-114">Description</span><span class="sxs-lookup"><span data-stu-id="471ed-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="471ed-115">configsections > 요소  **\<** </span><span class="sxs-lookup"><span data-stu-id="471ed-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="471ed-116">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="471ed-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="471ed-117">Child elements</span></span>

<span data-ttu-id="471ed-118">없음</span><span class="sxs-lookup"><span data-stu-id="471ed-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="471ed-119">설명</span><span class="sxs-lookup"><span data-stu-id="471ed-119">Remarks</span></span>

<span data-ttu-id="471ed-120">Remove > 요소를 사용  **\<** 하 여 구성 파일 계층 구조에서 상위 수준에 정의 된 섹션 및 섹션 그룹을 응용 프로그램에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="471ed-121">예제</span><span class="sxs-lookup"><span data-stu-id="471ed-121">Example</span></span>

<span data-ttu-id="471ed-122">다음 예제에서는 응용 프로그램 구성 파일에서  **\<remove >** 요소를 사용 하 여 컴퓨터 구성 파일에 이전에 정의 된 섹션을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="471ed-123">다음 컴퓨터 구성 파일 코드는  **\<sampleSection >** 섹션을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="471ed-124">다음 응용 프로그램 구성 파일 코드는  **\<sampleSection >** 섹션을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="471ed-125">제거 후 응용 프로그램은  **\<sampleSection >** 에서 설정을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="471ed-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="471ed-126">Configuration file</span></span>

<span data-ttu-id="471ed-127">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (machine.config) 및응용 프로그램 디렉터리 수준에 없는 web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="471ed-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="471ed-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="471ed-128">See also</span></span>

- [<span data-ttu-id="471ed-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="471ed-129">Configuration file schema for the .NET Framework</span></span>](index.md)
