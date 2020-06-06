---
title: <remove>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: d1e4f3478f6afd6a20c01c6b57a137020ee88f5f
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214763"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="04602-102">\<remove>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="04602-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="04602-103">이전에 정의 된 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="04602-103">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="04602-104">구문</span><span class="sxs-lookup"><span data-stu-id="04602-104">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="04602-105">attribute</span><span class="sxs-lookup"><span data-stu-id="04602-105">Attribute</span></span>

|           | <span data-ttu-id="04602-106">Description</span><span class="sxs-lookup"><span data-stu-id="04602-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="04602-107">**key**</span><span class="sxs-lookup"><span data-stu-id="04602-107">**key**</span></span>   | <span data-ttu-id="04602-108">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="04602-108">Required attribute.</span></span><br><br><span data-ttu-id="04602-109">제거할 설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04602-109">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="04602-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="04602-110">Parent element</span></span>

| <span data-ttu-id="04602-111">요소</span><span class="sxs-lookup"><span data-stu-id="04602-111">Element</span></span> | <span data-ttu-id="04602-112">Description</span><span class="sxs-lookup"><span data-stu-id="04602-112">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="04602-113">**\<sectionName>** 요소인</span><span class="sxs-lookup"><span data-stu-id="04602-113">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="04602-114">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="04602-114">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="04602-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="04602-115">Child elements</span></span>

<span data-ttu-id="04602-116">None</span><span class="sxs-lookup"><span data-stu-id="04602-116">None</span></span>

## <a name="remarks"></a><span data-ttu-id="04602-117">설명</span><span class="sxs-lookup"><span data-stu-id="04602-117">Remarks</span></span>

<span data-ttu-id="04602-118">요소를 사용 하 여 **\<remove>** 구성 파일 계층 구조에서 상위 수준에 정의 된 응용 프로그램의 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04602-118">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="04602-119">예제</span><span class="sxs-lookup"><span data-stu-id="04602-119">Example</span></span>

<span data-ttu-id="04602-120">다음 예제에서는 **\<remove>** 응용 프로그램 구성 파일에서 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 설정을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04602-120">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="04602-121">다음 컴퓨터 구성 파일 코드는 섹션을 선언 하 **\<mySection>** 고 두 개의 설정 인 및를 추가 합니다 `key1` `key2` .</span><span class="sxs-lookup"><span data-stu-id="04602-121">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="04602-122">다음 응용 프로그램 구성 파일 코드는 `key2` 에서 설정을 제거 합니다 **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="04602-122">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="04602-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="04602-123">Configuration file</span></span>

<span data-ttu-id="04602-124">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04602-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="04602-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04602-125">See also</span></span>

- [<span data-ttu-id="04602-126">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="04602-126">Configuration file schema for the .NET Framework</span></span>](index.md)
