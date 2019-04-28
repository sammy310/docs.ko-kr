---
title: <configuration>에 대한 <appSettings> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings
helpviewer_keywords:
- appSettings Element
- <appSettings> Element
ms.assetid: 39694cc4-6b84-45a6-9329-385a0d8b48fe
author: guardrex
ms.author: mairaw
ms.openlocfilehash: dcdf8d0f11ae65353da08bba1f8d2fe5ab415c6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705560"
---
# <a name="appsettings-element-for-configuration"></a><span data-ttu-id="030b3-102">\<appSettings > 요소에 대 한 \<구성 ></span><span class="sxs-lookup"><span data-stu-id="030b3-102">\<appSettings> element for \<configuration></span></span>

<span data-ttu-id="030b3-103">사용자 지정 응용 프로그램 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-103">Contains custom application settings.</span></span> <span data-ttu-id="030b3-104">.NET Framework에서 제공 하는 미리 정의 된 구성 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-104">This is a predefined configuration section provided by the .NET Framework.</span></span>

<span data-ttu-id="030b3-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="030b3-105">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="030b3-106">&nbsp;&nbsp;**\<appSettings>**</span><span class="sxs-lookup"><span data-stu-id="030b3-106">&nbsp;&nbsp;**\<appSettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="030b3-107">구문</span><span class="sxs-lookup"><span data-stu-id="030b3-107">Syntax</span></span>

```xml
<appSettings>
  <!-- Elements to add, clear, or remove configuration settings -->
</appSettings>
```

## <a name="attribute"></a><span data-ttu-id="030b3-108">특성</span><span class="sxs-lookup"><span data-stu-id="030b3-108">Attribute</span></span>

|           | <span data-ttu-id="030b3-109">설명</span><span class="sxs-lookup"><span data-stu-id="030b3-109">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="030b3-110">**file**</span><span class="sxs-lookup"><span data-stu-id="030b3-110">**file**</span></span>  | <span data-ttu-id="030b3-111">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-111">Optional attribute.</span></span><br><br><span data-ttu-id="030b3-112">사용자 지정 응용 프로그램 구성 설정이 포함 된 외부 파일에 상대 경로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-112">Specifies a relative path to an external file containing custom application configuration settings.</span></span> <span data-ttu-id="030b3-113">지정한 파일에 지정 된 설정의 동일한 종류에는  **\<추가 >** 를  **\<제거 >**, 및  **\<지우기 >** 요소와 해당 요소와 동일한 키/값 쌍 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-113">The specified file contains the same kind of settings that are specified in the **\<add>**, **\<remove>**, and **\<clear>** elements and uses the same key/value pair format as those elements.</span></span><br><br><span data-ttu-id="030b3-114">지정 된 경로 기본 구성 파일에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-114">The path specified is relative to the main configuration file.</span></span> <span data-ttu-id="030b3-115">Windows Forms 응용 프로그램의 경우 이진 폴더입니다 (같은 */bin/debug*), 응용 프로그램 구성 파일의 위치가 아닌 합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-115">For a Windows Forms application, this is the binary folder (such as */bin/debug*), not the location of the application configuration file.</span></span> <span data-ttu-id="030b3-116">Web Forms 응용 프로그램에 대 한 경로가 응용 프로그램 루트에 상대적인 위치를 *web.config* 파일이.</span><span class="sxs-lookup"><span data-stu-id="030b3-116">For Web Forms applications, the path is relative to the application root, where the *web.config* file is located.</span></span><br><br><span data-ttu-id="030b3-117">에서는 런타임에 지정된 된 파일을 찾을 수 없는 경우 특성을 무시 하는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-117">Note that the runtime ignores the attribute if the specified file can not be found.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="030b3-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="030b3-118">Parent element</span></span>

|     | <span data-ttu-id="030b3-119">설명</span><span class="sxs-lookup"><span data-stu-id="030b3-119">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="030b3-120">**\<구성 >** 요소</span><span class="sxs-lookup"><span data-stu-id="030b3-120">**\<configuration>** Element</span></span>](~/docs/framework/configure-apps/file-schema/configuration-element.md) | <span data-ttu-id="030b3-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="030b3-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="030b3-122">Child elements</span></span>

