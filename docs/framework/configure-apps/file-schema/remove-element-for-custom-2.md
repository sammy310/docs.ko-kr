---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cdd5833e14da1ab5185e56dce1190adfee4a2bf
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089036"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5ae00-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 > 요소 \<제거</span><span class="sxs-lookup"><span data-stu-id="5ae00-102">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5ae00-103">이전에 정의 된 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-103">Removes a previously defined setting.</span></span>

<span data-ttu-id="5ae00-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5ae00-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="5ae00-105">&nbsp;&nbsp;[ **\<섹션 이름 >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="5ae00-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="5ae00-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<제거**</span><span class="sxs-lookup"><span data-stu-id="5ae00-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5ae00-107">구문</span><span class="sxs-lookup"><span data-stu-id="5ae00-107">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="5ae00-108">특성</span><span class="sxs-lookup"><span data-stu-id="5ae00-108">Attribute</span></span>

|           | <span data-ttu-id="5ae00-109">설명</span><span class="sxs-lookup"><span data-stu-id="5ae00-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="5ae00-110">**key**</span><span class="sxs-lookup"><span data-stu-id="5ae00-110">**key**</span></span>   | <span data-ttu-id="5ae00-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-111">Required attribute.</span></span><br><br><span data-ttu-id="5ae00-112">제거할 설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-112">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="5ae00-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5ae00-113">Parent element</span></span>

| <span data-ttu-id="5ae00-114">요소</span><span class="sxs-lookup"><span data-stu-id="5ae00-114">Element</span></span> | <span data-ttu-id="5ae00-115">설명</span><span class="sxs-lookup"><span data-stu-id="5ae00-115">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="5ae00-116"> **\<섹션 이름 >** 요소인</span><span class="sxs-lookup"><span data-stu-id="5ae00-116">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="5ae00-117"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-117">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5ae00-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5ae00-118">Child elements</span></span>

<span data-ttu-id="5ae00-119">없음</span><span class="sxs-lookup"><span data-stu-id="5ae00-119">None</span></span>

## <a name="remarks"></a><span data-ttu-id="5ae00-120">주의</span><span class="sxs-lookup"><span data-stu-id="5ae00-120">Remarks</span></span>

<span data-ttu-id="5ae00-121">**\<제거 >** 요소를 사용 하 여 구성 파일 계층 구조에서 상위 수준으로 정의 된 응용 프로그램에서 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-121">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="5ae00-122">예제</span><span class="sxs-lookup"><span data-stu-id="5ae00-122">Example</span></span>

<span data-ttu-id="5ae00-123">다음 예제에서는 응용 프로그램 구성 파일에서 **\<제거 >** 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 설정을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-123">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="5ae00-124">다음 컴퓨터 구성 파일 코드는 **\<mysection >** 섹션을 선언 하 고이에 `key1` 및 `key2`두 가지 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-124">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

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

<span data-ttu-id="5ae00-125">다음 응용 프로그램 구성 파일 코드는 **\<mySection >** 에서 `key2` 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-125">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5ae00-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="5ae00-126">Configuration file</span></span>

<span data-ttu-id="5ae00-127">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ae00-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5ae00-128">참조</span><span class="sxs-lookup"><span data-stu-id="5ae00-128">See also</span></span>

- [<span data-ttu-id="5ae00-129">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="5ae00-129">Configuration file schema for the .NET Framework</span></span>](index.md)
