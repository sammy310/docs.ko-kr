---
description: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소에 대해 자세히 알아보세요. <clear>
title: <clear> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: 896aa7e8f0e3b41574538fcd9e4be9d6155da889
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699235"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="872d7-103">\<clear> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="872d7-103">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="872d7-104">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="872d7-104">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="872d7-105">구문</span><span class="sxs-lookup"><span data-stu-id="872d7-105">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="872d7-106">특성</span><span class="sxs-lookup"><span data-stu-id="872d7-106">Attributes</span></span>

<span data-ttu-id="872d7-107">None</span><span class="sxs-lookup"><span data-stu-id="872d7-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="872d7-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="872d7-108">Parent element</span></span>

|     | <span data-ttu-id="872d7-109">설명</span><span class="sxs-lookup"><span data-stu-id="872d7-109">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="872d7-110">**\<sectionName>** 요소</span><span class="sxs-lookup"><span data-stu-id="872d7-110">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="872d7-111">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="872d7-111">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="872d7-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="872d7-112">Child elements</span></span>

<span data-ttu-id="872d7-113">없음</span><span class="sxs-lookup"><span data-stu-id="872d7-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="872d7-114">설명</span><span class="sxs-lookup"><span data-stu-id="872d7-114">Remarks</span></span>

<span data-ttu-id="872d7-115">요소를 사용 하 여 **\<clear>** 구성 파일 계층 구조에서 상위 수준에 정의 된 응용 프로그램의 모든 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872d7-115">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="872d7-116">예제</span><span class="sxs-lookup"><span data-stu-id="872d7-116">Example</span></span>

<span data-ttu-id="872d7-117">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고, **\<clear>** 응용 프로그램 구성 파일에서 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 섹션을 지우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="872d7-117">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="872d7-118">다음 컴퓨터 구성 파일 코드는 섹션을 선언 합니다 **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="872d7-118">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="872d7-119">다음 응용 프로그램 구성 파일 코드는에서 모든 설정을 제거 합니다 **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="872d7-119">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="872d7-120">응용 프로그램은 **\<mySection>** 컴퓨터 구성 파일의 섹션에 있는에서 선언 된 설정을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="872d7-120">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="872d7-121">구성 파일</span><span class="sxs-lookup"><span data-stu-id="872d7-121">Configuration file</span></span>

<span data-ttu-id="872d7-122">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="872d7-122">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="872d7-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="872d7-123">See also</span></span>

- [<span data-ttu-id="872d7-124">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="872d7-124">Configuration file schema for the .NET Framework</span></span>](index.md)
