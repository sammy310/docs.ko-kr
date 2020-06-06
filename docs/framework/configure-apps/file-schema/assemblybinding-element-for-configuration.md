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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155481"
---
# <a name="assemblybinding-element-for-configuration"></a><span data-ttu-id="6e85b-102">\<configuration>에 대한 \<assemblyBinding> 요소</span><span class="sxs-lookup"><span data-stu-id="6e85b-102">\<assemblyBinding> element for \<configuration></span></span>

<span data-ttu-id="6e85b-103">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-103">Specifies assembly binding policy at the configuration level.</span></span>

<span data-ttu-id="6e85b-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span><span class="sxs-lookup"><span data-stu-id="6e85b-104">[**\<configuration>**](configuration-element.md) &nbsp;&nbsp;**\<assemblyBinding>**</span></span>

## <a name="syntax"></a><span data-ttu-id="6e85b-105">구문</span><span class="sxs-lookup"><span data-stu-id="6e85b-105">Syntax</span></span>

```xml
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
  <!-- Configuration files to include. -->
</assemblyBinding>
```

## <a name="attribute"></a><span data-ttu-id="6e85b-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6e85b-106">Attribute</span></span>

|           | <span data-ttu-id="6e85b-107">설명</span><span class="sxs-lookup"><span data-stu-id="6e85b-107">Description</span></span> |
| --------- | ----------- |
| <span data-ttu-id="6e85b-108">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="6e85b-108">**xmlns**</span></span> | <span data-ttu-id="6e85b-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-109">Required attribute.</span></span><br><br><span data-ttu-id="6e85b-110">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-110">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="6e85b-111">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-111">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span> |

## <a name="parent-element"></a><span data-ttu-id="6e85b-112">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6e85b-112">Parent element</span></span>

|     | <span data-ttu-id="6e85b-113">Description</span><span class="sxs-lookup"><span data-stu-id="6e85b-113">Description</span></span> |
| --- | ----------- |
| [**\<configuration>**](configuration-element.md) | <span data-ttu-id="6e85b-114">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |

## <a name="child-element"></a><span data-ttu-id="6e85b-115">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6e85b-115">Child element</span></span>

|     | <span data-ttu-id="6e85b-116">Description</span><span class="sxs-lookup"><span data-stu-id="6e85b-116">Description</span></span> |
| --- | ----------- |
| [**\<linkedConfiguration>**](linkedconfiguration-element.md) | <span data-ttu-id="6e85b-117">포함할 구성 파일을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-117">Specifies a configuration file to include.</span></span> |

## <a name="remarks"></a><span data-ttu-id="6e85b-118">설명</span><span class="sxs-lookup"><span data-stu-id="6e85b-118">Remarks</span></span>

<span data-ttu-id="6e85b-119">[**\<linkedConfiguration>**](linkedconfiguration-element.md)요소는 응용 프로그램 구성 파일이 어셈블리 구성 설정을 복제 하는 대신 잘 알려진 위치에 어셈블리 구성 파일을 포함 하도록 허용 하 여 구성 요소 어셈블리의 관리를 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-119">The [**\<linkedConfiguration>**](linkedconfiguration-element.md) element simplifies the management of component assemblies by allowing application configuration files to include assembly configuration files in well-known locations, rather than duplicating assembly configuration settings.</span></span>

> [!NOTE]
> <span data-ttu-id="6e85b-120">**\<linkedConfiguration>** Windows side-by-side 매니페스트를 사용 하는 응용 프로그램에서는 요소가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-120">The **\<linkedConfiguration>** element is not supported for applications with Windows side-by-side manifests.</span></span>

## <a name="example"></a><span data-ttu-id="6e85b-121">예제</span><span class="sxs-lookup"><span data-stu-id="6e85b-121">Example</span></span>

<span data-ttu-id="6e85b-122">다음 예제에서는 로컬 하드 디스크에 구성 파일을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e85b-122">The following example shows how to include a configuration file on the local hard disk:</span></span>

```xml
<configuration>
  <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
    <linkedConfiguration href="file://c:\Program Files\Contoso\sharedConfig.xml" />
  </assemblyBinding>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="6e85b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6e85b-123">See also</span></span>

- [<span data-ttu-id="6e85b-124">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6e85b-124">Configuration file schema for the .NET Framework</span></span>](index.md)
