---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 <add> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215445"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="6b5a5-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 > 요소 \<추가</span><span class="sxs-lookup"><span data-stu-id="6b5a5-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="6b5a5-103">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-103">Adds custom application settings.</span></span> <span data-ttu-id="6b5a5-104">각 **\<추가 >** 태그에는 키/값 쌍이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="6b5a5-105">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6b5a5-105">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="6b5a5-106">&nbsp;&nbsp;[ **\<섹션 이름 >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="6b5a5-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="6b5a5-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<추가**</span><span class="sxs-lookup"><span data-stu-id="6b5a5-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6b5a5-108">구문</span><span class="sxs-lookup"><span data-stu-id="6b5a5-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="6b5a5-109">특성</span><span class="sxs-lookup"><span data-stu-id="6b5a5-109">Attributes</span></span>

| <span data-ttu-id="6b5a5-110">attribute</span><span class="sxs-lookup"><span data-stu-id="6b5a5-110">Attribute</span></span> | <span data-ttu-id="6b5a5-111">Description</span><span class="sxs-lookup"><span data-stu-id="6b5a5-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6b5a5-112">**key**</span><span class="sxs-lookup"><span data-stu-id="6b5a5-112">**key**</span></span>   | <span data-ttu-id="6b5a5-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-113">Required attribute.</span></span><br><br><span data-ttu-id="6b5a5-114">설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="6b5a5-115">**value**</span><span class="sxs-lookup"><span data-stu-id="6b5a5-115">**value**</span></span> | <span data-ttu-id="6b5a5-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-116">Required attribute.</span></span><br><br><span data-ttu-id="6b5a5-117">설정 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6b5a5-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6b5a5-118">Parent element</span></span>

| <span data-ttu-id="6b5a5-119">요소</span><span class="sxs-lookup"><span data-stu-id="6b5a5-119">Element</span></span> | <span data-ttu-id="6b5a5-120">Description</span><span class="sxs-lookup"><span data-stu-id="6b5a5-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="6b5a5-121"> **\<섹션 이름 >** 요소인</span><span class="sxs-lookup"><span data-stu-id="6b5a5-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="6b5a5-122"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="6b5a5-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6b5a5-123">Child elements</span></span>

<span data-ttu-id="6b5a5-124">None</span><span class="sxs-lookup"><span data-stu-id="6b5a5-124">None</span></span>

## <a name="example"></a><span data-ttu-id="6b5a5-125">예제</span><span class="sxs-lookup"><span data-stu-id="6b5a5-125">Example</span></span>

<span data-ttu-id="6b5a5-126">다음 예제에서는 사용자 지정 구성 섹션을 정의 하 고 **\<> 요소 추가** 를 사용 하 여 설정을 섹션에 배치 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="6b5a5-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="6b5a5-127">Configuration file</span></span>

<span data-ttu-id="6b5a5-128">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b5a5-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="6b5a5-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b5a5-129">See also</span></span>

- [<span data-ttu-id="6b5a5-130">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6b5a5-130">Configuration file schema for the .NET Framework</span></span>](index.md)
