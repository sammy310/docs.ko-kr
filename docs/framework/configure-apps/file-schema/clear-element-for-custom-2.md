---
title: <clear>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214749"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="cf037-102">\<clear>NameValueSectionHandler 및 DictionarySectionHandler에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="cf037-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="cf037-103">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="cf037-103">Clears all previously defined settings in a section.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="cf037-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf037-104">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="cf037-105">특성</span><span class="sxs-lookup"><span data-stu-id="cf037-105">Attributes</span></span>

<span data-ttu-id="cf037-106">None</span><span class="sxs-lookup"><span data-stu-id="cf037-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="cf037-107">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cf037-107">Parent element</span></span>

|     | <span data-ttu-id="cf037-108">Description</span><span class="sxs-lookup"><span data-stu-id="cf037-108">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="cf037-109">**\<sectionName>** 요소인</span><span class="sxs-lookup"><span data-stu-id="cf037-109">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="cf037-110">및 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 <xref:System.Configuration.NameValueSectionHandler> <xref:System.Configuration.DictionarySectionHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf037-110">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="cf037-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cf037-111">Child elements</span></span>

<span data-ttu-id="cf037-112">None</span><span class="sxs-lookup"><span data-stu-id="cf037-112">None</span></span>

## <a name="remarks"></a><span data-ttu-id="cf037-113">설명</span><span class="sxs-lookup"><span data-stu-id="cf037-113">Remarks</span></span>

<span data-ttu-id="cf037-114">요소를 사용 하 여 **\<clear>** 구성 파일 계층 구조에서 상위 수준에 정의 된 응용 프로그램의 모든 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf037-114">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="cf037-115">예제</span><span class="sxs-lookup"><span data-stu-id="cf037-115">Example</span></span>

<span data-ttu-id="cf037-116">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고, **\<clear>** 응용 프로그램 구성 파일에서 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 섹션을 지우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf037-116">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="cf037-117">다음 컴퓨터 구성 파일 코드는 섹션을 선언 합니다 **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="cf037-117">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="cf037-118">다음 응용 프로그램 구성 파일 코드는에서 모든 설정을 제거 합니다 **\<mySection>** .</span><span class="sxs-lookup"><span data-stu-id="cf037-118">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="cf037-119">응용 프로그램은 **\<mySection>** 컴퓨터 구성 파일의 섹션에 있는에서 선언 된 설정을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf037-119">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="cf037-120">구성 파일</span><span class="sxs-lookup"><span data-stu-id="cf037-120">Configuration file</span></span>

<span data-ttu-id="cf037-121">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf037-121">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf037-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf037-122">See also</span></span>

- [<span data-ttu-id="cf037-123">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="cf037-123">Configuration file schema for the .NET Framework</span></span>](index.md)
