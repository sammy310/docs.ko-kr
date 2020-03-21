---
title: <configuration>에 대한 <appSettings> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
ms.openlocfilehash: ea341d562f4b163a3a1771da0f20903b7d64bcdf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155533"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="8fb50-102">\<구성> 대한 \<appSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="8fb50-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="8fb50-103">사용자 지정 응용 프로그램 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-103">Contains custom application settings.</span></span> <span data-ttu-id="8fb50-104">.NET Framework에서 제공하는 미리 정의된 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="8fb50-105">구성 &nbsp; &nbsp;>[\*\* \<\*\*](../configuration-element.md) \*\* \<앱설정>\*\*</span><span class="sxs-lookup"><span data-stu-id="8fb50-105">[**\<configuration>**](../configuration-element.md) &nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="8fb50-106">구문</span><span class="sxs-lookup"><span data-stu-id="8fb50-106">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="8fb50-107">attribute</span><span class="sxs-lookup"><span data-stu-id="8fb50-107">Attribute</span></span>

|           | <span data-ttu-id="8fb50-108">Description</span><span class="sxs-lookup"><span data-stu-id="8fb50-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="8fb50-109">**파일**</span><span class="sxs-lookup"><span data-stu-id="8fb50-109">**file**</span></span>  | <span data-ttu-id="8fb50-110">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-110">Optional attribute.</span></span><br><br><span data-ttu-id="8fb50-111">사용자 지정 응용 프로그램 구성 설정이 포함된 외부 파일에 대한 상대 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-111">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="8fb50-112">지정된 파일에는 \*\* \<추가>, \*\* \*\* \<>제거 **및 \*\* \<>** 요소 지우기 및 해당 요소와 동일한 키/값 쌍 형식에 지정된 동일한 종류의 설정이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-112">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="8fb50-113">지정된 경로는 주 구성 파일을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-113">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="8fb50-114">Windows Forms 응용 프로그램의 경우 응용 프로그램 구성 파일의 위치가 아닌 이진 폴더(예: */bin/디버그)입니다.*</span><span class="sxs-lookup"><span data-stu-id="8fb50-114">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="8fb50-115">Web Forms 응용 프로그램의 경우 경로는 *web.config* 파일이 있는 응용 프로그램 루트를 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-115">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="8fb50-116">지정된 파일을 찾을 수 없는 경우 런타임은 특성을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-116">The runtime ignores the attribute if the specified file can't be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="8fb50-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8fb50-117">Parent element</span></span>

|     | <span data-ttu-id="8fb50-118">Description</span><span class="sxs-lookup"><span data-stu-id="8fb50-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8fb50-119">\*\* \<구성>\*\* 요소</span><span class="sxs-lookup"><span data-stu-id="8fb50-119">**\<configuration>** Element</span></span>](../configuration-element.md) | <span data-ttu-id="8fb50-120">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8fb50-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8fb50-121">Child elements</span></span>

|     | <span data-ttu-id="8fb50-122">Description</span><span class="sxs-lookup"><span data-stu-id="8fb50-122">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="8fb50-123">**\<>추가**</span><span class="sxs-lookup"><span data-stu-id="8fb50-123">**\<add>**</span></span>](add-element-for-appsettings.md) | <span data-ttu-id="8fb50-124">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-124">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="8fb50-125">**\<클리어>**</span><span class="sxs-lookup"><span data-stu-id="8fb50-125">**\<clear>**</span></span>](clear-element-for-appsettings.md) | <span data-ttu-id="8fb50-126">이전에 정의된 모든 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-126">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="8fb50-127">**\<>제거**</span><span class="sxs-lookup"><span data-stu-id="8fb50-127">**\<remove>**</span></span>](remove-element-for-appsettings.md) | <span data-ttu-id="8fb50-128">이전에 정의된 응용 프로그램 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-128">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="8fb50-129">설명</span><span class="sxs-lookup"><span data-stu-id="8fb50-129">Remarks</span></span>

<span data-ttu-id="8fb50-130">appSettings>요소는 데이터베이스 연결 문자열, 파일 경로, XML 웹 서비스 URL 또는 응용 프로그램에 대한 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 구성 정보를 저장합니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="8fb50-130">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="8fb50-131">appSettings>요소에 지정된 키/값 쌍은 <xref:System.Configuration.ConfigurationSettings> 클래스를 사용하는 코드에서 액세스됩니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="8fb50-131">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="8fb50-132">appSettings>*Web.config* 및 응용 프로그램 구성 파일의 요소에서 **파일** 특성을 사용할 수 있습니다. \*\* \<\*\*</span><span class="sxs-lookup"><span data-stu-id="8fb50-132">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="8fb50-133">이 특성은 추가 설정을 제공하거나 \*\* \<appSettings>\*\* 요소에 지정된 설정을 재정의하는 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-133">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="8fb50-134">**파일** 특성은 사용자가 응용 프로그램 구성 파일에 지정된 프로젝트 설정을 재정의하려는 경우와 같은 소스 제어 팀 개발 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-134">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="8fb50-135">**파일** 특성에 의해 지정된 구성 파일에는 \*\* \< \*\* \*\* \<구성\*\*>아니라 appSettings>루트 노드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-135">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="8fb50-136">예제</span><span class="sxs-lookup"><span data-stu-id="8fb50-136">Example</span></span>

<span data-ttu-id="8fb50-137">다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-137">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="8fb50-138">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-138">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="8fb50-139">구성 파일</span><span class="sxs-lookup"><span data-stu-id="8fb50-139">Configuration file</span></span>

<span data-ttu-id="8fb50-140">이 요소는 응용 프로그램 구성 파일, 컴퓨터 구성*파일(Machine.config)* 및 응용 프로그램 디렉터리 수준에 없는 *Web.config* 파일에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8fb50-140">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="8fb50-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8fb50-141">See also</span></span>

- [<span data-ttu-id="8fb50-142">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8fb50-142">Configuration file schema for the .NET Framework</span></span>](../index.md)
