---
title: <remove>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: cd338ff2d613be31ab1524f6baed6107f803a688
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920941"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="497dc-102">\<NameValueSectionHandler 및 DictionarySectionHandler에 대 한 > 요소 제거</span><span class="sxs-lookup"><span data-stu-id="497dc-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="497dc-103">이전에 정의 된 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="497dc-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="497dc-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="497dc-105">&nbsp;&nbsp;[ **\<sectionName>** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="497dc-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="497dc-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="497dc-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="497dc-107">구문</span><span class="sxs-lookup"><span data-stu-id="497dc-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="497dc-108">특성</span><span class="sxs-lookup"><span data-stu-id="497dc-108">Attribute</span></span>

|           | <span data-ttu-id="497dc-109">설명</span><span class="sxs-lookup"><span data-stu-id="497dc-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="497dc-110">**key**</span><span class="sxs-lookup"><span data-stu-id="497dc-110">**key**</span></span>   | <span data-ttu-id="497dc-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-111">Required attribute.</span></span><br><br><span data-ttu-id="497dc-112">제거할 설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="497dc-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="497dc-113">Parent element</span></span>

| <span data-ttu-id="497dc-114">요소</span><span class="sxs-lookup"><span data-stu-id="497dc-114">Element</span></span> | <span data-ttu-id="497dc-115">Description</span><span class="sxs-lookup"><span data-stu-id="497dc-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="497dc-116">섹션 이름 > 요소  **\<** </span><span class="sxs-lookup"><span data-stu-id="497dc-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="497dc-117"><xref:System.Configuration.NameValueSectionHandler> 및<xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="497dc-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="497dc-118">Child elements</span></span>

<span data-ttu-id="497dc-119">없음</span><span class="sxs-lookup"><span data-stu-id="497dc-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="497dc-120">설명</span><span class="sxs-lookup"><span data-stu-id="497dc-120">Remarks</span></span>

<span data-ttu-id="497dc-121">Remove > 요소를 사용  **\<** 하 여 구성 파일 계층 구조에서 상위 수준에 정의 된 설정을 응용 프로그램에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="497dc-122">예제</span><span class="sxs-lookup"><span data-stu-id="497dc-122">Example</span></span>

<span data-ttu-id="497dc-123">다음 예제에서는 응용 프로그램 구성 파일에서  **\<remove >** 요소를 사용 하 여 컴퓨터 구성 파일에 이전에 정의 된 설정을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="497dc-124">다음 컴퓨터 구성 파일 코드는  **\<mysection >** 섹션을 선언 하 고이에 `key2`두 `key1` 가지 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="497dc-125">다음 응용 프로그램 구성 파일 코드는 `key2`  **\<mysection >** 에서 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="497dc-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="497dc-126">Configuration file</span></span>

<span data-ttu-id="497dc-127">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (machine.config) 및응용 프로그램 디렉터리 수준에 없는 web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="497dc-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="497dc-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="497dc-128">See also</span></span>

- [<span data-ttu-id="497dc-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="497dc-129">Configuration file schema for the .NET Framework</span></span>](index.md)
