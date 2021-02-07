---
description: '에 대 한 자세한 정보: <remove> 요소 <appSettings>'
title: <appSettings>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: a67003d310377ee4b896843003306201353dae91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699274"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="bfd38-103">\<appSettings>에 대한 \<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="bfd38-103">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="bfd38-104">사용자 지정 응용 프로그램 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfd38-104">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="bfd38-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfd38-105">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="bfd38-106">attribute</span><span class="sxs-lookup"><span data-stu-id="bfd38-106">Attribute</span></span>

|         | <span data-ttu-id="bfd38-107">Description</span><span class="sxs-lookup"><span data-stu-id="bfd38-107">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="bfd38-108">**key**</span><span class="sxs-lookup"><span data-stu-id="bfd38-108">**key**</span></span> | <span data-ttu-id="bfd38-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="bfd38-109">Required attribute.</span></span><br><br><span data-ttu-id="bfd38-110">제거할 키의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfd38-110">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="bfd38-111">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bfd38-111">Parent element</span></span>

|     | <span data-ttu-id="bfd38-112">설명</span><span class="sxs-lookup"><span data-stu-id="bfd38-112">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="bfd38-113">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfd38-113">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="bfd38-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bfd38-114">Child elements</span></span>

<span data-ttu-id="bfd38-115">없음</span><span class="sxs-lookup"><span data-stu-id="bfd38-115">None</span></span>

## <a name="example"></a><span data-ttu-id="bfd38-116">예제</span><span class="sxs-lookup"><span data-stu-id="bfd38-116">Example</span></span>

<span data-ttu-id="bfd38-117">다음 예제에서는에 대 한 사용자 지정 구성 설정을 제거 하는 방법을 보여 줍니다 `ApplicationName` .</span><span class="sxs-lookup"><span data-stu-id="bfd38-117">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="bfd38-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfd38-118">See also</span></span>

- [<span data-ttu-id="bfd38-119">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="bfd38-119">Configuration file schema for the .NET Framework</span></span>](../index.md)
