---
title: <clear> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: e5ab12150c5200dc346e950541443d5286f739c8
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301244"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="e3bda-102">\<지우기 > NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="e3bda-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="e3bda-103">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="e3bda-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="e3bda-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="e3bda-105">&nbsp;&nbsp;[ **\<sectionName>** ](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="e3bda-105">&nbsp;&nbsp;[**\<sectionName>**](~/docs/framework/configure-apps/file-schema/custom-element-2.md) </span></span>  
<span data-ttu-id="e3bda-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="e3bda-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e3bda-107">구문</span><span class="sxs-lookup"><span data-stu-id="e3bda-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="e3bda-108">특성</span><span class="sxs-lookup"><span data-stu-id="e3bda-108">Attributes</span></span>

<span data-ttu-id="e3bda-109">없음</span><span class="sxs-lookup"><span data-stu-id="e3bda-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="e3bda-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e3bda-110">Parent element</span></span>

|     | <span data-ttu-id="e3bda-111">설명</span><span class="sxs-lookup"><span data-stu-id="e3bda-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="e3bda-112"> *\*\<sectionName>** Element</span><span class="sxs-lookup"><span data-stu-id="e3bda-112">**\<sectionName>** Element</span></span>](~/docs/framework/configure-apps/file-schema/custom-element-2.md) | <span data-ttu-id="e3bda-113">사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다 <xref:System.Configuration.NameValueSectionHandler> 고 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e3bda-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e3bda-114">Child elements</span></span>

<span data-ttu-id="e3bda-115">없음</span><span class="sxs-lookup"><span data-stu-id="e3bda-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e3bda-116">설명</span><span class="sxs-lookup"><span data-stu-id="e3bda-116">Remarks</span></span>

<span data-ttu-id="e3bda-117">사용할 수는  **\<지우기 >** 구성 파일 계층 구조의 상위 수준에 정의 된 응용 프로그램에서 모든 설정을 제거 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="e3bda-118">예제</span><span class="sxs-lookup"><span data-stu-id="e3bda-118">Example</span></span>

<span data-ttu-id="e3bda-119">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고 사용 하는 방법을 보여 줍니다 합니다  **\<지우기 >** 요소에서 이전에 정의 된 섹션의 선택을 취소 하는 응용 프로그램 구성 파일에는 컴퓨터 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="e3bda-120">다음 컴퓨터 구성 파일 코드 섹션을 선언  **\<mySection >** :</span><span class="sxs-lookup"><span data-stu-id="e3bda-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="e3bda-121">다음 응용 프로그램 구성 파일 코드의 모든 설정을 제거  **\<mySection >** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="e3bda-122">응용 프로그램에 선언 된 설정 중 필요한 설정을 검색할 수 없습니다는에  **\<mySection >** 컴퓨터 구성 파일의 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="e3bda-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="e3bda-123">Configuration file</span></span>

<span data-ttu-id="e3bda-124">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="e3bda-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3bda-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3bda-125">See also</span></span>

- [<span data-ttu-id="e3bda-126">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e3bda-126">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
