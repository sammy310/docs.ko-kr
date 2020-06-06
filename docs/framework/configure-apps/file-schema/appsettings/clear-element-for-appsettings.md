---
title: <appSettings>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77214796"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="e9db6-102">\<appSettings>에 대한 \<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="e9db6-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="e9db6-103">사용자 지정 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e9db6-103">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="e9db6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e9db6-104">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="e9db6-105">특성</span><span class="sxs-lookup"><span data-stu-id="e9db6-105">Attributes</span></span>

<span data-ttu-id="e9db6-106">None</span><span class="sxs-lookup"><span data-stu-id="e9db6-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="e9db6-107">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9db6-107">Parent element</span></span>

|     | <span data-ttu-id="e9db6-108">Description</span><span class="sxs-lookup"><span data-stu-id="e9db6-108">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="e9db6-109">파일 경로, XML Web services Url 또는 기타 사용자 지정 응용 프로그램 구성 정보와 같은 사용자 지정 응용 프로그램 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9db6-109">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="e9db6-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9db6-110">Child elements</span></span>

<span data-ttu-id="e9db6-111">None</span><span class="sxs-lookup"><span data-stu-id="e9db6-111">None</span></span>

## <a name="example"></a><span data-ttu-id="e9db6-112">예제</span><span class="sxs-lookup"><span data-stu-id="e9db6-112">Example</span></span>

<span data-ttu-id="e9db6-113">다음 예제에서는 사용자 지정 구성 설정을 지우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e9db6-113">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="e9db6-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9db6-114">See also</span></span>

- [<span data-ttu-id="e9db6-115">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e9db6-115">Configuration file schema for the .NET Framework</span></span>](../index.md)
