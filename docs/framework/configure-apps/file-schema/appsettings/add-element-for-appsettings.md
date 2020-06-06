---
title: <appSettings>에 대한 <add> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/add
helpviewer_keywords:
- add Element
- <add> Element
ms.assetid: 8734efdc-00f6-4a65-bba6-084c5bc65246
ms.openlocfilehash: 5c7de79ec626966e71d461dd3865b294a8979db2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214801"
---
# <a name="add-element-for-appsettings"></a><span data-ttu-id="c4cc8-102">\<appSettings>에 대한 \<add> 요소</span><span class="sxs-lookup"><span data-stu-id="c4cc8-102">\<add> element for \<appSettings></span></span>

<span data-ttu-id="c4cc8-103">사용자 지정 응용 프로그램 설정을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-103">Adds a custom application setting.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="c4cc8-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4cc8-104">Syntax</span></span>

```xml
<appSettings>
  <add key="Key of custom setting" value="Value of custom setting" />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="c4cc8-105">특성</span><span class="sxs-lookup"><span data-stu-id="c4cc8-105">Attributes</span></span>

|           | <span data-ttu-id="c4cc8-106">Description</span><span class="sxs-lookup"><span data-stu-id="c4cc8-106">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="c4cc8-107">**key**</span><span class="sxs-lookup"><span data-stu-id="c4cc8-107">**key**</span></span>   | <span data-ttu-id="c4cc8-108">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-108">Required attribute.</span></span><br><br><span data-ttu-id="c4cc8-109">추가할 키의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-109">Specifies the name of the key to add.</span></span> |
| <span data-ttu-id="c4cc8-110">**value**</span><span class="sxs-lookup"><span data-stu-id="c4cc8-110">**value**</span></span> | <span data-ttu-id="c4cc8-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-111">Required attribute.</span></span><br><br><span data-ttu-id="c4cc8-112">추가할 키의 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-112">Specifies the value of the key to add.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="c4cc8-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c4cc8-113">Parent element</span></span>

|     | <span data-ttu-id="c4cc8-114">Description</span><span class="sxs-lookup"><span data-stu-id="c4cc8-114">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="c4cc8-115">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-115">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="c4cc8-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c4cc8-116">Child elements</span></span>

<span data-ttu-id="c4cc8-117">None</span><span class="sxs-lookup"><span data-stu-id="c4cc8-117">None</span></span>

## <a name="example"></a><span data-ttu-id="c4cc8-118">예제</span><span class="sxs-lookup"><span data-stu-id="c4cc8-118">Example</span></span>

<span data-ttu-id="c4cc8-119">다음 예제에서는 응용 프로그램의 이름에 대 한 사용자 지정 구성 설정을 추가 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-119">The following example shows how to add a custom configuration setting for the application's name:</span></span>

```xml
<appSettings>
  <add key="ApplicationName" value="MyApplication" />
</appSettings>
```

<span data-ttu-id="c4cc8-120">다음 예제에서는 요소를 사용 하 여 `<add>` ASP.NET 응용 프로그램에서 두 가지 호환성 설정을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4cc8-120">The following example uses the `<add>` element to define two compatibility settings in an ASP.NET application:</span></span>

```xml
<appSettings>
  <add key="AppContext.SetSwitch:Switch.System.Globalization.NoAsyncCurrentCulture" value="true" />
  <add key="AppContext.SetSwitch:Switch.System.Uri.DontEnableStrictRFC3986ReservedCharacterSets" value="true" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="c4cc8-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4cc8-121">See also</span></span>

- [<span data-ttu-id="c4cc8-122">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c4cc8-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
