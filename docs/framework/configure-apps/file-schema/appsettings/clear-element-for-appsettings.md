---
title: <appSettings>에 대한 <clear> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/clear
helpviewer_keywords:
- clear Element
- <clear> Element
ms.assetid: 6d18c7be-27db-438b-8fb5-765d396b0b7b
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: 5d4d96143dbd1db440de2247a7dc2f0c66f20403
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66301290"
---
# <a name="clear-element-for-appsettings"></a><span data-ttu-id="0bd27-102">\<지우기 > 요소에 대 한 \<appSettings ></span><span class="sxs-lookup"><span data-stu-id="0bd27-102">\<clear> element for \<appSettings></span></span>

<span data-ttu-id="0bd27-103">사용자 지정 응용 프로그램 설정을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="0bd27-103">Clears custom application settings.</span></span>

<span data-ttu-id="0bd27-104">[ **\<configuration>** ](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="0bd27-104">[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) </span></span>  
<span data-ttu-id="0bd27-105">&nbsp;&nbsp;[ **\<appSettings>** ](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="0bd27-105">&nbsp;&nbsp;[**\<appSettings>**](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) </span></span>  
<span data-ttu-id="0bd27-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<clear>**</span><span class="sxs-lookup"><span data-stu-id="0bd27-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="0bd27-107">구문</span><span class="sxs-lookup"><span data-stu-id="0bd27-107">Syntax</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="attributes"></a><span data-ttu-id="0bd27-108">특성</span><span class="sxs-lookup"><span data-stu-id="0bd27-108">Attributes</span></span>

<span data-ttu-id="0bd27-109">없음</span><span class="sxs-lookup"><span data-stu-id="0bd27-109">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="0bd27-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0bd27-110">Parent element</span></span>

|     | <span data-ttu-id="0bd27-111">설명</span><span class="sxs-lookup"><span data-stu-id="0bd27-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="0bd27-112"> *\*\<appSettings>** </span><span class="sxs-lookup"><span data-stu-id="0bd27-112">**\<appSettings>**</span></span>](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) | <span data-ttu-id="0bd27-113">파일 경로, XML 웹 서비스 Url 또는 기타 사용자 지정 응용 프로그램 구성 정보와 같은 사용자 지정 응용 프로그램 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="0bd27-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom application configuration information.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="0bd27-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0bd27-114">Child elements</span></span>

<span data-ttu-id="0bd27-115">없음</span><span class="sxs-lookup"><span data-stu-id="0bd27-115">None</span></span>

## <a name="example"></a><span data-ttu-id="0bd27-116">예제</span><span class="sxs-lookup"><span data-stu-id="0bd27-116">Example</span></span>

<span data-ttu-id="0bd27-117">다음 예제에서는 사용자 지정 구성 설정의 선택을 취소 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bd27-117">The following example shows how to clear custom configuration settings:</span></span>

```xml
<appSettings>
  <clear />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="0bd27-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0bd27-118">See also</span></span>

- [<span data-ttu-id="0bd27-119">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="0bd27-119">Configuration file schema for the .NET Framework</span></span>](~/docs/framework/configure-apps/file-schema/index.md)
