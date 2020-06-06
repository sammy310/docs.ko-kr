---
title: 앱 설정 스키마
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
ms.openlocfilehash: 0a3363b35a6fc8bd27753eb034f8a1e95feb5292
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215422"
---
# <a name="app-settings-schema"></a><span data-ttu-id="c800e-102">앱 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c800e-102">App Settings schema</span></span>

<span data-ttu-id="c800e-103">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-103">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<clear>**](clear-element-for-appsettings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<remove>**](remove-element-for-appsettings.md)

| <span data-ttu-id="c800e-104">요소</span><span class="sxs-lookup"><span data-stu-id="c800e-104">Element</span></span> | <span data-ttu-id="c800e-105">Description</span><span class="sxs-lookup"><span data-stu-id="c800e-105">Description</span></span> |
| ------- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="c800e-106">**\<add>** **\<clear>** **\<remove>** 응용 프로그램 설정을 제어 하는, 및 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-106">Contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="c800e-107">선택적 **파일** 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-107">Has an optional **file** attribute.</span></span> |
| [**\<add>**](add-element-for-appsettings.md) | <span data-ttu-id="c800e-108">설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-108">Defines a setting.</span></span> <span data-ttu-id="c800e-109">의 자식 **\<appSettings>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-109">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c800e-110">**키** 및 **값** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-110">Requires **key** and **value** attributes.</span></span> |
| [**\<clear>**](clear-element-for-appsettings.md) | <span data-ttu-id="c800e-111">모든 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-111">Clears all settings.</span></span> <span data-ttu-id="c800e-112">의 자식 **\<appSettings>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-112">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c800e-113">특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-113">Has no attributes.</span></span> |
| [**\<remove>**](remove-element-for-appsettings.md) | <span data-ttu-id="c800e-114">설정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-114">Removes a setting.</span></span> <span data-ttu-id="c800e-115">의 자식 **\<appSettings>** 입니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-115">Child of **\<appSettings>**.</span></span> <span data-ttu-id="c800e-116">**키** 특성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-116">Requires a **key** attribute.</span></span> |

## <a name="appsettings-element"></a><span data-ttu-id="c800e-117">\<appSettings> 요소</span><span class="sxs-lookup"><span data-stu-id="c800e-117">\<appSettings> element</span></span>

<span data-ttu-id="c800e-118">이 요소 **\<add>** 는 **\<clear>** **\<remove>** 응용 프로그램 설정을 제어 하는, 및 태그를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-118">This element contains **\<add>**, **\<clear>**, and **\<remove>** tags to control application settings.</span></span> <span data-ttu-id="c800e-119">**파일**에 대한 선택적 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-119">It defines an optional attribute for **file**.</span></span>

## <a name="add-element"></a><span data-ttu-id="c800e-120">\<add> 요소</span><span class="sxs-lookup"><span data-stu-id="c800e-120">\<add> element</span></span>

<span data-ttu-id="c800e-121">애플리케이션 설정 컬렉션에 사용자 지정 애플리케이션 설정을 이름/값 쌍으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-121">Adds a custom application setting as a name/value pair to the application settings collection.</span></span> <span data-ttu-id="c800e-122">**키** 및 **값**에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-122">It defines attributes for **key** and **value**.</span></span>

## <a name="clear-element"></a><span data-ttu-id="c800e-123">\<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="c800e-123">\<clear> element</span></span>

<span data-ttu-id="c800e-124">상속 된 사용자 지정 응용 프로그램 설정에 대 한 모든 참조를 제거 하 고 **\<add>** 요소 다음에 나오는 요소에 의해 추가 된 참조만 허용 합니다 **\<clear>** .</span><span class="sxs-lookup"><span data-stu-id="c800e-124">Removes all references to inherited custom application settings and allows only the references that are added by **\<add>** elements following the **\<clear>** element.</span></span> <span data-ttu-id="c800e-125">특성 없음을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-125">It defines no attributes.</span></span>

## <a name="remove-element"></a><span data-ttu-id="c800e-126">\<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="c800e-126">\<remove> element</span></span>

<span data-ttu-id="c800e-127">상속된 사용자 지정 애플리케이션 설정에 대한 참조를 애플리케이션 설정 컬렉션에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-127">Removes a reference to an inherited custom application setting from the application settings collection.</span></span> <span data-ttu-id="c800e-128">**키**에 대한 특성을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-128">It defines an attribute for **key**.</span></span>

## <a name="example"></a><span data-ttu-id="c800e-129">예제</span><span class="sxs-lookup"><span data-stu-id="c800e-129">Example</span></span>

<span data-ttu-id="c800e-130">다음 예제에서는 사용자 지정 애플리케이션 설정을 정의하는 외부 애플리케이션 설정 파일(*custom.config*)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-130">The following example shows an external application settings file (*custom.config*) that defines a custom application setting:</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

<span data-ttu-id="c800e-131">다음 예제에서는 외부 설정 파일의 설정을 사용하고 자체의 애플리케이션 설정을 지정하는 애플리케이션 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c800e-131">The following example shows an application configuration file that consumes the setting in the external settings file and sets an application setting of its own:</span></span>

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="c800e-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c800e-132">See also</span></span>

- [<span data-ttu-id="c800e-133">애플리케이션 설정 개요</span><span class="sxs-lookup"><span data-stu-id="c800e-133">Application Settings Overview</span></span>](../../../winforms/advanced/application-settings-overview.md)
- [<span data-ttu-id="c800e-134">애플리케이션 설정 아키텍처</span><span class="sxs-lookup"><span data-stu-id="c800e-134">Application Settings Architecture</span></span>](../../../winforms/advanced/application-settings-architecture.md)
