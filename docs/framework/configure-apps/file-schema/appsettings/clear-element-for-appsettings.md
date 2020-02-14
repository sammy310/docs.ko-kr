---
title: <clear>에 대한 <appSettings> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 266d32ccb8b322f0472e0f552f9c0fc877c9a78e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214796"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="1b9ad-102">\<appSettings에 대 한 \<clear > 요소 ></span><span class="sxs-lookup"><span data-stu-id="1b9ad-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="1b9ad-103">사용자 지정 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="1b9ad-103">Clears custom application settings.</span></span>

<span data-ttu-id="1b9ad-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1b9ad-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1b9ad-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="1b9ad-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="1b9ad-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear >**</span><span class="sxs-lookup"><span data-stu-id="1b9ad-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="1b9ad-107">구문</span><span class="sxs-lookup"><span data-stu-id="1b9ad-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="1b9ad-108">특성</span><span class="sxs-lookup"><span data-stu-id="1b9ad-108">Attributes</span></span>

<span data-ttu-id="1b9ad-109">None</span><span class="sxs-lookup"><span data-stu-id="1b9ad-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="1b9ad-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1b9ad-110">Parent element</span></span>

|     | <span data-ttu-id="1b9ad-111">Description</span><span class="sxs-lookup"><span data-stu-id="1b9ad-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="1b9ad-112"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="1b9ad-112">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="1b9ad-113">파일 경로, XML Web services Url 또는 기타 사용자 지정 응용 프로그램 구성 정보와 같은 사용자 지정 응용 프로그램 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b9ad-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="1b9ad-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1b9ad-114">Child elements</span></span>

<span data-ttu-id="1b9ad-115">None</span><span class="sxs-lookup"><span data-stu-id="1b9ad-115">None</span></span>

## <a name="example"></a><span data-ttu-id="1b9ad-116">예제</span><span class="sxs-lookup"><span data-stu-id="1b9ad-116">Example</span></span>

<span data-ttu-id="1b9ad-117">다음 예제에서는 사용자 지정 구성 설정을 지우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1b9ad-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="1b9ad-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b9ad-118">See also</span></span>

- [<span data-ttu-id="1b9ad-119">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="1b9ad-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
