---
title: <configuration>에 대한 <assemblyBinding> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: 21cf5e749b0dae310c3326f8abf82c6678fc97e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155481"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="06c31-102">\<구성> 위한 \<어셈블리 바인딩> 요소</span><span class="sxs-lookup"><span data-stu-id="06c31-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="06c31-103">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="06c31-104">구성 &nbsp; &nbsp;>[\*\* \<\*\*](configuration-element.md) **어셈블리바인딩 \<>**</span><span class="sxs-lookup"><span data-stu-id="06c31-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="06c31-105">구문</span><span class="sxs-lookup"><span data-stu-id="06c31-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="06c31-106">attribute</span><span class="sxs-lookup"><span data-stu-id="06c31-106">Attribute</span></span>

|           | <span data-ttu-id="06c31-107">Description</span><span class="sxs-lookup"><span data-stu-id="06c31-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="06c31-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="06c31-108">**xmlns**</span></span> | <span data-ttu-id="06c31-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-109">Required attribute.</span></span><br><br><span data-ttu-id="06c31-110">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="06c31-111">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="06c31-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="06c31-112">Parent element</span></span>

|     | <span data-ttu-id="06c31-113">Description</span><span class="sxs-lookup"><span data-stu-id="06c31-113">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="06c31-114">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="06c31-114">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="06c31-115">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="06c31-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="06c31-116">Child element</span></span>

|     | <span data-ttu-id="06c31-117">Description</span><span class="sxs-lookup"><span data-stu-id="06c31-117">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="06c31-118">**\<링크된 구성>**</span><span class="sxs-lookup"><span data-stu-id="06c31-118">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="06c31-119">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-119">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="06c31-120">설명</span><span class="sxs-lookup"><span data-stu-id="06c31-120">Remarks</span></span>

<span data-ttu-id="06c31-121">연결된Configuration>요소는 어셈블리 구성 설정을 복제하는 대신 응용 프로그램 구성 파일이 잘 알려진 위치에 어셈블리 구성 파일을 포함하도록 허용하여 구성 요소 어셈블리관리를 단순화합니다. [\*\* \<\*\*](linkedconfiguration-element.md)</span><span class="sxs-lookup"><span data-stu-id="06c31-121">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="06c31-122">\*\* \<링크된Configuration>\*\* 요소는 Windows 나란히 매니페스트가 있는 응용 프로그램에 대해 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-122">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="06c31-123">예제</span><span class="sxs-lookup"><span data-stu-id="06c31-123">Example</span></span>

<span data-ttu-id="06c31-124">다음 예제에서는 로컬 하드 디스크에 구성 파일을 포함하는 방법을 보여 주십습니다.</span><span class="sxs-lookup"><span data-stu-id="06c31-124">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="06c31-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06c31-125">See also</span></span>

- [<span data-ttu-id="06c31-126">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="06c31-126">Configuration file schema for the .NET Framework</span></span>](index.md)
