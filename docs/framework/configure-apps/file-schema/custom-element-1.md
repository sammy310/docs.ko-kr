---
title: SingleTagSectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8fae3673fe72d036802cb1a8366aaa2430c38884
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927496"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="0b001-102">SingleTagSectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="0b001-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="0b001-103">\<섹션 > 요소에 정의 되 고 클래스를 <xref:System.Configuration.SingleTagSectionHandler> 사용 하는 사용자 지정 구성 섹션의 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b001-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="0b001-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0b001-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="0b001-105">&nbsp;&nbsp; *\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="0b001-105">&nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="0b001-106">구문</span><span class="sxs-lookup"><span data-stu-id="0b001-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="0b001-107">특성</span><span class="sxs-lookup"><span data-stu-id="0b001-107">Attributes</span></span>

<span data-ttu-id="0b001-108">특성 및 특성 값은 사용자 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0b001-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="0b001-109">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0b001-109">Parent element</span></span>

|     | <span data-ttu-id="0b001-110">설명</span><span class="sxs-lookup"><span data-stu-id="0b001-110">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0b001-111"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="0b001-111">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="0b001-112">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0b001-112">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0b001-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0b001-113">Child elements</span></span>

<span data-ttu-id="0b001-114">없음</span><span class="sxs-lookup"><span data-stu-id="0b001-114">None</span></span>

## <a name="remarks"></a><span data-ttu-id="0b001-115">설명</span><span class="sxs-lookup"><span data-stu-id="0b001-115">Remarks</span></span>

<span data-ttu-id="0b001-116">섹션 이름 > 요소는 [**configsections > 요소의 section > 태그에 의해 정의 되는 사용자 지정 요소입니다. \<** ](configsections-element-for-configuration.md) [ **\<** ](section-element.md)  **\<**</span><span class="sxs-lookup"><span data-stu-id="0b001-116">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="0b001-117">를 호출할 <xref:System.Collections.IDictionary> <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>때 구성 시스템에서 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b001-117">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="0b001-118">예제</span><span class="sxs-lookup"><span data-stu-id="0b001-118">Example</span></span>

<span data-ttu-id="0b001-119">다음 예제에서는 <xref:System.Configuration.SingleTagSectionHandler> 클래스에서 읽은 설정을 포함 하는  **\<sampleSection >** 이라는 사용자 지정 요소를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0b001-119">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

```xml
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

## <a name="configuration-file"></a><span data-ttu-id="0b001-120">구성 파일</span><span class="sxs-lookup"><span data-stu-id="0b001-120">Configuration file</span></span>

<span data-ttu-id="0b001-121">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (machine.config) 및응용 프로그램 디렉터리 수준에 없는 web.config 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0b001-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="0b001-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="0b001-122">See also</span></span>

- [<span data-ttu-id="0b001-123">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="0b001-123">Configuration file schema for the .NET Framework</span></span>](index.md)
