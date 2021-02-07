---
description: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소에 대해 자세히 알아보세요. <add>
title: <add> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
ms.openlocfilehash: 5a8cf22b21370e60086408f792f8137386d07aa3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99713054"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="f0a03-103">\<add> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="f0a03-103">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="f0a03-104">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-104">Adds custom application settings.</span></span> <span data-ttu-id="f0a03-105">각 **\<add>** 태그에는 키/값 쌍이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-105">Each **\<add>** tag contains a key/value pair.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="f0a03-106">구문</span><span class="sxs-lookup"><span data-stu-id="f0a03-106">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="f0a03-107">특성</span><span class="sxs-lookup"><span data-stu-id="f0a03-107">Attributes</span></span>

| <span data-ttu-id="f0a03-108">attribute</span><span class="sxs-lookup"><span data-stu-id="f0a03-108">Attribute</span></span> | <span data-ttu-id="f0a03-109">Description</span><span class="sxs-lookup"><span data-stu-id="f0a03-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f0a03-110">**key**</span><span class="sxs-lookup"><span data-stu-id="f0a03-110">**key**</span></span>   | <span data-ttu-id="f0a03-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-111">Required attribute.</span></span><br><br><span data-ttu-id="f0a03-112">설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-112">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="f0a03-113">**value**</span><span class="sxs-lookup"><span data-stu-id="f0a03-113">**value**</span></span> | <span data-ttu-id="f0a03-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-114">Required attribute.</span></span><br><br><span data-ttu-id="f0a03-115">설정 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-115">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f0a03-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f0a03-116">Parent element</span></span>

| <span data-ttu-id="f0a03-117">요소</span><span class="sxs-lookup"><span data-stu-id="f0a03-117">Element</span></span> | <span data-ttu-id="f0a03-118">설명</span><span class="sxs-lookup"><span data-stu-id="f0a03-118">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="f0a03-119">**\<sectionName>** 요소</span><span class="sxs-lookup"><span data-stu-id="f0a03-119">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="f0a03-120">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-120">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f0a03-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f0a03-121">Child elements</span></span>

<span data-ttu-id="f0a03-122">없음</span><span class="sxs-lookup"><span data-stu-id="f0a03-122">None</span></span>

## <a name="example"></a><span data-ttu-id="f0a03-123">예제</span><span class="sxs-lookup"><span data-stu-id="f0a03-123">Example</span></span>

<span data-ttu-id="f0a03-124">다음 예제에서는 사용자 지정 구성 섹션을 정의 하 고 요소를 사용 하 여 섹션에 설정을 추가 하는 방법을 보여 줍니다 **\<add>** .</span><span class="sxs-lookup"><span data-stu-id="f0a03-124">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="f0a03-125">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f0a03-125">Configuration file</span></span>

<span data-ttu-id="f0a03-126">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a03-126">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0a03-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0a03-127">See also</span></span>

- [<span data-ttu-id="f0a03-128">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f0a03-128">Configuration file schema for the .NET Framework</span></span>](index.md)
