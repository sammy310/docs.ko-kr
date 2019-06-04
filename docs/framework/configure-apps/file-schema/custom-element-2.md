---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: 2303031f-4c1d-4df4-bca1-e9bd96ca40dc
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 8636050b2618d1b2c2da0c08c756b0ed221c7f6f
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300768"
---
# <a name="custom-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="af35f-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 사용자 지정 요소</span><span class="sxs-lookup"><span data-stu-id="af35f-102">Custom element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="af35f-103">사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다 <xref:System.Configuration.NameValueSectionHandler> 고 <xref:System.Configuration.DictionarySectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-103">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span>

<span data-ttu-id="af35f-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span><span class="sxs-lookup"><span data-stu-id="af35f-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)\\</span></span>
<span data-ttu-id="af35f-105">&nbsp;&nbsp; **\<sectionName>**</span><span class="sxs-lookup"><span data-stu-id="af35f-105">&nbsp;&nbsp;**\<sectionName>**</span></span>

## <a name="attributes"></a><span data-ttu-id="af35f-106">특성</span><span class="sxs-lookup"><span data-stu-id="af35f-106">Attributes</span></span>

<span data-ttu-id="af35f-107">없음</span><span class="sxs-lookup"><span data-stu-id="af35f-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="af35f-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="af35f-108">Parent element</span></span>

|     | <span data-ttu-id="af35f-109">설명</span><span class="sxs-lookup"><span data-stu-id="af35f-109">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="af35f-110"> *\*\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="af35f-110">**\<configuration>**</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="af35f-111">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-111">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="af35f-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="af35f-112">Child elements</span></span>

|     | <span data-ttu-id="af35f-113">설명</span><span class="sxs-lookup"><span data-stu-id="af35f-113">Description</span></span> |
| --- | ----------- |
| <span data-ttu-id="af35f-114">[ **\<추가 >** ](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="af35f-114">[**\<add>**](~/docs/framework/configure-apps/file-schema/add-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span>  | <span data-ttu-id="af35f-115">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-115">Adds custom application settings.</span></span> |
| <span data-ttu-id="af35f-116">[ **\<제거 >** ](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="af35f-116">[**\<remove>**](~/docs/framework/configure-apps/file-schema/remove-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="af35f-117">이전에 정의 된 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-117">Removes a previously defined setting.</span></span> |
| <span data-ttu-id="af35f-118">[ **\<지우기 >** ](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) 에 대 한 <xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler></span><span class="sxs-lookup"><span data-stu-id="af35f-118">[**\<clear>**](~/docs/framework/configure-apps/file-schema/clear-element-for-custom-2.md) for <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler></span></span> | <span data-ttu-id="af35f-119">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-119">Clears all previously defined settings in a section.</span></span> |

## <a name="remarks"></a><span data-ttu-id="af35f-120">설명</span><span class="sxs-lookup"><span data-stu-id="af35f-120">Remarks</span></span>

<span data-ttu-id="af35f-121">합니다  **\<sectionName >** 정의한 사용자 지정 요소입니다를  **\<섹션 >** 태그를  **\<configSections >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-121">The **\<sectionName>** element is a custom element defined by a **\<section>** tag in the **\<configSections>** element.</span></span>

<span data-ttu-id="af35f-122">다음 표에서 각 구성 섹션 처리기에 대 한 반환 ConfigurationSettings.GetConfig 메서드 개체의 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-122">The following table shows the type of object the ConfigurationSettings.GetConfig method returns for each configuration section handler:</span></span>

| <span data-ttu-id="af35f-123">구성 섹션 처리기</span><span class="sxs-lookup"><span data-stu-id="af35f-123">Configuration section handler</span></span>                        | <span data-ttu-id="af35f-124">반환 형식</span><span class="sxs-lookup"><span data-stu-id="af35f-124">Return type</span></span>                                                |
| ---------------------------------------------------- | ---------------------------------------------------------- |
| <xref:System.Configuration.NameValueSectionHandler>  | <xref:System.Collections.Specialized.NameValueCollection>  |
| <xref:System.Configuration.DictionarySectionHandler> | <xref:System.Collections.IDictionary>                      |

## <a name="example"></a><span data-ttu-id="af35f-125">예제</span><span class="sxs-lookup"><span data-stu-id="af35f-125">Example</span></span>

<span data-ttu-id="af35f-126">다음 예제를 사용 하는 섹션을 선언 하는 방법을 보여 줍니다 합니다 <xref:System.Configuration.DictionarySectionHandler> 고 <xref:System.Configuration.NameValueSectionHandler> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-126">The following example shows how to declare sections that use the <xref:System.Configuration.DictionarySectionHandler> and <xref:System.Configuration.NameValueSectionHandler> classes.</span></span>

<span data-ttu-id="af35f-127">첫 번째 사용자 지정 요소  **\<dictionarySample >** , 읽은 설정을 포함 하는 합니다 <xref:System.Configuration.DictionarySectionHandler> 클래스는 `System.dll` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-127">The first custom element is **\<dictionarySample>**, which contains settings read by the <xref:System.Configuration.DictionarySectionHandler> class in the `System.dll` assembly.</span></span> <span data-ttu-id="af35f-128">두 번째 사용자 지정 요소는  **\<mySection >** , 읽은 설정을 포함 하는 합니다 <xref:System.Configuration.NameValueSectionHandler> 클래스는 `System.dll` 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-128">The second custom element is **\<mySection>**, which contains settings read by the <xref:System.Configuration.NameValueSectionHandler> class in the `System.dll` assembly.</span></span>

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

## <a name="configuration-file"></a><span data-ttu-id="af35f-129">구성 파일</span><span class="sxs-lookup"><span data-stu-id="af35f-129">Configuration file</span></span>

<span data-ttu-id="af35f-130">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="af35f-130">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="af35f-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="af35f-131">See also</span></span>

- [<span data-ttu-id="af35f-132">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="af35f-132">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
