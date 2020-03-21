---
title: 싱글태그섹션핸들러용 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 04360a796b18cf1e414f1f84bff247a1e9d8ef9c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155156"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="a1a00-102">싱글태그섹션핸들러용 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="a1a00-102">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="a1a00-103">\<섹션> 요소에 의해 정의되고 <xref:System.Configuration.SingleTagSectionHandler> 클래스를 사용하는 사용자 지정 구성 섹션에서 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a00-103">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="a1a00-104">구성 &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) \* \<섹션이름>\*</span><span class="sxs-lookup"><span data-stu-id="a1a00-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="a1a00-105">구문</span><span class="sxs-lookup"><span data-stu-id="a1a00-105">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a><span data-ttu-id="a1a00-106">특성</span><span class="sxs-lookup"><span data-stu-id="a1a00-106">Attributes</span></span>

<span data-ttu-id="a1a00-107">특성 및 특성 값은 사용자가 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a00-107">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="a1a00-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a1a00-108">Parent element</span></span>

|     | <span data-ttu-id="a1a00-109">Description</span><span class="sxs-lookup"><span data-stu-id="a1a00-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="a1a00-110">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="a1a00-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="a1a00-111">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a1a00-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="a1a00-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a1a00-112">Child elements</span></span>

<span data-ttu-id="a1a00-113">None</span><span class="sxs-lookup"><span data-stu-id="a1a00-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="a1a00-114">설명</span><span class="sxs-lookup"><span data-stu-id="a1a00-114">Remarks</span></span>

<span data-ttu-id="a1a00-115">섹션Name>요소는 [\*\* \<구성\*\*](configsections-element-for-configuration.md) 섹션>요소의 [\*\* \<>\*\*](section-element.md) 태그에 의해 정의된 사용자 지정 요소입니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="a1a00-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="a1a00-116">구성 시스템은 을 <xref:System.Collections.IDictionary> 호출할 <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>때 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a00-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="a1a00-117">예제</span><span class="sxs-lookup"><span data-stu-id="a1a00-117">Example</span></span>

<span data-ttu-id="a1a00-118">다음 예제에서는 <xref:System.Configuration.SingleTagSectionHandler> \*\* \<sampleSection>\*\* 라는 사용자 지정 요소를 선언 합니다 만 클래스에서 읽은 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1a00-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="a1a00-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="a1a00-119">Configuration file</span></span>

<span data-ttu-id="a1a00-120">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1a00-120">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1a00-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1a00-121">See also</span></span>

- [<span data-ttu-id="a1a00-122">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="a1a00-122">Configuration file schema for the .NET Framework</span></span>](index.md)
