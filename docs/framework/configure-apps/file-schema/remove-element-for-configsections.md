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
ms.openlocfilehash: 7c0173879c692588cc2e15f0b14a5687bb0404fb
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300670"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="5908f-102">\<제거 > 요소에 대 한 \<configSections ></span><span class="sxs-lookup"><span data-stu-id="5908f-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="5908f-103">미리 정의 된 섹션 또는 섹션 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="5908f-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="5908f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="5908f-105">&nbsp;&nbsp;[ **\<configSections>** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="5908f-105">&nbsp;&nbsp;[**\<configSections>**](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) </span></span>  
<span data-ttu-id="5908f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="5908f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5908f-107">구문</span><span class="sxs-lookup"><span data-stu-id="5908f-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="5908f-108">특성</span><span class="sxs-lookup"><span data-stu-id="5908f-108">Attribute</span></span>

|           | <span data-ttu-id="5908f-109">설명</span><span class="sxs-lookup"><span data-stu-id="5908f-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5908f-110">**name**</span><span class="sxs-lookup"><span data-stu-id="5908f-110">**name**</span></span>  | <span data-ttu-id="5908f-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-111">Required attribute.</span></span><br><br><span data-ttu-id="5908f-112">섹션 또는 제거할 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5908f-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5908f-113">Parent element</span></span>

|     | <span data-ttu-id="5908f-114">설명</span><span class="sxs-lookup"><span data-stu-id="5908f-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="5908f-115"> *\*\<configSections >** 요소</span><span class="sxs-lookup"><span data-stu-id="5908f-115">**\<configSections>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) | <span data-ttu-id="5908f-116">구성 섹션 및 네임 스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5908f-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5908f-117">Child elements</span></span>

<span data-ttu-id="5908f-118">없음</span><span class="sxs-lookup"><span data-stu-id="5908f-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5908f-119">설명</span><span class="sxs-lookup"><span data-stu-id="5908f-119">Remarks</span></span>

<span data-ttu-id="5908f-120">사용할 수는  **\<제거 >** 구성 파일 계층 구조의 상위 수준에 정의 된 응용 프로그램에서 섹션 및 섹션 그룹을 제거할 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="5908f-121">예제</span><span class="sxs-lookup"><span data-stu-id="5908f-121">Example</span></span>

<span data-ttu-id="5908f-122">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<제거 >** 컴퓨터 구성 파일에서 이전에 정의 된 섹션을 제거할 응용 프로그램 구성 파일의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="5908f-123">다음 컴퓨터 구성 파일 코드 섹션을 선언  **\<sampleSection >** :</span><span class="sxs-lookup"><span data-stu-id="5908f-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="5908f-124">다음 응용 프로그램 구성 파일 코드를 제거 합니다  **\<sampleSection >** 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="5908f-125">제거한 후 응용 프로그램의 설정을 검색할 수 없습니다  **\<sampleSection >** 합니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5908f-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="5908f-126">Configuration file</span></span>

<span data-ttu-id="5908f-127">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="5908f-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5908f-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="5908f-128">See also</span></span>

- [<span data-ttu-id="5908f-129">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="5908f-129">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
