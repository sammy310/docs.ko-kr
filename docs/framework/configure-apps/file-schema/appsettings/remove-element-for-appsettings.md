---
title: <appSettings>에 대한 <remove> 요소
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/appSettings/remove
helpviewer_keywords:
- remove Element
- <remove> Element
ms.assetid: 218c4464-e007-4539-803f-7c8b0a909fd8
ms.openlocfilehash: 83abbdbf0d3e4dfd16c0e8c649200c4ecc7329f7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "77215485"
---
# <a name="remove-element-for-appsettings"></a><span data-ttu-id="8f950-102">\<appSettings>에 대한 \<remove> 요소</span><span class="sxs-lookup"><span data-stu-id="8f950-102">\<remove> element for \<appSettings></span></span>

<span data-ttu-id="8f950-103">사용자 지정 응용 프로그램 설정을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-103">Removes custom application settings.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<appSettings>**](appsettings-element-for-configuration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="8f950-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f950-104">Syntax</span></span>

```xml
<appSettings>
  <remove key="Key of custom setting" />
</appSettings>
```

### <a name="attribute"></a><span data-ttu-id="8f950-105">attribute</span><span class="sxs-lookup"><span data-stu-id="8f950-105">Attribute</span></span>

|         | <span data-ttu-id="8f950-106">Description</span><span class="sxs-lookup"><span data-stu-id="8f950-106">Description</span></span> |
| ------- | ----------- |
| <span data-ttu-id="8f950-107">**key**</span><span class="sxs-lookup"><span data-stu-id="8f950-107">**key**</span></span> | <span data-ttu-id="8f950-108">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-108">Required attribute.</span></span><br><br><span data-ttu-id="8f950-109">제거할 키의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-109">Specifies the name of the key to remove.</span></span> |

### <a name="parent-element"></a><span data-ttu-id="8f950-110">부모 요소</span><span class="sxs-lookup"><span data-stu-id="8f950-110">Parent element</span></span>

|     | <span data-ttu-id="8f950-111">Description</span><span class="sxs-lookup"><span data-stu-id="8f950-111">Description</span></span> |
| --- | ----------- |
| [**\<appSettings>**](appsettings-element-for-configuration.md) | <span data-ttu-id="8f950-112">파일 경로, XML Web services URL 또는 애플리케이션의 기타 사용자 지정 구성 정보와 같은 사용자 지정 애플리케이션 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f950-112">Contains custom application settings, such as file paths, XML Web service URLs, or any other custom configuration information for an application.</span></span> |

## <a name="child-elements"></a><span data-ttu-id="8f950-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="8f950-113">Child elements</span></span>

<span data-ttu-id="8f950-114">None</span><span class="sxs-lookup"><span data-stu-id="8f950-114">None</span></span>

## <a name="example"></a><span data-ttu-id="8f950-115">예제</span><span class="sxs-lookup"><span data-stu-id="8f950-115">Example</span></span>

<span data-ttu-id="8f950-116">다음 예제에서는에 대 한 사용자 지정 구성 설정을 제거 하는 방법을 보여 줍니다 `ApplicationName` .</span><span class="sxs-lookup"><span data-stu-id="8f950-116">The following example shows how to remove a custom configuration setting for `ApplicationName`:</span></span>

```xml
<appSettings>
  <remove key="ApplicationName" />
</appSettings>
```

## <a name="see-also"></a><span data-ttu-id="8f950-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f950-117">See also</span></span>

- [<span data-ttu-id="8f950-118">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="8f950-118">Configuration file schema for the .NET Framework</span></span>](../index.md)
