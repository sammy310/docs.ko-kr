---
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
ms.openlocfilehash: 14ee2275ecf690ab16ffaabd71fbbe7e1a4897bc
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74087957"
---
# <a name="linkedconfiguration-element"></a><span data-ttu-id="de983-102">\<linkedConfiguration > 요소</span><span class="sxs-lookup"><span data-stu-id="de983-102">\<linkedConfiguration> element</span></span>

<span data-ttu-id="de983-103">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de983-103">Specifies a configuration file to include.</span></span>

<span data-ttu-id="de983-104">[ **\<configuration>** ](configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de983-104">[**\<configuration>**](configuration-element.md)</span></span>\
<span data-ttu-id="de983-105">[**assemblyBinding >\<** ](assemblybinding-element-for-configuration.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="de983-105">&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-configuration.md)</span></span>\
<span data-ttu-id="de983-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<linkedConfiguration >**</span><span class="sxs-lookup"><span data-stu-id="de983-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<linkedConfiguration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="de983-107">구문</span><span class="sxs-lookup"><span data-stu-id="de983-107">Syntax</span></span>

```xml
<linkedConfiguration href="URL of linked configuration file" />
```

## <a name="attribute"></a><span data-ttu-id="de983-108">특성</span><span class="sxs-lookup"><span data-stu-id="de983-108">Attribute</span></span>

|           | <span data-ttu-id="de983-109">설명</span><span class="sxs-lookup"><span data-stu-id="de983-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="de983-110">**href**</span><span class="sxs-lookup"><span data-stu-id="de983-110">**href**</span></span>  | <span data-ttu-id="de983-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="de983-111">Required attribute.</span></span><br><br><span data-ttu-id="de983-112">포함할 구성 파일의 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="de983-112">The URL of the configuration file to include.</span></span> <span data-ttu-id="de983-113">**Href** 특성에 대해 지원 되는 유일한 형식은 `file://`입니다.</span><span class="sxs-lookup"><span data-stu-id="de983-113">The only format supported for the **href** attribute is `file://`.</span></span> <span data-ttu-id="de983-114">로컬 파일 및 UNC 파일이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-114">Local files and UNC files are supported.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="de983-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="de983-115">Parent element</span></span>

|     | <span data-ttu-id="de983-116">설명</span><span class="sxs-lookup"><span data-stu-id="de983-116">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="de983-117"> **\<assemblyBinding >** 요소인</span><span class="sxs-lookup"><span data-stu-id="de983-117">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="de983-118">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de983-118">Specifies assembly binding policy at the configuration level.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="de983-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="de983-119">Child elements</span></span>

<span data-ttu-id="de983-120">없음</span><span class="sxs-lookup"><span data-stu-id="de983-120">None</span></span>

## <a name="remarks"></a><span data-ttu-id="de983-121">주의</span><span class="sxs-lookup"><span data-stu-id="de983-121">Remarks</span></span>

<span data-ttu-id="de983-122">**\<linkedConfiguration >** 요소는 구성 요소 어셈블리에 대 한 서비스를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="de983-122">The **\<linkedConfiguration>** element simplifies servicing for component assemblies.</span></span> <span data-ttu-id="de983-123">하나 이상의 응용 프로그램에서 잘 알려진 위치에 있는 구성 파일이 있는 어셈블리를 사용 하는 경우 어셈블리를 사용 하는 응용 프로그램의 구성 파일은 **\<linkedConfiguration >** 요소를 사용 하 여 구성 정보를 직접 포함 하는 대신 어셈블리 구성 파일을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de983-123">If one or more applications use an assembly that has a configuration file residing in a well-known location, the configuration files of the applications that use the assembly can use the **\<linkedConfiguration>** element to include the assembly configuration file, rather than including configuration information directly.</span></span> <span data-ttu-id="de983-124">구성 요소 어셈블리를 서비스할 때 공통 구성 파일을 업데이트 하면 어셈블리를 사용 하는 모든 응용 프로그램에 업데이트 된 구성 정보가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-124">When the component assembly is serviced, updating the common configuration file provides updated configuration information to all applications that use the assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="de983-125">Windows side-by-side 매니페스트를 사용 하는 응용 프로그램에서는 **\<linkedConfiguration >** 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de983-125">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

<span data-ttu-id="de983-126">다음 규칙은 연결 된 구성 파일의 사용을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="de983-126">The following rules govern the use of linked configuration files:</span></span>

- <span data-ttu-id="de983-127">포함 된 구성 파일의 설정은 로더 바인딩 정책에만 영향을 주며 로더에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-127">The settings in included configuration files only affect loader binding policy and are used only by the loader.</span></span> <span data-ttu-id="de983-128">포함 된 구성 파일에는 바인딩 정책 이외의 설정이 있을 수 있지만 이러한 설정은 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de983-128">The included configuration files can have settings other than binding policies, but those settings don't have any effect.</span></span>

- <span data-ttu-id="de983-129">`href` 특성에 대해 지원 되는 유일한 형식은 `file://`입니다.</span><span class="sxs-lookup"><span data-stu-id="de983-129">The only format supported for the `href` attribute is `file://`.</span></span> <span data-ttu-id="de983-130">로컬 파일 및 UNC 파일이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-130">Local files and UNC files are supported.</span></span>

- <span data-ttu-id="de983-131">구성 파일당 연결 된 구성 수에는 제약 조건이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de983-131">There is no constraint on the number of linked configurations per configuration file.</span></span>

- <span data-ttu-id="de983-132">C/C++에서 `#include` 지시문의 동작과 마찬가지로 연결 된 모든 구성 파일이 병합 되어 한 파일을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de983-132">All linked configuration files are merged to form one file, similar to the behavior of the `#include` directive in C/C++.</span></span>

- <span data-ttu-id="de983-133">**\<linkedConfiguration >** 요소는 응용 프로그램 구성 파일 에서만 사용할 수 있습니다. *machine.config에서 무시*됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-133">The **\<linkedConfiguration>** element is allowed only in application configuration files; it's ignored in *Machine.config*.</span></span>

- <span data-ttu-id="de983-134">순환 참조가 감지 되 고 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-134">Circular references are detected and terminated.</span></span> <span data-ttu-id="de983-135">즉, 일련의 구성 파일에 있는 **\<linkedConfiguration >** 요소가 루프를 형성 하면 루프가 검색 되 고 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de983-135">That is, if the **\<linkedConfiguration>** elements of a series of configuration files form a loop, the loop is detected and stopped.</span></span>

## <a name="example"></a><span data-ttu-id="de983-136">예제</span><span class="sxs-lookup"><span data-stu-id="de983-136">Example</span></span>

<span data-ttu-id="de983-137">다음 예제에서는 로컬 하드 디스크의 구성 파일을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de983-137">The following example shows how to include configuration file from the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml"/>
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="de983-138">참조</span><span class="sxs-lookup"><span data-stu-id="de983-138">See also</span></span>

- [<span data-ttu-id="de983-139"> **\<assemblyBinding >** 요소인</span><span class="sxs-lookup"><span data-stu-id="de983-139">**\<assemblyBinding>** Element</span></span>](assemblybinding-element-for-configuration.md)
- [<span data-ttu-id="de983-140">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="de983-140">Configuration file schema for the .NET Framework</span></span>](index.md)
