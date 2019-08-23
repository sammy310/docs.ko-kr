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
ms.openlocfilehash: 0e09ec49024b769c516fd97085904781f64b4486
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921240"
---
# <a name="configuration-element"></a><span data-ttu-id="d5022-102">\<configuration > 요소</span><span class="sxs-lookup"><span data-stu-id="d5022-102">\<configuration> element</span></span>

<span data-ttu-id="d5022-103">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-103">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>

<span data-ttu-id="d5022-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="d5022-104">**\<configuration>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d5022-105">구문</span><span class="sxs-lookup"><span data-stu-id="d5022-105">Syntax</span></span>

```xml
<configuration>
  <!-- Configuration settings -->
</configuration>
```

## <a name="attributes"></a><span data-ttu-id="d5022-106">특성</span><span class="sxs-lookup"><span data-stu-id="d5022-106">Attributes</span></span>

<span data-ttu-id="d5022-107">없음</span><span class="sxs-lookup"><span data-stu-id="d5022-107">None</span></span>

## <a name="parent-element"></a><span data-ttu-id="d5022-108">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d5022-108">Parent element</span></span>

<span data-ttu-id="d5022-109">없음</span><span class="sxs-lookup"><span data-stu-id="d5022-109">None</span></span>

## <a name="child-elements"></a><span data-ttu-id="d5022-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d5022-110">Child elements</span></span>

|     | <span data-ttu-id="d5022-111">설명</span><span class="sxs-lookup"><span data-stu-id="d5022-111">Description</span></span> |
| --- | ----------- |
| [<span data-ttu-id="d5022-112"> **\<assemblyBinding>** </span><span class="sxs-lookup"><span data-stu-id="d5022-112">**\<assemblyBinding>**</span></span>](assemblybinding-element-for-configuration.md) | <span data-ttu-id="d5022-113">구성 수준에서 어셈블리 바인딩 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-113">Specifies assembly binding policy at the configuration level.</span></span>|
| [<span data-ttu-id="d5022-114">시작 > 설정 스키마  **\<** </span><span class="sxs-lookup"><span data-stu-id="d5022-114">**\<startup>** Settings Schema</span></span>](./startup/index.md) | <span data-ttu-id="d5022-115">시작 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-115">All elements in the startup settings schema.</span></span> |
| [<span data-ttu-id="d5022-116">런타임 > 설정 스키마  **\<** </span><span class="sxs-lookup"><span data-stu-id="d5022-116">**\<runtime>** Settings Schema</span></span>](./runtime/index.md) | <span data-ttu-id="d5022-117">런타임 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-117">All elements in the runtime settings schema.</span></span> |
| <span data-ttu-id="d5022-118">[ **\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d5022-118">[**\<system.runtime.remoting>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/z415cf9a(v=vs.100))</span></span> | <span data-ttu-id="d5022-119">원격 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-119">All elements in the remoting settings schema.</span></span> |
| [<span data-ttu-id="d5022-120">시스템 .net > 설정 스키마  **\<** </span><span class="sxs-lookup"><span data-stu-id="d5022-120">**\<system.Net>** Settings Schema</span></span>](./network/index.md) | <span data-ttu-id="d5022-121">네트워크 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-121">All elements in the network settings schema.</span></span> |
| [<span data-ttu-id="d5022-122">cryptographysettings > 설정 스키마  **\<** </span><span class="sxs-lookup"><span data-stu-id="d5022-122">**\<cryptographySettings>** Settings Schema</span></span>](./cryptography/index.md) | <span data-ttu-id="d5022-123">암호화 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-123">All elements in the crypto settings schema.</span></span> |
| [<span data-ttu-id="d5022-124">구성 > 섹션 스키마  **\<** </span><span class="sxs-lookup"><span data-stu-id="d5022-124">**\<configuration>** Sections Schema</span></span>](configuration-sections-schema.md) | <span data-ttu-id="d5022-125">구성 섹션 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-125">All elements in the configuration section settings schema.</span></span> |
| [<span data-ttu-id="d5022-126">추적 및 디버그 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d5022-126">Trace and Debug Settings Schema</span></span>](./trace-debug/index.md) | <span data-ttu-id="d5022-127">추적 및 디버그 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-127">All elements in the trace and debug settings schema.</span></span> |
| <span data-ttu-id="d5022-128">[ASP.NET 구성 설정 스키마](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d5022-128">[ASP.NET Configuration Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/b5ysx397(v=vs.100))</span></span> | <span data-ttu-id="d5022-129">ASP.NET 웹 사이트 및 응용 프로그램을 구성 하기 위한 요소를 포함 하는 ASP.NET 구성 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-129">All elements in the ASP.NET configuration schema, which includes elements for configuring ASP.NET Web sites and applications.</span></span> <span data-ttu-id="d5022-130">Web.config 파일 에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-130">Used in *Web.config* files.</span></span> |
| <span data-ttu-id="d5022-131">[ **\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d5022-131">[**\<webServices>** Settings Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cctwteet(v=vs.100))</span></span> | <span data-ttu-id="d5022-132">웹 서비스 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-132">All elements in the Web services settings schema.</span></span> |
| [<span data-ttu-id="d5022-133">웹 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d5022-133">Web Settings Schema</span></span>](./web/index.md) | <span data-ttu-id="d5022-134">ASP.NET이 IIS와 같은 호스트 응용 프로그램과 함께 작동하는 방법을 구성하기 위한 요소를 비롯한 웹 설정 스키마의 모든 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-134">All elements in the Web settings schema, which includes elements for configuring how ASP.NET works with a host application such as IIS.</span></span> <span data-ttu-id="d5022-135">*Aspnet .config* 파일에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-135">Used in *aspnet.config* files.</span></span> |

## <a name="remarks"></a><span data-ttu-id="d5022-136">설명</span><span class="sxs-lookup"><span data-stu-id="d5022-136">Remarks</span></span>

<span data-ttu-id="d5022-137">각 구성 파일에는 정확히 하나의  **\<구성 >** 요소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5022-137">Each configuration file must contain exactly one **\<configuration>** element.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5022-138">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5022-138">See also</span></span>

- [<span data-ttu-id="d5022-139">.NET Framework에 대 한 구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d5022-139">Configuration file schema for the .NET Framework</span></span>](index.md)
