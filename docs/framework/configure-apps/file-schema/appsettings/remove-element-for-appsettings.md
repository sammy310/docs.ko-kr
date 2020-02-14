---
title: <remove>에 대한 <appSettings> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215485"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="89dd9-102">\<appSettings에 대 한 > 요소 \<제거 ></span><span class="sxs-lookup"><span data-stu-id="89dd9-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="89dd9-103">사용자 지정 응용 프로그램 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dd9-103">Removes custom application settings.</span></span>

<span data-ttu-id="89dd9-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="89dd9-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="89dd9-105">&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="89dd9-105">&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)</span></span>\
<span data-ttu-id="89dd9-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<제거**</span><span class="sxs-lookup"><span data-stu-id="89dd9-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>

## <a name="syntax"></a><span data-ttu-id="89dd9-107">구문</span><span class="sxs-lookup"><span data-stu-id="89dd9-107">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="89dd9-108">attribute</span><span class="sxs-lookup"><span data-stu-id="89dd9-108">Attribute</span></span>

|         | <span data-ttu-id="89dd9-109">Description</span><span class="sxs-lookup"><span data-stu-id="89dd9-109">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="89dd9-110">**key**</span><span class="sxs-lookup"><span data-stu-id="89dd9-110">**key**</span></span> | <span data-ttu-id="89dd9-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="89dd9-111">Required attribute.</span></span><br><br><span data-ttu-id="89dd9-112">제거할 키의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="89dd9-112">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="89dd9-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="89dd9-113">Parent element</span></span>

|     | <span data-ttu-id="89dd9-114">Description</span><span class="sxs-lookup"><span data-stu-id="89dd9-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="89dd9-115"> **\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="89dd9-115">**\<appSettings>**</span></span>](appsettings-element-for-configuration.md) | <span data-ttu-id="89dd9-116">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89dd9-116">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="89dd9-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="89dd9-117">Child elements</span></span>

<span data-ttu-id="89dd9-118">None</span><span class="sxs-lookup"><span data-stu-id="89dd9-118">None</span></span>

## <a name="example"></a><span data-ttu-id="89dd9-119">예제</span><span class="sxs-lookup"><span data-stu-id="89dd9-119">Example</span></span>

<span data-ttu-id="89dd9-120">다음 예제에서는 `ApplicationName`에 대 한 사용자 지정 구성 설정을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89dd9-120">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="89dd9-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="89dd9-121">See also</span></span>

- [<span data-ttu-id="89dd9-122">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="89dd9-122">Configuration file schema for the .NET Framework</span></span>](../index.md)
