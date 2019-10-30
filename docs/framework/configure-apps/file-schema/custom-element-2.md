---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d73c07d58bb226346cb99a1fe50b12bb0e7e746e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118537"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="56a91-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="56a91-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="56a91-103"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="56a91-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="56a91-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="56a91-105">&nbsp;&nbsp; **\<섹션 이름 >**</span><span class="sxs-lookup"><span data-stu-id="56a91-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="56a91-106">특성</span><span class="sxs-lookup"><span data-stu-id="56a91-106">Attributes</span></span>

<span data-ttu-id="56a91-107">없음</span><span class="sxs-lookup"><span data-stu-id="56a91-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="56a91-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="56a91-108">Parent element</span></span>

|     | <span data-ttu-id="56a91-109">설명</span><span class="sxs-lookup"><span data-stu-id="56a91-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="56a91-110"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="56a91-110">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="56a91-111">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="56a91-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="56a91-112">Child elements</span></span>

|     | <span data-ttu-id="56a91-113">설명</span><span class="sxs-lookup"><span data-stu-id="56a91-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="56a91-114"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>에 대 한 [ **> 추가\<** ](add-element-for-custom-2.md)</span><span class="sxs-lookup"><span data-stu-id="56a91-114">[**\<add>**](add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="56a91-115">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="56a91-116"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>에 대 한 [ **> 제거\<** ](remove-element-for-custom-2.md)</span><span class="sxs-lookup"><span data-stu-id="56a91-116">[**\<remove>**](remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="56a91-117">이전에 정의 된 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="56a91-118"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler>에 대 한 [ **> 지우기\<** ](clear-element-for-custom-2.md)</span><span class="sxs-lookup"><span data-stu-id="56a91-118">[**\<clear>**](clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="56a91-119">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="56a91-120">주의</span><span class="sxs-lookup"><span data-stu-id="56a91-120">Remarks</span></span>

<span data-ttu-id="56a91-121">**\<섹션 이름 >** 요소는 **\<configsections >** 요소의 **\<섹션 >** 태그에 의해 정의 되는 사용자 지정 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="56a91-122">다음 표에서는 ConfigurationSettings의 개체 형식을 보여 줍니다. GetConfig 메서드는 각 구성 섹션 처리기에 대해를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="56a91-123">구성 섹션 처리기</span><span class="sxs-lookup"><span data-stu-id="56a91-123">Configuration section handler</span></span>                        | <span data-ttu-id="56a91-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="56a91-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="56a91-125">예제</span><span class="sxs-lookup"><span data-stu-id="56a91-125">Example</span></span>

<span data-ttu-id="56a91-126">다음 예제에서는 <xref:System.Configuration.DictionarySectionHandler> 및 <xref:System.Configuration.NameValueSectionHandler> 클래스를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="56a91-127">첫 번째 사용자 지정 요소는 `System.dll` 어셈블리의 <xref:System.Configuration.DictionarySectionHandler> 클래스에서 읽은 설정을 포함 하는 **\<dictionarySample >** 입니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="56a91-128">두 번째 사용자 지정 요소는 `System.dll` 어셈블리의 <xref:System.Configuration.NameValueSectionHandler> 클래스에서 읽은 설정을 포함 하는 **mySection >\<** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="56a91-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="56a91-129">Configuration file</span></span>

<span data-ttu-id="56a91-130">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56a91-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="56a91-131">참조</span><span class="sxs-lookup"><span data-stu-id="56a91-131">See also</span></span>

- [<span data-ttu-id="56a91-132">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="56a91-132">Configuration file schema for the .NET Framework</span></span>](index.md)
