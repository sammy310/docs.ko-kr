---
description: '자세히 알아보기: SingleTagSectionHandler에 대 한 사용자 지정 요소'
title: SingleTagSectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
ms.openlocfilehash: 83022a1ebf295b89d5f868589e3d9a77c78e3fab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729981"
---
# <a name="custom-element-for-singletagsectionhandler"></a><span data-ttu-id="e8700-103">SingleTagSectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="e8700-103">Custom element for SingleTagSectionHandler</span></span>

<span data-ttu-id="e8700-104">요소에 의해 정의 되 \<section> 고 클래스를 사용 하는 사용자 지정 구성 섹션의 설정을 정의 합니다 <xref:System.Configuration.SingleTagSectionHandler> .</span><span class="sxs-lookup"><span data-stu-id="e8700-104">Defines settings in a custom configuration section that is defined by a \<section> element and uses the <xref:System.Configuration.SingleTagSectionHandler> class.</span></span>

<span data-ttu-id="e8700-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span><span class="sxs-lookup"><span data-stu-id="e8700-105">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;*\<sectionName>*</span></span>

## <a name="syntax"></a><span data-ttu-id="e8700-106">구문</span><span class="sxs-lookup"><span data-stu-id="e8700-106">Syntax</span></span>

```xml
<sectionName key="value" key2="value2" />
```

## <a name="attributes"></a><span data-ttu-id="e8700-107">특성</span><span class="sxs-lookup"><span data-stu-id="e8700-107">Attributes</span></span>

<span data-ttu-id="e8700-108">특성 및 특성 값은 사용자 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8700-108">Attributes and attribute values are user defined.</span></span>

## <a name="parent-element"></a><span data-ttu-id="e8700-109">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e8700-109">Parent element</span></span>

|     | <span data-ttu-id="e8700-110">설명</span><span class="sxs-lookup"><span data-stu-id="e8700-110">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="e8700-111">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e8700-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e8700-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e8700-112">Child elements</span></span>

<span data-ttu-id="e8700-113">없음</span><span class="sxs-lookup"><span data-stu-id="e8700-113">None</span></span>

## <a name="remarks"></a><span data-ttu-id="e8700-114">설명</span><span class="sxs-lookup"><span data-stu-id="e8700-114">Remarks</span></span>

<span data-ttu-id="e8700-115">**\<sectionName>** 요소는 요소의 태그에 의해 정의 되는 사용자 지정 요소입니다 [**\<section>**](section-element.md) [**\<configSections>**](configsections-element-for-configuration.md) .</span><span class="sxs-lookup"><span data-stu-id="e8700-115">The **\<sectionName>** element is a custom element defined by a [**\<section>**](section-element.md) tag in the [**\<configSections>**](configsections-element-for-configuration.md) element.</span></span> <span data-ttu-id="e8700-116">를 호출할 때 구성 시스템에서 개체를 반환 합니다 <xref:System.Collections.IDictionary> <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="e8700-116">The configuration system returns a <xref:System.Collections.IDictionary> object when you call <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="e8700-117">예제</span><span class="sxs-lookup"><span data-stu-id="e8700-117">Example</span></span>

<span data-ttu-id="e8700-118">다음 예제에서는 **\<sampleSection>** 클래스에서 읽은 설정을 포함 하는 라는 사용자 지정 요소를 선언 합니다 <xref:System.Configuration.SingleTagSectionHandler> .</span><span class="sxs-lookup"><span data-stu-id="e8700-118">The following example declares a custom element called **\<sampleSection>** that contains settings read by the <xref:System.Configuration.SingleTagSectionHandler> class:</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="e8700-119">구성 파일</span><span class="sxs-lookup"><span data-stu-id="e8700-119">Configuration file</span></span>

<span data-ttu-id="e8700-120">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8700-120">This element can be used in the application configuration file, the machine configuration file (*Machine.config*), and *Web.config* files that aren't at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8700-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8700-121">See also</span></span>

- [<span data-ttu-id="e8700-122">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e8700-122">Configuration file schema for the .NET Framework</span></span>](index.md)
