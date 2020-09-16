---
title: <configuration> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: 8f79981a55d0bc9b1cd522e45f5606fda102c72c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544692"
---
# <a name="configuration-element"></a><span data-ttu-id="195c2-102">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="195c2-102">\<configuration> element</span></span>

<span data-ttu-id="195c2-103">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="195c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="195c2-104">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="195c2-105">특성</span><span class="sxs-lookup"><span data-stu-id="195c2-105">Attributes</span></span>

<span data-ttu-id="195c2-106">None</span><span class="sxs-lookup"><span data-stu-id="195c2-106">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="195c2-107">부모 요소</span><span class="sxs-lookup"><span data-stu-id="195c2-107">Parent element</span></span>

<span data-ttu-id="195c2-108">None</span><span class="sxs-lookup"><span data-stu-id="195c2-108">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="195c2-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="195c2-109">Child elements</span></span>

|     | <span data-ttu-id="195c2-110">Description</span><span class="sxs-lookup"><span data-stu-id="195c2-110">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="195c2-111">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-111">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="195c2-112">**\<startup>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-112">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="195c2-113">시작 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-113">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="195c2-114">**\<runtime>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-114">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="195c2-115">런타임 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-115">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="195c2-116">[**\<system.runtime.remoting>** 설정 스키마](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="195c2-116">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="195c2-117">원격 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-117">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="195c2-118">**\<system.Net>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-118">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="195c2-119">네트워크 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-119">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="195c2-120">**\<cryptographySettings>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-120">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="195c2-121">암호화 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-121">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="195c2-122">**\<configuration>** 섹션 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-122">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="195c2-123">구성 섹션 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-123">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="195c2-124">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-124">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="195c2-125">추적 및 디버그 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-125">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="195c2-126">[ASP.NET 구성 설정 스키마](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="195c2-126">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="195c2-127">ASP.NET 웹 사이트 및 응용 프로그램을 구성 하기 위한 요소를 포함 하는 ASP.NET 구성 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-127">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="195c2-128">*Web.config* 파일에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-128">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="195c2-129">[**\<webServices>** 설정 스키마](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="195c2-129">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="195c2-130">웹 서비스 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-130">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="195c2-131">웹 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-131">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="195c2-132">ASP.NET이 IIS와 같은 호스트 애플리케이션과 함께 작동하는 방법을 구성하기 위한 요소를 비롯한 웹 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-132">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="195c2-133">*aspnet.config* 파일에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="195c2-133">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="195c2-134">설명</span><span class="sxs-lookup"><span data-stu-id="195c2-134">Remarks</span></span>

<span data-ttu-id="195c2-135">각 구성 파일에는 정확히 하나의 요소만 포함 되어야 합니다 **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="195c2-135">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="195c2-136">참조</span><span class="sxs-lookup"><span data-stu-id="195c2-136">See also</span></span>

- [<span data-ttu-id="195c2-137">.NET Framework의 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="195c2-137">Configuration file schema for the .NET Framework</span></span>](index.md)
