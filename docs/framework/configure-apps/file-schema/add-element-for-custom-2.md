---
title: <add>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 57722f3518fad12cb8e6e35d68f40bb8465bdd86
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215445"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="f8b29-102">\<add>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="f8b29-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="f8b29-103">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-103">Adds custom application settings.</span></span> <span data-ttu-id="f8b29-104">각 **\<add>** 태그에는 키/값 쌍이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-104">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="f8b29-105">구문</span><span class="sxs-lookup"><span data-stu-id="f8b29-105">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="f8b29-106">특성</span><span class="sxs-lookup"><span data-stu-id="f8b29-106">Attributes</span></span>

| <span data-ttu-id="f8b29-107">attribute</span><span class="sxs-lookup"><span data-stu-id="f8b29-107">Attribute</span></span> | <span data-ttu-id="f8b29-108">Description</span><span class="sxs-lookup"><span data-stu-id="f8b29-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f8b29-109">**key**</span><span class="sxs-lookup"><span data-stu-id="f8b29-109">**key**</span></span>   | <span data-ttu-id="f8b29-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-110">Required attribute.</span></span><br><br><span data-ttu-id="f8b29-111">설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-111">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="f8b29-112">**value**</span><span class="sxs-lookup"><span data-stu-id="f8b29-112">**value**</span></span> | <span data-ttu-id="f8b29-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-113">Required attribute.</span></span><br><br><span data-ttu-id="f8b29-114">설정 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-114">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f8b29-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f8b29-115">Parent element</span></span>

| <span data-ttu-id="f8b29-116">요소</span><span class="sxs-lookup"><span data-stu-id="f8b29-116">Element</span></span> | <span data-ttu-id="f8b29-117">Description</span><span class="sxs-lookup"><span data-stu-id="f8b29-117">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="f8b29-118">**\<sectionName>** 요소인</span><span class="sxs-lookup"><span data-stu-id="f8b29-118">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="f8b29-119">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-119">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f8b29-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f8b29-120">Child elements</span></span>

<span data-ttu-id="f8b29-121">None</span><span class="sxs-lookup"><span data-stu-id="f8b29-121">None</span></span>

## <a name="example"></a><span data-ttu-id="f8b29-122">예제</span><span class="sxs-lookup"><span data-stu-id="f8b29-122">Example</span></span>

<span data-ttu-id="f8b29-123">다음 예제에서는 사용자 지정 구성 섹션을 정의 하 고 요소를 사용 하 여 섹션에 설정을 추가 하는 방법을 보여 줍니다 **\<add>** .</span><span class="sxs-lookup"><span data-stu-id="f8b29-123">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="f8b29-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f8b29-124">Configuration file</span></span>

<span data-ttu-id="f8b29-125">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b29-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f8b29-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8b29-126">See also</span></span>

- [<span data-ttu-id="f8b29-127">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f8b29-127">Configuration file schema for the .NET Framework</span></span>](index.md)
