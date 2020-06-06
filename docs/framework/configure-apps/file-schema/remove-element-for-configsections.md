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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154532"
---
# <a name="remove-element-for-configsections"></a><span data-ttu-id="f075d-102">\<configSections>에 대한 \<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="f075d-102">\<remove> element for \<configSections></span></span>

<span data-ttu-id="f075d-103">미리 정의 된 섹션 또는 섹션 그룹을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-103">Removes a predefined section or section group.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<configSections>**](configsections-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="f075d-104">구문</span><span class="sxs-lookup"><span data-stu-id="f075d-104">Syntax</span></span>

```xml
<remove name="section name or section group name" />
```

## <a name="attribute"></a><span data-ttu-id="f075d-105">attribute</span><span class="sxs-lookup"><span data-stu-id="f075d-105">Attribute</span></span>

|           | <span data-ttu-id="f075d-106">Description</span><span class="sxs-lookup"><span data-stu-id="f075d-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="f075d-107">**name**</span><span class="sxs-lookup"><span data-stu-id="f075d-107">**name**</span></span>  | <span data-ttu-id="f075d-108">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-108">Required attribute.</span></span><br><br><span data-ttu-id="f075d-109">제거할 섹션 또는 섹션 그룹의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-109">Specifies the name of the section or section group to remove.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="f075d-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f075d-110">Parent element</span></span>

|     | <span data-ttu-id="f075d-111">Description</span><span class="sxs-lookup"><span data-stu-id="f075d-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="f075d-112">**\<configSections>** 요소인</span><span class="sxs-lookup"><span data-stu-id="f075d-112">**\<configSections>** Element</span></span>](configsections-element-for-configuration.md) | <span data-ttu-id="f075d-113">구성 섹션과 네임 스페이스 선언을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-113">Contains configuration section and namespace declarations.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="f075d-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f075d-114">Child elements</span></span>

<span data-ttu-id="f075d-115">None</span><span class="sxs-lookup"><span data-stu-id="f075d-115">None</span></span>

## <a name="remarks"></a><span data-ttu-id="f075d-116">설명</span><span class="sxs-lookup"><span data-stu-id="f075d-116">Remarks</span></span>

<span data-ttu-id="f075d-117">요소를 사용 하 여 **\<remove>** 구성 파일 계층 구조에서 상위 수준에 정의 된 섹션 및 섹션 그룹을 응용 프로그램에서 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-117">You can use the **\<remove>** element to remove sections and section groups from your application that were defined at a higher level in the configuration file hierarchy.</span></span>

## <a name="example"></a><span data-ttu-id="f075d-118">예제</span><span class="sxs-lookup"><span data-stu-id="f075d-118">Example</span></span>

<span data-ttu-id="f075d-119">다음 예제에서는 **\<remove>** 응용 프로그램 구성 파일에서 요소를 사용 하 여 이전에 컴퓨터 구성 파일에 정의 된 섹션을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-119">The following example shows how to use the **\<remove>** element in an application configuration file to remove a section previously defined in the machine configuration file.</span></span>

<span data-ttu-id="f075d-120">다음 컴퓨터 구성 파일 코드는 섹션을 선언 합니다 **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="f075d-120">The following machine configuration file code declares the section **\<sampleSection>**:</span></span>

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

<span data-ttu-id="f075d-121">다음 응용 프로그램 구성 파일 코드는 섹션을 제거 합니다 **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="f075d-121">The following application configuration file code removes the **\<sampleSection>** section.</span></span> <span data-ttu-id="f075d-122">제거 후 응용 프로그램은에서 설정을 검색할 수 없습니다 **\<sampleSection>** .</span><span class="sxs-lookup"><span data-stu-id="f075d-122">After removal, the application cannot retrieve the settings in **\<sampleSection>**.</span></span>

```xml
<!-- Application configuration file -->
<configuration>
  <configSections>
    <remove name="sampleSection"/>
  </configSections>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="f075d-123">구성 파일</span><span class="sxs-lookup"><span data-stu-id="f075d-123">Configuration file</span></span>

<span data-ttu-id="f075d-124">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f075d-124">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="f075d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f075d-125">See also</span></span>

- [<span data-ttu-id="f075d-126">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f075d-126">Configuration file schema for the .NET Framework</span></span>](index.md)
