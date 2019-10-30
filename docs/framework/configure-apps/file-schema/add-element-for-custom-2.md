---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 <add> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 0d4ddb53-eb2b-49c0-9c33-a8dec5c39b46
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e7d68530ae1f0666fc4940ffe7605c3bf8dfe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73119605"
---
# <a name="add-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="d5d86-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 > 요소 \<추가</span><span class="sxs-lookup"><span data-stu-id="d5d86-102">\<add> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="d5d86-103">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-103">Adds custom application settings.</span></span> <span data-ttu-id="d5d86-104">각 **\<추가 >** 태그에는 키/값 쌍이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-104">Each **\<add>** tag contains a key/value pair.</span></span>

<span data-ttu-id="d5d86-105">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="d5d86-105">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="d5d86-106">&nbsp;&nbsp;[ **\<섹션 이름 >** ](custom-element-2.md) </span><span class="sxs-lookup"><span data-stu-id="d5d86-106">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md) </span></span>  
<span data-ttu-id="d5d86-107">&nbsp;&nbsp;&nbsp;&nbsp; **\<추가**</span><span class="sxs-lookup"><span data-stu-id="d5d86-107">&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d5d86-108">구문</span><span class="sxs-lookup"><span data-stu-id="d5d86-108">Syntax</span></span>

```xml
<add key="key" value="value" />
```

## <a name="attributes"></a><span data-ttu-id="d5d86-109">특성</span><span class="sxs-lookup"><span data-stu-id="d5d86-109">Attributes</span></span>

| <span data-ttu-id="d5d86-110">특성</span><span class="sxs-lookup"><span data-stu-id="d5d86-110">Attribute</span></span> | <span data-ttu-id="d5d86-111">설명</span><span class="sxs-lookup"><span data-stu-id="d5d86-111">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="d5d86-112">**key**</span><span class="sxs-lookup"><span data-stu-id="d5d86-112">**key**</span></span>   | <span data-ttu-id="d5d86-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-113">Required attribute.</span></span><br><br><span data-ttu-id="d5d86-114">설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-114">Specifies the name of the setting.</span></span> |
| <span data-ttu-id="d5d86-115">**value**</span><span class="sxs-lookup"><span data-stu-id="d5d86-115">**value**</span></span> | <span data-ttu-id="d5d86-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-116">Required attribute.</span></span><br><br><span data-ttu-id="d5d86-117">설정 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-117">Specifies the value of the setting.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="d5d86-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d5d86-118">Parent element</span></span>

| <span data-ttu-id="d5d86-119">요소</span><span class="sxs-lookup"><span data-stu-id="d5d86-119">Element</span></span> | <span data-ttu-id="d5d86-120">설명</span><span class="sxs-lookup"><span data-stu-id="d5d86-120">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="d5d86-121"> **\<섹션 이름 >** 요소인</span><span class="sxs-lookup"><span data-stu-id="d5d86-121">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="d5d86-122"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-122">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="d5d86-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d5d86-123">Child elements</span></span>

<span data-ttu-id="d5d86-124">없음</span><span class="sxs-lookup"><span data-stu-id="d5d86-124">None</span></span>

## <a name="example"></a><span data-ttu-id="d5d86-125">예제</span><span class="sxs-lookup"><span data-stu-id="d5d86-125">Example</span></span>

<span data-ttu-id="d5d86-126">다음 예제에서는 사용자 지정 구성 섹션을 정의 하 고 **\<> 요소 추가** 를 사용 하 여 설정을 섹션에 배치 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-126">The following example shows how to define a custom configuration section and use the **\<add>** element to put settings into the section:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="d5d86-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="d5d86-127">Configuration file</span></span>

<span data-ttu-id="d5d86-128">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d86-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5d86-129">참조</span><span class="sxs-lookup"><span data-stu-id="d5d86-129">See also</span></span>

- [<span data-ttu-id="d5d86-130">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d5d86-130">Configuration file schema for the .NET Framework</span></span>](index.md)
