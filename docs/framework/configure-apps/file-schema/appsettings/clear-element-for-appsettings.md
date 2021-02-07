---
description: '에 대 한 자세한 정보: <clear> 요소 <appSettings>'
title: <appSettings>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
ms.openlocfilehash: 88c6a02441c038619cb74947c024de7712189915
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699339"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="3f290-103">\<appSettings>에 대한 \<clear> 요소</span><span class="sxs-lookup"><span data-stu-id="3f290-103">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="3f290-104">사용자 지정 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="3f290-104">Clears custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3f290-105">구문</span><span class="sxs-lookup"><span data-stu-id="3f290-105">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="3f290-106">특성</span><span class="sxs-lookup"><span data-stu-id="3f290-106">Attributes</span></span>

<span data-ttu-id="3f290-107">None</span><span class="sxs-lookup"><span data-stu-id="3f290-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="3f290-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3f290-108">Parent element</span></span>

|     | <span data-ttu-id="3f290-109">설명</span><span class="sxs-lookup"><span data-stu-id="3f290-109">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="3f290-110">파일 경로, XML Web services Url 또는 기타 사용자 지정 응용 프로그램 구성 정보와 같은 사용자 지정 응용 프로그램 설정을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f290-110">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="3f290-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3f290-111">Child elements</span></span>

<span data-ttu-id="3f290-112">없음</span><span class="sxs-lookup"><span data-stu-id="3f290-112">None</span></span>

## <a name="example"></a><span data-ttu-id="3f290-113">예제</span><span class="sxs-lookup"><span data-stu-id="3f290-113">Example</span></span>

<span data-ttu-id="3f290-114">다음 예제에서는 사용자 지정 구성 설정을 지우는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f290-114">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="3f290-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f290-115">See also</span></span>

- [<span data-ttu-id="3f290-116">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3f290-116">Configuration file schema for the .NET Framework</span></span>](../index.md)
