---
description: '자세히 알아보기: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소'
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
ms.openlocfilehash: c1bb5b2fb321e2cc9235e02be2158c0875d42032
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698728"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="5b770-103">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="5b770-103">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="5b770-104">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-104">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;**\<sectionName>**

## <a name="attributes"></a><span data-ttu-id="5b770-105">특성</span><span class="sxs-lookup"><span data-stu-id="5b770-105">Attributes</span></span>

<span data-ttu-id="5b770-106">None</span><span class="sxs-lookup"><span data-stu-id="5b770-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="5b770-107">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5b770-107">Parent element</span></span>

|     | <span data-ttu-id="5b770-108">설명</span><span class="sxs-lookup"><span data-stu-id="5b770-108">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="5b770-109">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-109">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="5b770-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5b770-110">Child elements</span></span>

|     | <span data-ttu-id="5b770-111">설명</span><span class="sxs-lookup"><span data-stu-id="5b770-111">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="5b770-112">[**\<add>**](add-element-for-custom-2.md)및의 경우 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5b770-112">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="5b770-113">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-113">Adds custom application settings.</span></span> |
| <span data-ttu-id="5b770-114">[**\<remove>**](remove-element-for-custom-2.md)및의 경우 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5b770-114">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="5b770-115">이전에 정의 된 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-115">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="5b770-116">[**\<clear>**](clear-element-for-custom-2.md)및의 경우 <xref:System.Configuration.NameValueSectionHandler><xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="5b770-116">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="5b770-117">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-117">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5b770-118">설명</span><span class="sxs-lookup"><span data-stu-id="5b770-118">Remarks</span></span>

<span data-ttu-id="5b770-119">**\<sectionName>** 요소는 요소의 태그에 의해 정의 되는 사용자 지정 요소입니다 **\<section>** **\<configSections>** .</span><span class="sxs-lookup"><span data-stu-id="5b770-119">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="5b770-120">다음 표에서는 ConfigurationSettings의 개체 형식을 보여 줍니다. GetConfig 메서드는 각 구성 섹션 처리기에 대해를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-120">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="5b770-121">구성 섹션 처리기</span><span class="sxs-lookup"><span data-stu-id="5b770-121">Configuration section handler</span></span>                        | <span data-ttu-id="5b770-122">반환 형식</span><span class="sxs-lookup"><span data-stu-id="5b770-122">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="5b770-123">예제</span><span class="sxs-lookup"><span data-stu-id="5b770-123">Example</span></span>

<span data-ttu-id="5b770-124">다음 예제에서는 및 클래스를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다 <xref:System.Configuration.DictionarySectionHandler> <xref:System.Configuration.NameValueSectionHandler> .</span><span class="sxs-lookup"><span data-stu-id="5b770-124">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="5b770-125">첫 번째 사용자 지정 요소는 이며,이는 **\<dictionarySample>** <xref:System.Configuration.DictionarySectionHandler> 어셈블리의 클래스에서 읽은 설정을 포함 합니다 `System.dll` .</span><span class="sxs-lookup"><span data-stu-id="5b770-125">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="5b770-126">두 번째 사용자 지정 요소는 이며,이는 **\<mySection>** <xref:System.Configuration.NameValueSectionHandler> 어셈블리의 클래스에서 읽은 설정을 포함 합니다 `System.dll` .</span><span class="sxs-lookup"><span data-stu-id="5b770-126">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

```xml
<configuration>
  <configSections>
    <section name="dictionarySample" type="System.Configuration.DictionarySectionHandler,System" />
    <sectionGroup name="mySectionGroup">
      <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
    </sectionGroup>
  </configSections>
  <dictionarySample>
    <add key="myKey" value="myValue" />
  </dictionarySample>
  <mySectionGroup>
    <mySection>
      <add key="key1" value="value1" />
    </mySection>
  </mySectionGroup>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="5b770-127">구성 파일</span><span class="sxs-lookup"><span data-stu-id="5b770-127">Configuration file</span></span>

<span data-ttu-id="5b770-128">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b770-128">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b770-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b770-129">See also</span></span>

- [<span data-ttu-id="5b770-130">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="5b770-130">Configuration file schema for the .NET Framework</span></span>](index.md)