|     | <span data-ttu-id="030b3-123">설명</span><span class="sxs-lookup"><span data-stu-id="030b3-123">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="030b3-124">**\<add>**</span><span class="sxs-lookup"><span data-stu-id="030b3-124">**\<add>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/add-element-for-appsettings.md) | <span data-ttu-id="030b3-125">사용자 지정 응용 프로그램 설정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-125">Adds a custom application setting.</span></span> |
| [<span data-ttu-id="030b3-126">**\<clear>**</span><span class="sxs-lookup"><span data-stu-id="030b3-126">**\<clear>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/clear-element-for-appsettings.md) | <span data-ttu-id="030b3-127">모든 이전에 정의 된 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-127">Clears all previously defined application settings.</span></span> |
| [<span data-ttu-id="030b3-128">**\<remove>**</span><span class="sxs-lookup"><span data-stu-id="030b3-128">**\<remove>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/remove-element-for-appsettings.md) | <span data-ttu-id="030b3-129">이전에 정의 된 응용 프로그램 설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-129">Removes a previously defined application setting.</span></span> |

## <a name="remarks"></a><span data-ttu-id="030b3-130">설명</span><span class="sxs-lookup"><span data-stu-id="030b3-130">Remarks</span></span>

<span data-ttu-id="030b3-131">합니다  **\<appSettings >** 데이터베이스 연결 문자열, 파일 경로, XML 웹 서비스 Url 또는 기타 사용자 지정 구성 정보와 같은 사용자 지정 응용 프로그램 구성 정보를 저장 하는 요소는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-131">The **\<appSettings>** element stores custom application configuration information, such as database connection strings, file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> <span data-ttu-id="030b3-132">에 지정 된 키/값 쌍을  **\<appSettings >** 사용 하 여 코드에 액세스 하는 요소는 <xref:System.Configuration.ConfigurationSettings> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-132">The key/value pairs specified in the **\<appSettings>** element are accessed in code using the <xref:System.Configuration.ConfigurationSettings> class.</span></span>

<span data-ttu-id="030b3-133">사용할 수는 **파일** 특성을  **\<appSettings >** 요소의 *Web.config* 및 응용 프로그램 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-133">You can use the **file** attribute in the **\<appSettings>** element of the *Web.config* and application configuration files.</span></span> <span data-ttu-id="030b3-134">이 특성에 지정 된 설정을 재정의 또는 추가 설정을 제공 하는 구성 파일을 지정 합니다  **\<appSettings >** 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-134">This attribute specifies a configuration file that provides additional settings or overrides the settings specified in the **\<appSettings>** element.</span></span> <span data-ttu-id="030b3-135">합니다 **파일** 특성은 사용자가 응용 프로그램 구성 파일에 지정 된 프로젝트 설정 재정의 하려고 할 때와 같은 원본 제어 팀 개발 시나리오에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-135">The **file** attribute can be used in source control team development scenarios, such as when a user wants to override the project settings specified in an application configuration file.</span></span>

<span data-ttu-id="030b3-136">지정 된 구성 파일을 **파일** 특성의 루트 노드에 있어야 합니다.  **\<appSettings >** 대신  **\<구성 >**.</span><span class="sxs-lookup"><span data-stu-id="030b3-136">Configuration files specified by the **file** attribute must have a root node of **\<appSettings>** rather than **\<configuration>**.</span></span>

## <a name="example"></a><span data-ttu-id="030b3-137">예제</span><span class="sxs-lookup"><span data-stu-id="030b3-137">Example</span></span>

<span data-ttu-id="030b3-138">다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-138">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="030b3-139">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-139">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="configuration-file"></a><span data-ttu-id="030b3-140">구성 파일</span><span class="sxs-lookup"><span data-stu-id="030b3-140">Configuration file</span></span>

<span data-ttu-id="030b3-141">응용 프로그램 구성 파일을 컴퓨터 구성 파일에서이 요소를 사용할 수 있습니다 (*Machine.config*), 및 *Web.config* 응용 프로그램 디렉터리 수준에서 포함 되지 않은 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="030b3-141">This element can be used in the application configuration file, machine configuration file (*Machine.config*), and *Web.config* files that are not at the application directory level.</span></span>

## <a name="see-also"></a><span data-ttu-id="030b3-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="030b3-142">See also</span></span>

- [<span data-ttu-id="030b3-143">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="030b3-143">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
