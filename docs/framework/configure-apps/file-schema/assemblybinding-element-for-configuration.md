---
title: <configuration>에 대한 <assemblyBinding> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/assemblyBinding
helpviewer_keywords:
- assemblyBinding Element
- <assemblyBinding> Element
ms.assetid: 6cc55983-b894-449b-8e26-b258e53939cd
ms.openlocfilehash: e0b83c4b3573ab6819654e72cac1bf3e4a0ba637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921269"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="93dc3-102">\<구성 >에 대 한 \<assemblybinding > 요소</span><span class="sxs-lookup"><span data-stu-id="93dc3-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="93dc3-103">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="93dc3-104">[ **\<configuration>** ](configuration-element.md) </span><span class="sxs-lookup"><span data-stu-id="93dc3-104">[**\<configuration>**](configuration-element.md) </span></span>  
<span data-ttu-id="93dc3-105">&nbsp;&nbsp; **\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="93dc3-105">&nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="93dc3-106">구문</span><span class="sxs-lookup"><span data-stu-id="93dc3-106">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="93dc3-107">특성</span><span class="sxs-lookup"><span data-stu-id="93dc3-107">Attribute</span></span>

|           | <span data-ttu-id="93dc3-108">설명</span><span class="sxs-lookup"><span data-stu-id="93dc3-108">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="93dc3-109">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="93dc3-109">**xmlns**</span></span> | <span data-ttu-id="93dc3-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-110">Required attribute.</span></span><br><br><span data-ttu-id="93dc3-111">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-111">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="93dc3-112">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-112">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="93dc3-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="93dc3-113">Parent element</span></span>

|     | <span data-ttu-id="93dc3-114">설명</span><span class="sxs-lookup"><span data-stu-id="93dc3-114">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="93dc3-115"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="93dc3-115">**\<configuration>**</span></span>](configuration-element.md) | <span data-ttu-id="93dc3-116">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="93dc3-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="93dc3-117">Child element</span></span>

|     | <span data-ttu-id="93dc3-118">설명</span><span class="sxs-lookup"><span data-stu-id="93dc3-118">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="93dc3-119"> **\<linkedConfiguration>** </span><span class="sxs-lookup"><span data-stu-id="93dc3-119">**\<linkedConfiguration>**</span></span>](linkedconfiguration-element.md) | <span data-ttu-id="93dc3-120">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-120">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="93dc3-121">설명</span><span class="sxs-lookup"><span data-stu-id="93dc3-121">Remarks</span></span>

<span data-ttu-id="93dc3-122">[ **\<LinkedConfiguration >** ](linkedconfiguration-element.md) 요소는 응용 프로그램 구성 파일에서 어셈블리를 복제 하는 대신 잘 알려진 위치에 어셈블리 구성 파일을 포함 하도록 허용 하 여 구성 요소 어셈블리의 관리를 간소화 합니다. 구성 설정.</span><span class="sxs-lookup"><span data-stu-id="93dc3-122">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="93dc3-123">LinkedConfiguration > 요소는 Windows side-by-side 매니페스트를 사용 하는 응용 프로그램에 대해 지원 되지 않습니다.  **\<**</span><span class="sxs-lookup"><span data-stu-id="93dc3-123">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="93dc3-124">예제</span><span class="sxs-lookup"><span data-stu-id="93dc3-124">Example</span></span>

<span data-ttu-id="93dc3-125">다음 예제에서는 로컬 하드 디스크에 구성 파일을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93dc3-125">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="93dc3-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="93dc3-126">See also</span></span>

- [<span data-ttu-id="93dc3-127">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="93dc3-127">Configuration file schema for the .NET Framework</span></span>](index.md)
