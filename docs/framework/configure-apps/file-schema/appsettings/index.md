---
description: '자세히 알아보기: 앱 설정 스키마'
title: 앱 설정 스키마
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: a98a60b0470e0fa2c03313f25de9b310f5fce785
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699352"
---
# <a name="app-settings-schema"></a><span data-ttu-id="75aed-103">앱 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="75aed-103">App Settings schema</span></span>

<span data-ttu-id="75aed-104">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-104">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="75aed-105">요소</span><span class="sxs-lookup"><span data-stu-id="75aed-105">Element</span></span> | <span data-ttu-id="75aed-106">설명</span><span class="sxs-lookup"><span data-stu-id="75aed-106">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="75aed-107">**\<add>** **\<clear>** **\<remove>** 응용 프로그램 설정을 제어 하는, 및 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-107">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="75aed-108">선택적 **파일** 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-108">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="75aed-109">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-109">Defines a setting.</span></span> <span data-ttu-id="75aed-110">의 자식 **\<appSettings>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-110">Child of **\<appSettings>**.</span></span> <span data-ttu-id="75aed-111">**키** 및 **값** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-111">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="75aed-112">모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-112">Clears all settings.</span></span> <span data-ttu-id="75aed-113">의 자식 **\<appSettings>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-113">Child of **\<appSettings>**.</span></span> <span data-ttu-id="75aed-114">특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-114">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="75aed-115">설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-115">Removes a setting.</span></span> <span data-ttu-id="75aed-116">의 자식 **\<appSettings>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-116">Child of **\<appSettings>**.</span></span> <span data-ttu-id="75aed-117">**키** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-117">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="75aed-118">\<appSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="75aed-118">\<appSettings> element</span></span>

<span data-ttu-id="75aed-119">이 요소 **\<add>** 는 **\<clear>** **\<remove>** 응용 프로그램 설정을 제어 하는, 및 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-119">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="75aed-120">**파일** 에 대한 선택적 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-120">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="75aed-121">\<add> 요소</span><span class="sxs-lookup"><span data-stu-id="75aed-121">\<add> element</span></span>

<span data-ttu-id="75aed-122">애플리케이션 설정 컬렉션에 사용자 지정 애플리케이션 설정을 이름/값 쌍으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-122">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="75aed-123">**키** 및 **값** 에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-123">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="75aed-124">\<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="75aed-124">\<clear> element</span></span>

<span data-ttu-id="75aed-125">상속 된 사용자 지정 응용 프로그램 설정에 대 한 모든 참조를 제거 하 고 **\<add>** 요소 다음에 나오는 요소에 의해 추가 된 참조만 허용 합니다 **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="75aed-125">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="75aed-126">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-126">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="75aed-127">\<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="75aed-127">\<remove> element</span></span>

<span data-ttu-id="75aed-128">상속된 사용자 지정 애플리케이션 설정에 대한 참조를 애플리케이션 설정 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-128">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="75aed-129">**키** 에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-129">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="75aed-130">예제</span><span class="sxs-lookup"><span data-stu-id="75aed-130">Example</span></span>

<span data-ttu-id="75aed-131">다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-131">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="75aed-132">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75aed-132">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="75aed-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75aed-133">See also</span></span>

- [<span data-ttu-id="75aed-134">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="75aed-134">Application Settings Overview</span></span>](/dotnet/desktop/winforms/advanced/application-settings-overview)
- [<span data-ttu-id="75aed-135">애플리케이션 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="75aed-135">Application Settings Architecture</span></span>](/dotnet/desktop/winforms/advanced/application-settings-architecture)
