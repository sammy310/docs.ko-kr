---
title: NameValueSectionHandler 및 DictionarySectionHandler에 대 한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: ff2294ec-fb82-4b0c-933e-ae185433fc7b
ms.openlocfilehash: f6d860f35d22002030ffa3d09dd0d8a96116bf5e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214749"
---
# <a name="clear-element-for-namevaluesectionhandler-and-dictionarysectionhandler"></a><span data-ttu-id="15831-102">NameValueSectionHandler 및 DictionarySectionHandler에 대 한 \<clear > 요소</span><span class="sxs-lookup"><span data-stu-id="15831-102">\<clear> element for NameValueSectionHandler and DictionarySectionHandler</span></span>

<span data-ttu-id="15831-103">섹션에서 이전에 정의 된 모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="15831-103">Clears all previously defined settings in a section.</span></span>

<span data-ttu-id="15831-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15831-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="15831-105">&nbsp;&nbsp;[ **\<섹션 이름 >** ](custom-element-2.md)</span><span class="sxs-lookup"><span data-stu-id="15831-105">&nbsp;&nbsp;[**\<sectionName>**](custom-element-2.md)</span></span>\
<span data-ttu-id="15831-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="15831-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="15831-107">구문</span><span class="sxs-lookup"><span data-stu-id="15831-107">Syntax</span></span>

```xml
<clear />
```

## <a name="attributes"></a><span data-ttu-id="15831-108">특성</span><span class="sxs-lookup"><span data-stu-id="15831-108">Attributes</span></span>

<span data-ttu-id="15831-109">None</span><span class="sxs-lookup"><span data-stu-id="15831-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="15831-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="15831-110">Parent element</span></span>

|     | <span data-ttu-id="15831-111">Description</span><span class="sxs-lookup"><span data-stu-id="15831-111">Description</span></span> |
| --- | ------------|
| [<span data-ttu-id="15831-112"> **\<섹션 이름 >** 요소인</span><span class="sxs-lookup"><span data-stu-id="15831-112">**\<sectionName>** Element</span></span>](custom-element-2.md) | <span data-ttu-id="15831-113"><xref:System.Configuration.NameValueSectionHandler> 및 <xref:System.Configuration.DictionarySectionHandler> 클래스를 사용 하는 사용자 지정 구성 섹션에 대 한 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="15831-113">Defines settings for custom configuration sections that use the <xref:System.Configuration.NameValueSectionHandler> and <xref:System.Configuration.DictionarySectionHandler> classes.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="15831-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="15831-114">Child elements</span></span>

<span data-ttu-id="15831-115">None</span><span class="sxs-lookup"><span data-stu-id="15831-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="15831-116">설명</span><span class="sxs-lookup"><span data-stu-id="15831-116">Remarks</span></span>

<span data-ttu-id="15831-117">**\<clear >** 요소를 사용 하 여 구성 파일 계층 구조에서 상위 수준에 정의 된 응용 프로그램의 모든 설정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15831-117">You can use the **\<clear>** element to remove all settings from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="15831-118">예제</span><span class="sxs-lookup"><span data-stu-id="15831-118">Example</span></span>

<span data-ttu-id="15831-119">이 예제에서는 컴퓨터 구성 파일 및 응용 프로그램 구성 파일을 정의 하 고, 응용 프로그램 구성 파일에서 **\<clear >** 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 섹션을 지우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15831-119">This example defines a machine configuration file and an application configuration file and shows how to use the **\<clear>** element in an application configuration file to clear sections previously defined in the machine configuration file.</span></span>

<span data-ttu-id="15831-120">다음 컴퓨터 구성 파일 코드는 **\<mysection >** 섹션을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="15831-120">The following machine configuration file code declares the section **\<mySection>**:</span></span>

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

<span data-ttu-id="15831-121">다음 응용 프로그램 구성 파일 코드는 **\<mySection >** 에서 모든 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="15831-121">The following application configuration file code removes all settings from **\<mySection>**.</span></span> <span data-ttu-id="15831-122">응용 프로그램은 컴퓨터 구성 파일의 **\<mysection >** 섹션에서에 선언 된 설정을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15831-122">The application cannot retrieve any of the settings that were declared in the in the **\<mySection>** section of the machine configuration file.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <mySection>
    <clear/>
  </mySection>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="15831-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="15831-123">Configuration file</span></span>

<span data-ttu-id="15831-124">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15831-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="15831-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15831-125">See also</span></span>

- [<span data-ttu-id="15831-126">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="15831-126">Configuration file schema for the .NET Framework</span></span>](index.md)
