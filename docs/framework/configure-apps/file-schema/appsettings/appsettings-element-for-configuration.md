---
title: <configuration>에 대한 <appSettings> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: 66260d15768781b7fa3d9397b8e8a7d9ad68ab95
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009796"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="ac6b4-102">\<configuration>에 대한 \<appSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="ac6b4-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="ac6b4-103">사용자 지정 응용 프로그램 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-103">Contains custom application settings.</span></span> <span data-ttu-id="ac6b4-104">.NET Framework에서 제공 하는 미리 정의 된 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;**\<appSettings>**

## <a name="syntax"></a><span data-ttu-id="ac6b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="ac6b4-105">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="ac6b4-106">attribute</span><span class="sxs-lookup"><span data-stu-id="ac6b4-106">Attribute</span></span>

|           | <span data-ttu-id="ac6b4-107">Description</span><span class="sxs-lookup"><span data-stu-id="ac6b4-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="ac6b4-108">**file**</span><span class="sxs-lookup"><span data-stu-id="ac6b4-108">**file**</span></span>  | <span data-ttu-id="ac6b4-109">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-109">Optional attribute.</span></span><br><br><span data-ttu-id="ac6b4-110">사용자 지정 응용 프로그램 구성 설정이 포함 된 외부 파일에 대 한 상대 경로를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-110">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="ac6b4-111">지정 된 파일에는, 및 요소에 지정 된 것과 동일한 종류의 설정이 포함 되어 **\<add>** **\<remove>** **\<clear>** 있으며 해당 요소와 동일한 키/값 쌍 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-111">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="ac6b4-112">지정 된 경로는 기본 구성 파일을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-112">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="ac6b4-113">Windows Forms 응용 프로그램의 경우이 폴더는 응용 프로그램 구성 파일의 위치가 아니라 */so/debug* 와 같은 이진 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-113">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="ac6b4-114">Web Forms 응용 프로그램의 경우 경로는 *web.config* 파일이 있는 응용 프로그램 루트를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-114">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="ac6b4-115">지정 된 파일을 찾을 수 없는 경우 런타임은 특성을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-115">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="ac6b4-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="ac6b4-116">Parent element</span></span>

|     | <span data-ttu-id="ac6b4-117">Description</span><span class="sxs-lookup"><span data-stu-id="ac6b4-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="ac6b4-118">**\<configuration>** 요소</span><span class="sxs-lookup"><span data-stu-id="ac6b4-118">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="ac6b4-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="ac6b4-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="ac6b4-120">Child elements</span></span>

|     | <span data-ttu-id="ac6b4-121">Description</span><span class="sxs-lookup"><span data-stu-id="ac6b4-121">Description</span></span> |
| --- | ----------- |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="ac6b4-122">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-122">Adds a custom application setting.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="ac6b4-123">이전에 정의 된 모든 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-123">Clears all previously defined application settings.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="ac6b4-124">이전에 정의 된 응용 프로그램 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-124">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="ac6b4-125">설명</span><span class="sxs-lookup"><span data-stu-id="ac6b4-125">Remarks</span></span>

<span data-ttu-id="ac6b4-126">**\<appSettings>** 요소는 데이터베이스 연결 문자열, 파일 경로, XML Web Services url 또는 응용 프로그램에 대 한 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 구성 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-126">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="ac6b4-127">요소에 지정 된 키/값 쌍은 **\<appSettings>** 클래스를 사용 하 여 코드에서 액세스 됩니다 <xref:System.Configuration.ConfigurationSettings> .</span><span class="sxs-lookup"><span data-stu-id="ac6b4-127">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="ac6b4-128"> **\<appSettings>** *Web.config* 및 응용 프로그램 구성 파일의 요소에서 file 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-128">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="ac6b4-129">이 특성은 추가 설정을 제공 하거나 요소에 지정 된 설정을 재정의 하는 구성 파일을 지정 합니다 **\<appSettings>** .</span><span class="sxs-lookup"><span data-stu-id="ac6b4-129">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="ac6b4-130">사용자가 응용 프로그램 구성 파일에 지정 된 프로젝트 설정을 재정의 하려는 경우와 같이 소스 제어 팀 개발 시나리오에서 **file** 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-130">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="ac6b4-131">**File** 특성에 의해 지정 된 구성 파일에는가 아닌 루트 노드가 있어야 합니다 **\<appSettings>** **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="ac6b4-131">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="ac6b4-132">예제</span><span class="sxs-lookup"><span data-stu-id="ac6b4-132">Example</span></span>

<span data-ttu-id="ac6b4-133">다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-133">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="ac6b4-134">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-134">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="ac6b4-135">구성 파일</span><span class="sxs-lookup"><span data-stu-id="ac6b4-135">Configuration file</span></span>

<span data-ttu-id="ac6b4-136">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성 파일 (*Machine.config*) 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac6b4-136">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac6b4-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac6b4-137">See also</span></span>

- [<span data-ttu-id="ac6b4-138">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="ac6b4-138">Configuration file schema for the .NET Framework</span></span>](../index.md)
