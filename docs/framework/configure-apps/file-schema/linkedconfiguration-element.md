---
description: '다음에 대 한 자세한 정보: <linkedConfiguration> 요소'
title: <linkedConfiguration> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding/linkedConfiguration
- http://schemas.microsoft.com/.NetConfiguration/v2.0#linkedConfiguration
helpviewer_keywords:
- configuration files [.NET Framework],linked configuration files
- <linkedConfiguration> element
- including configuration files
- linked configuration files
- linkedConfiguration Element
ms.assetid: 8eb34f3b-427e-4288-a7ff-c73f489deb45
ms.openlocfilehash: e4312cf788784241efc35304b632dfe1fdef1bc4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698663"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="406e9-103">\<linkedConfiguration> 요소</span><span class="sxs-lookup"><span data-stu-id="406e9-103">\<linkedConfiguration> element</span></span>

<span data-ttu-id="406e9-104">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-104">Specifies a configuration file to include.</span></span>

[**\<configuration>**](configuration-element.md)\
&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**

## <a name="syntax"></a><span data-ttu-id="406e9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="406e9-105">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="406e9-106">attribute</span><span class="sxs-lookup"><span data-stu-id="406e9-106">Attribute</span></span>

|           | <span data-ttu-id="406e9-107">설명</span><span class="sxs-lookup"><span data-stu-id="406e9-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="406e9-108">**href**</span><span class="sxs-lookup"><span data-stu-id="406e9-108">**href**</span></span>  | <span data-ttu-id="406e9-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-109">Required attribute.</span></span><br><br><span data-ttu-id="406e9-110">포함할 구성 파일의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-110">The URL of the configuration file to include.</span></span> <span data-ttu-id="406e9-111">**Href** 특성에 대해 지원 되는 유일한 형식은 `file://` 입니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-111">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="406e9-112">로컬 파일 및 UNC 파일이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-112">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="406e9-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="406e9-113">Parent element</span></span>

|     | <span data-ttu-id="406e9-114">설명</span><span class="sxs-lookup"><span data-stu-id="406e9-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="406e9-115">**\<assemblyBinding>** 요소</span><span class="sxs-lookup"><span data-stu-id="406e9-115">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="406e9-116">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-116">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="406e9-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="406e9-117">Child elements</span></span>

<span data-ttu-id="406e9-118">없음</span><span class="sxs-lookup"><span data-stu-id="406e9-118">None</span></span>

## <a name="remarks"></a><span data-ttu-id="406e9-119">설명</span><span class="sxs-lookup"><span data-stu-id="406e9-119">Remarks</span></span>

<span data-ttu-id="406e9-120">**\<linkedConfiguration>** 요소는 구성 요소 어셈블리에 대 한 서비스를 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-120">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="406e9-121">하나 이상의 응용 프로그램에서 잘 알려진 위치에 있는 구성 파일이 있는 어셈블리를 사용 하는 경우 해당 어셈블리를 사용 하는 응용 프로그램의 구성 파일은 **\<linkedConfiguration>** 구성 정보를 직접 포함 하는 대신 요소를 사용 하 여 어셈블리 구성 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-121">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="406e9-122">구성 요소 어셈블리를 서비스할 때 공통 구성 파일을 업데이트 하면 어셈블리를 사용 하는 모든 응용 프로그램에 업데이트 된 구성 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-122">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="406e9-123">**\<linkedConfiguration>** Windows side-by-side 매니페스트를 사용 하는 응용 프로그램에서는 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="406e9-124">다음 규칙은 연결 된 구성 파일의 사용을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-124">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="406e9-125">포함 된 구성 파일의 설정은 로더 바인딩 정책에만 영향을 주며 로더에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-125">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="406e9-126">포함 된 구성 파일에는 바인딩 정책 이외의 설정이 있을 수 있지만 이러한 설정은 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-126">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="406e9-127">특성에 대해 지원 되는 유일한 형식은 `href` `file://` 입니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-127">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="406e9-128">로컬 파일 및 UNC 파일이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-128">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="406e9-129">구성 파일당 연결 된 구성 수에는 제약 조건이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-129">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="406e9-130">모든 연결 된 구성 파일은 `#include` C/c + +의 지시문 동작과 유사 하 게 하나의 파일을 구성 하기 위해 병합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-130">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="406e9-131">**\<linkedConfiguration>** 요소는 응용 프로그램 구성 파일 에서만 허용 되며 *Machine.config* 에서는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-131">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="406e9-132">순환 참조가 감지 되 고 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-132">Circular references are detected and terminated.</span></span> <span data-ttu-id="406e9-133">즉, **\<linkedConfiguration>** 일련의 구성 파일 요소가 루프를 구성 하면 루프가 검색 되 고 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-133">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="406e9-134">예제</span><span class="sxs-lookup"><span data-stu-id="406e9-134">Example</span></span>

<span data-ttu-id="406e9-135">다음 예제에서는 로컬 하드 디스크의 구성 파일을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="406e9-135">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="406e9-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="406e9-136">See also</span></span>

- [<span data-ttu-id="406e9-137">**\<assemblyBinding>** 요소</span><span class="sxs-lookup"><span data-stu-id="406e9-137">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="406e9-138">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="406e9-138">Configuration file schema for the .NET Framework</span></span>](index.md)
