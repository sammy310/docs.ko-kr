---
title: <appSettings>에 대한 <configuration> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: e1f285aae10a89fa49846534d5b47e15920294ea
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452281"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="770c7-102">\<구성에 대 한 \<appSettings > 요소 ></span><span class="sxs-lookup"><span data-stu-id="770c7-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="770c7-103">사용자 지정 응용 프로그램 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-103">Contains custom application settings.</span></span> <span data-ttu-id="770c7-104">.NET Framework에서 제공 하는 미리 정의 된 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="770c7-105">[ **\<configuration>** ](../configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="770c7-105">[**\<configuration>**](../configuration-element.md) </span></span>  
<span data-ttu-id="770c7-106">&nbsp;&nbsp; **\<appSettings >**</span><span class="sxs-lookup"><span data-stu-id="770c7-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="770c7-107">구문</span><span class="sxs-lookup"><span data-stu-id="770c7-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="770c7-108">attribute</span><span class="sxs-lookup"><span data-stu-id="770c7-108">Attribute</span></span>

|           | <span data-ttu-id="770c7-109">Description</span><span class="sxs-lookup"><span data-stu-id="770c7-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="770c7-110">**file**</span><span class="sxs-lookup"><span data-stu-id="770c7-110">**file**</span></span>  | <span data-ttu-id="770c7-111">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-111">Optional attribute.</span></span><br><br><span data-ttu-id="770c7-112">사용자 지정 응용 프로그램 구성 설정이 포함 된 외부 파일에 대 한 상대 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="770c7-113">지정 된 파일에는 **> 추가\<** 에 지정 된 것과 동일한 종류의 설정이 포함 되어 있습니다. **>\<제거**하 고 **\<요소를 삭제 하 고 해당** 요소와 동일한 키/값 쌍 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="770c7-114">지정 된 경로는 기본 구성 파일을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="770c7-115">Windows Forms 응용 프로그램의 경우이 폴더는 응용 프로그램 구성 파일의 위치가 아니라 */so/debug*와 같은 이진 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="770c7-116">Web Forms 응용 프로그램의 경우 경로는 *web.config* 파일이 있는 응용 프로그램 루트를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="770c7-117">지정 된 파일을 찾을 수 없는 경우 런타임은 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-117">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="770c7-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="770c7-118">Parent element</span></span>

|     | <span data-ttu-id="770c7-119">Description</span><span class="sxs-lookup"><span data-stu-id="770c7-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="770c7-120"> **\<구성 >** 요소인</span><span class="sxs-lookup"><span data-stu-id="770c7-120">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="770c7-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="770c7-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="770c7-122">Child elements</span></span>

|     | <span data-ttu-id="770c7-123">Description</span><span class="sxs-lookup"><span data-stu-id="770c7-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="770c7-124"> **\<add>** </span><span class="sxs-lookup"><span data-stu-id="770c7-124">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="770c7-125">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="770c7-126"> **\<clear>** </span><span class="sxs-lookup"><span data-stu-id="770c7-126">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="770c7-127">이전에 정의 된 모든 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="770c7-128"> **\<remove>** </span><span class="sxs-lookup"><span data-stu-id="770c7-128">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="770c7-129">이전에 정의 된 응용 프로그램 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="770c7-130">설명</span><span class="sxs-lookup"><span data-stu-id="770c7-130">Remarks</span></span>

<span data-ttu-id="770c7-131">**\<appSettings >** 요소는 데이터베이스 연결 문자열, 파일 경로, XML Web services url 또는 응용 프로그램에 대 한 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 구성 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="770c7-132">**\<appSettings >** 요소에 지정 된 키/값 쌍은 <xref:System.Configuration.ConfigurationSettings> 클래스를 사용 하 여 코드에서 액세스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="770c7-133">*Web.config 및 응용* 프로그램 구성 파일의 **\<appSettings >** 요소에서 **file** 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="770c7-134">이 특성은 추가 설정을 제공 하거나 **\<appSettings >** 요소에 지정 된 설정을 재정의 하는 구성 파일을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="770c7-135">사용자가 응용 프로그램 구성 파일에 지정 된 프로젝트 설정을 재정의 하려는 경우와 같이 소스 제어 팀 개발 시나리오에서 **file** 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="770c7-136">**File** 특성에 지정 된 구성 파일에는 **\<구성 >** 아닌 **\<appSettings >** 의 루트 노드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="770c7-137">예제</span><span class="sxs-lookup"><span data-stu-id="770c7-137">Example</span></span>

<span data-ttu-id="770c7-138">다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="770c7-139">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="770c7-140">구성 파일</span><span class="sxs-lookup"><span data-stu-id="770c7-140">Configuration file</span></span>

<span data-ttu-id="770c7-141">이 요소는 응용 프로그램 구성 파일 *, 컴퓨터 구성 파일 (machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *web.config 파일* 에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="770c7-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="770c7-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="770c7-142">See also</span></span>

- [<span data-ttu-id="770c7-143">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="770c7-143">Configuration file schema for the .NET Framework</span></span>](../index.md)
