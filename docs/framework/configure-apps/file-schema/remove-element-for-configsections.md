---
title: <configSections>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/configSections/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: ae4d82e0-e8fe-468c-81ab-46d63c4d66a8
ms.openlocfilehash: 6991e3f73ac180fc690ec48e1a0d15f40c915733
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154532"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="1a0f6-102">\<> 구성에 \<대한> 요소 제거</span><span class="sxs-lookup"><span data-stu-id="1a0f6-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="1a0f6-103">미리 정의된 단면 또는 단면 그룹을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-103">Removes a predefined section or section group.</span></span>

<span data-ttu-id="1a0f6-104">[**\<구성>**](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1a0f6-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="1a0f6-105">&nbsp;&nbsp;[**\<>섹션**](configsections-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="1a0f6-105">&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)</span></span>\
<span data-ttu-id="1a0f6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<>제거**</span><span class="sxs-lookup"><span data-stu-id="1a0f6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1a0f6-107">구문</span><span class="sxs-lookup"><span data-stu-id="1a0f6-107">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="1a0f6-108">attribute</span><span class="sxs-lookup"><span data-stu-id="1a0f6-108">Attribute</span></span>

|           | <span data-ttu-id="1a0f6-109">Description</span><span class="sxs-lookup"><span data-stu-id="1a0f6-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="1a0f6-110">**(이름)**</span><span class="sxs-lookup"><span data-stu-id="1a0f6-110">**name**</span></span>  | <span data-ttu-id="1a0f6-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-111">Required attribute.</span></span><br><br><span data-ttu-id="1a0f6-112">제거할 단면 또는 단면 그룹의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-112">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="1a0f6-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1a0f6-113">Parent element</span></span>

|     | <span data-ttu-id="1a0f6-114">Description</span><span class="sxs-lookup"><span data-stu-id="1a0f6-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1a0f6-115">\*\* \<>구성섹션\*\* 요소</span><span class="sxs-lookup"><span data-stu-id="1a0f6-115">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="1a0f6-116">구성 섹션 및 네임스페이스 선언을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-116">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1a0f6-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1a0f6-117">Child elements</span></span>

<span data-ttu-id="1a0f6-118">None</span><span class="sxs-lookup"><span data-stu-id="1a0f6-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="1a0f6-119">설명</span><span class="sxs-lookup"><span data-stu-id="1a0f6-119">Remarks</span></span>

<span data-ttu-id="1a0f6-120">제거>요소를 사용하여 구성 파일 계층 구조의 상위 수준에서 정의된 응용 프로그램에서 섹션 및 단면 그룹을 제거할 수 있습니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="1a0f6-120">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="1a0f6-121">예제</span><span class="sxs-lookup"><span data-stu-id="1a0f6-121">Example</span></span>

<span data-ttu-id="1a0f6-122">다음 예제에서는 응용 프로그램 구성 파일에서 \*\* \<제거>\*\* 요소를 사용하여 이전에 컴퓨터 구성 파일에 정의된 섹션을 제거하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-122">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="1a0f6-123">다음 컴퓨터 구성 파일 코드는 섹션 \*\* \<sampleSection>\*\* 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-123">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

```xml
<!-- Machine.config file -->
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

<span data-ttu-id="1a0f6-124">다음 응용 프로그램 구성 파일 코드는 \*\* \<샘플섹션을>.\*\*</span><span class="sxs-lookup"><span data-stu-id="1a0f6-124">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="1a0f6-125">제거 후 응용 프로그램은 \*\* \<sampleSection>\*\* 설정을 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-125">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="1a0f6-126">구성 파일</span><span class="sxs-lookup"><span data-stu-id="1a0f6-126">Configuration file</span></span>

<span data-ttu-id="1a0f6-127">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a0f6-127">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a0f6-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1a0f6-128">See also</span></span>

- [<span data-ttu-id="1a0f6-129">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="1a0f6-129">Configuration file schema for the .NET Framework</span></span>](index.md)
