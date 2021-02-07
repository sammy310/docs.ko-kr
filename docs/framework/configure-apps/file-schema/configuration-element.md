---
description: '다음에 대 한 자세한 정보: <configuration> 요소'
title: <configuration> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration
helpviewer_keywords:
- <configuration> element
- configuration element
- container tags, <configuration> element
ms.assetid: 2ec1c9dc-2e5c-4ef0-9958-81670ab88449
ms.openlocfilehash: ee48a45ddb987201e84213a0d7674da004951ab1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699000"
---
# <a name="configuration-element"></a><span data-ttu-id="17def-103">\<configuration> 요소</span><span class="sxs-lookup"><span data-stu-id="17def-103">\<configuration> element</span></span>

<span data-ttu-id="17def-104">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-104">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

**\<configuration>**

## <a name="syntax"></a><span data-ttu-id="17def-105">구문</span><span class="sxs-lookup"><span data-stu-id="17def-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="17def-106">특성</span><span class="sxs-lookup"><span data-stu-id="17def-106">Attributes</span></span>

<span data-ttu-id="17def-107">None</span><span class="sxs-lookup"><span data-stu-id="17def-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="17def-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="17def-108">Parent element</span></span>

<span data-ttu-id="17def-109">None</span><span class="sxs-lookup"><span data-stu-id="17def-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="17def-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="17def-110">Child elements</span></span>

|     | <span data-ttu-id="17def-111">설명</span><span class="sxs-lookup"><span data-stu-id="17def-111">Description</span></span> |
| --- | ----------- |
| [**\<assemblyBinding>**](assemblybinding-element-for-configuration.md) | <span data-ttu-id="17def-112">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17def-112">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="17def-113">**\<startup>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-113">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="17def-114">시작 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-114">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="17def-115">**\<runtime>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-115">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="17def-116">런타임 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-116">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="17def-117">[**\<system.runtime.remoting>** 설정 스키마](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="17def-117">[**\<system.runtime.remoting>** Settings Schema](/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="17def-118">원격 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-118">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="17def-119">**\<system.Net>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-119">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="17def-120">네트워크 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-120">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="17def-121">**\<cryptographySettings>** 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-121">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="17def-122">암호화 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-122">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="17def-123">**\<configuration>** 섹션 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-123">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="17def-124">구성 섹션 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-124">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="17def-125">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-125">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="17def-126">추적 및 디버그 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-126">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="17def-127">[ASP.NET 구성 설정 스키마](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="17def-127">[ASP.NET Configuration Settings Schema](/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="17def-128">ASP.NET 웹 사이트 및 응용 프로그램을 구성 하기 위한 요소를 포함 하는 ASP.NET 구성 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-128">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="17def-129">*Web.config* 파일에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17def-129">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="17def-130">[**\<webServices>** 설정 스키마](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="17def-130">[**\<webServices>** Settings Schema](/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="17def-131">웹 서비스 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-131">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="17def-132">웹 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-132">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="17def-133">ASP.NET이 IIS와 같은 호스트 애플리케이션과 함께 작동하는 방법을 구성하기 위한 요소를 비롯한 웹 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="17def-133">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="17def-134">*aspnet.config* 파일에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17def-134">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="17def-135">설명</span><span class="sxs-lookup"><span data-stu-id="17def-135">Remarks</span></span>

<span data-ttu-id="17def-136">각 구성 파일에는 정확히 하나의 요소만 포함 되어야 합니다 **\<configuration>** .</span><span class="sxs-lookup"><span data-stu-id="17def-136">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="17def-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17def-137">See also</span></span>

- [<span data-ttu-id="17def-138">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="17def-138">Configuration file schema for the .NET Framework</span></span>](index.md)
