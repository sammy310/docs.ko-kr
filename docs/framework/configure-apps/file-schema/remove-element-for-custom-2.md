---
description: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소에 대해 자세히 알아보세요. <remove>
title: <remove> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 8d8af7f5-26c9-4db9-bbe4-b2a4e6949568
ms.openlocfilehash: bf1434b257aa014c8f46e34f2d57d109bd510452
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740082"
---
# <a name="remove-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="42557-103">\<remove> NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="42557-103">\<remove> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="42557-104">이전에 정의 된 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="42557-104">Removes a previously defined setting.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="42557-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="42557-105">Syntax</span></span>

```xml
<add remove="key" />
```

## <a name="attribute"></a><span data-ttu-id="42557-106">attribute</span><span class="sxs-lookup"><span data-stu-id="42557-106">Attribute</span></span>

|           | <span data-ttu-id="42557-107">Description</span><span class="sxs-lookup"><span data-stu-id="42557-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="42557-108">**key**</span><span class="sxs-lookup"><span data-stu-id="42557-108">**key**</span></span>   | <span data-ttu-id="42557-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="42557-109">Required attribute.</span></span><br><br><span data-ttu-id="42557-110">제거할 설정의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="42557-110">Specifies the name of the setting to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="42557-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="42557-111">Parent element</span></span>

| <span data-ttu-id="42557-112">요소</span><span class="sxs-lookup"><span data-stu-id="42557-112">Element</span></span> | <span data-ttu-id="42557-113">설명</span><span class="sxs-lookup"><span data-stu-id="42557-113">Description</span></span> |
| ------- | ------------|
| [<span data-ttu-id="42557-114">**\<sectionName>** 요소</span><span class="sxs-lookup"><span data-stu-id="42557-114">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="42557-115">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="42557-115">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="42557-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="42557-116">Child elements</span></span>

<span data-ttu-id="42557-117">없음</span><span class="sxs-lookup"><span data-stu-id="42557-117">None</span></span>

## <a name="remarks"></a><span data-ttu-id="42557-118">설명</span><span class="sxs-lookup"><span data-stu-id="42557-118">Remarks</span></span>

<span data-ttu-id="42557-119">요소를 사용 하 여 **\<remove>** 구성 파일 계층 구조에서 상위 수준에 정의 된 응용 프로그램의 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42557-119">You can use the **\<remove>** element to remove settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="42557-120">예제</span><span class="sxs-lookup"><span data-stu-id="42557-120">Example</span></span>

<span data-ttu-id="42557-121">다음 예제에서는 **\<remove>** 응용 프로그램 구성 파일에서 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 설정을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="42557-121">The following example shows how to use the **\<remove>** element in an application configuration file to remove settings previously defined in the machine configuration file.</span></span>

<span data-ttu-id="42557-122">다음 컴퓨터 구성 파일 코드는 섹션을 선언 하 **\<mySection>** 고 두 개의 설정 인 및를 추가 합니다 `key1` `key2` .</span><span class="sxs-lookup"><span data-stu-id="42557-122">The following machine configuration file code declares the section **\<mySection>** and adds two settings, `key1` and `key2`, to it:</span></span>

```xml
<!-- Machine.config file -->
<configuration>
  <configSections>
    <section name="mySection" type="System.Configuration.NameValueSectionHandler,System" />
  </configSections>
  <mySection>
    <add key="key1" value="value1" />
    <add key="key2" value="value2" />
  </mySection>
</configuration>
```

<span data-ttu-id="42557-123">다음 응용 프로그램 구성 파일 코드는 `key2` 에서 설정을 제거 합니다 **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="42557-123">The following application configuration file code removes the `key2` setting from **\<mySection>**:</span></span>

```xml
<!--Application configuration file -->
<configuration>
  <mySection>
    <remove key="key2" />
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="42557-124">구성 파일</span><span class="sxs-lookup"><span data-stu-id="42557-124">Configuration file</span></span>

<span data-ttu-id="42557-125">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42557-125">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="42557-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="42557-126">See also</span></span>

- [<span data-ttu-id="42557-127">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="42557-127">Configuration file schema for the .NET Framework</span></span>](index.md)
