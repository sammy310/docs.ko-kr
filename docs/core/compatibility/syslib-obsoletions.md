---
title: .NET 5+에서 사용되지 않는 기능
description: .NET 5.0 이상 버전에서 SYSLIB 컴파일러 경고를 생성하고 사용되지 않는 것으로 표시되는 API에 대해 알아봅니다.
ms.date: 10/20/2020
ms.openlocfilehash: 336958c93e3db8f66cfbec89476a666e5e103b70
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97593307"
---
# <a name="obsolete-features-in-net-5"></a><span data-ttu-id="fc5fa-103">.NET 5+에서 사용되지 않는 기능</span><span class="sxs-lookup"><span data-stu-id="fc5fa-103">Obsolete features in .NET 5</span></span>

<span data-ttu-id="fc5fa-104">.NET 5.0부터 사용되지 않는 것으로 새로 표시되는 일부 API는 <xref:System.ObsoleteAttribute>에서 두 개의 새 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-104">Starting in .NET 5.0, some APIs that are newly marked as obsolete make use of two new properties on <xref:System.ObsoleteAttribute>.</span></span>

- <span data-ttu-id="fc5fa-105"><xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> 속성은 사용자 지정 진단 ID를 사용하여 빌드 경로를 생성하도록 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-105">The <xref:System.ObsoleteAttribute.DiagnosticId?displayProperty=nameWithType> property tells the compiler to generate build warnings using a custom diagnostic ID.</span></span> <span data-ttu-id="fc5fa-106">사용자 지정 ID를 사용하면 사용되지 않음 경고를 별도로 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-106">The custom ID allows for obsoletion warning to be suppressed specifically and separately from one another.</span></span> <span data-ttu-id="fc5fa-107">.NET 5+ 사용되지 않음에서 사용자 지정 진단 ID의 형식은 `SYSLIBxxxx`입니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-107">In the case of the .NET 5+ obsoletions, the format for the custom diagnostic ID is `SYSLIBxxxx`.</span></span>

- <span data-ttu-id="fc5fa-108"><xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> 속성은 사용되지 않음에 대한 자세한 정보를 제공하는 URL 링크를 포함하도록 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-108">The <xref:System.ObsoleteAttribute.UrlFormat?displayProperty=nameWithType> property tells the compiler to include a URL link to learn more about the obsoletion.</span></span>

<span data-ttu-id="fc5fa-109">사용되지 않는 API 사용으로 인해 빌드 경고나 오류가 발생하면 [참조](#reference) 섹션에 나열된 진단 ID에 대해 제공되는 특정 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-109">If you encounter build warnings or errors due to usage of an obsolete API, follow the specific guidance provided for the diagnostic ID listed in the [Reference](#reference) section.</span></span> <span data-ttu-id="fc5fa-110">이러한 사용되지 않음에 대한 경고나 오류는 사용되지 않는 형식이나 멤버에 대한 [표준 진단 ID(CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md)를 사용하여 표시하지 않을 수 ‘없으며’, 사용자 지정 `SYSLIBxxxx` 진단 ID를 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-110">Warnings or errors for these obsoletions *can't* be suppressed using the [standard diagnostic ID (CS0618)](../../csharp/language-reference/compiler-messages/cs0618.md) for obsolete types or members; use the custom `SYSLIBxxxx` diagnostic ID values instead.</span></span> <span data-ttu-id="fc5fa-111">자세한 내용은 [경고 표시 안 함](#suppress-warnings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-111">For more information, see [Suppress warnings](#suppress-warnings).</span></span>

## <a name="reference"></a><span data-ttu-id="fc5fa-112">참조</span><span class="sxs-lookup"><span data-stu-id="fc5fa-112">Reference</span></span>

<span data-ttu-id="fc5fa-113">다음 표에서는 .NET 5+의 `SYSLIBxxxx` 사용되지 않음에 대한 인덱스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-113">The following table provides an index to the `SYSLIBxxxx` obsoletions in .NET 5+.</span></span>

| <span data-ttu-id="fc5fa-114">진단 ID</span><span class="sxs-lookup"><span data-stu-id="fc5fa-114">Diagnostic ID</span></span> | <span data-ttu-id="fc5fa-115">Description</span><span class="sxs-lookup"><span data-stu-id="fc5fa-115">Description</span></span> |
| - | - |
| [<span data-ttu-id="fc5fa-116">SYSLIB0001</span><span class="sxs-lookup"><span data-stu-id="fc5fa-116">SYSLIB0001</span></span>](syslib-warnings/syslib0001.md) | <span data-ttu-id="fc5fa-117">UTF-7 인코딩은 안전하지 않으므로 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-117">The UTF-7 encoding is insecure and should not be used.</span></span> <span data-ttu-id="fc5fa-118">대신 UTF-8을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-118">Consider using UTF-8 instead.</span></span> |
| [<span data-ttu-id="fc5fa-119">SYSLIB0002</span><span class="sxs-lookup"><span data-stu-id="fc5fa-119">SYSLIB0002</span></span>](syslib-warnings/syslib0002.md) | <span data-ttu-id="fc5fa-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute>는 런타임에 적용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-120"><xref:System.Security.Permissions.PrincipalPermissionAttribute> is not honored by the runtime and must not be used.</span></span> |
| [<span data-ttu-id="fc5fa-121">SYSLIB0003</span><span class="sxs-lookup"><span data-stu-id="fc5fa-121">SYSLIB0003</span></span>](syslib-warnings/syslib0003.md) | <span data-ttu-id="fc5fa-122">CAS(코드 액세스 보안)가 런타임에 지원되거나 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-122">Code access security (CAS) is not supported or honored by the runtime.</span></span> |
| [<span data-ttu-id="fc5fa-123">SYSLIB0004</span><span class="sxs-lookup"><span data-stu-id="fc5fa-123">SYSLIB0004</span></span>](syslib-warnings/syslib0004.md) | <span data-ttu-id="fc5fa-124">CER(제약이 있는 실행 영역) 기능이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-124">The constrained execution region (CER) feature is not supported.</span></span> |
| [<span data-ttu-id="fc5fa-125">SYSLIB0005</span><span class="sxs-lookup"><span data-stu-id="fc5fa-125">SYSLIB0005</span></span>](syslib-warnings/syslib0005.md) | <span data-ttu-id="fc5fa-126">GAC(전역 어셈블리 캐시)가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-126">The global assembly cache (GAC) is not supported.</span></span> |
| [<span data-ttu-id="fc5fa-127">SYSLIB0006</span><span class="sxs-lookup"><span data-stu-id="fc5fa-127">SYSLIB0006</span></span>](syslib-warnings/syslib0006.md) | <span data-ttu-id="fc5fa-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType>이 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-128"><xref:System.Threading.Thread.Abort?displayProperty=nameWithType> is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fc5fa-129">SYSLIB0007</span><span class="sxs-lookup"><span data-stu-id="fc5fa-129">SYSLIB0007</span></span>](syslib-warnings/syslib0007.md) | <span data-ttu-id="fc5fa-130">이 암호화 알고리즘의 기본 구현이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-130">The default implementation of this cryptography algorithm is not supported.</span></span> |
| [<span data-ttu-id="fc5fa-131">SYSLIB0008</span><span class="sxs-lookup"><span data-stu-id="fc5fa-131">SYSLIB0008</span></span>](syslib-warnings/syslib0008.md) | <span data-ttu-id="fc5fa-132"><xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-132">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator> API is not supported and throws <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fc5fa-133">SYSLIB0009</span><span class="sxs-lookup"><span data-stu-id="fc5fa-133">SYSLIB0009</span></span>](syslib-warnings/syslib0009.md) | <span data-ttu-id="fc5fa-134"><xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> 및 <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> 메서드가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-134">The <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType> and <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType> methods are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fc5fa-135">SYSLIB0010</span><span class="sxs-lookup"><span data-stu-id="fc5fa-135">SYSLIB0010</span></span>](syslib-warnings/syslib0010.md) | <span data-ttu-id="fc5fa-136">일부 원격 API가 지원되지 않으며 <xref:System.PlatformNotSupportedException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-136">Some remoting APIs are not supported and throw <xref:System.PlatformNotSupportedException>.</span></span> |
| [<span data-ttu-id="fc5fa-137">SYSLIB0011</span><span class="sxs-lookup"><span data-stu-id="fc5fa-137">SYSLIB0011</span></span>](syslib-warnings/syslib0011.md) | <span data-ttu-id="fc5fa-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization이 사용되지 않으며 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-138"><xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialization is obsolete and should not be used.</span></span> |
| [<span data-ttu-id="fc5fa-139">SYSLIB0012</span><span class="sxs-lookup"><span data-stu-id="fc5fa-139">SYSLIB0012</span></span>](syslib-warnings/syslib0012.md) | <span data-ttu-id="fc5fa-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> 및 <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>은 .NET Framework 호환성을 위해서만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-140"><xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType> and <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType> are only included for .NET Framework compatibility.</span></span> <span data-ttu-id="fc5fa-141">대신 <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-141">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span> |

## <a name="suppress-warnings"></a><span data-ttu-id="fc5fa-142">경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="fc5fa-142">Suppress warnings</span></span>

<span data-ttu-id="fc5fa-143">사용되지 않는 API를 사용해야 하고 `SYSLIBxxxx` 진단에서 오류로 표시되는 경우 코드 또는 프로젝트 파일에서 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-143">If you must use the obsolete APIs and the `SYSLIBxxxx` diagnostic does not surface as an error, you can suppress the warning in code or in your project file.</span></span>

<span data-ttu-id="fc5fa-144">코드</span><span class="sxs-lookup"><span data-stu-id="fc5fa-144">In code:</span></span>

```csharp
// Disable the warning.
#pragma warning disable SYSLIB0001
// Code that uses obsolete API.
...
// Re-enable the warning.
#pragma warning restore SYSLIB0001
```

<span data-ttu-id="fc5fa-145">프로젝트 파일:</span><span class="sxs-lookup"><span data-stu-id="fc5fa-145">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
   <TargetFramework>net5.0</TargetFramework>
   <!-- NoWarn below suppresses SYSLIB0001 project-wide -->
   <NoWarn>$(NoWarn);SYSLIB0001</NoWarn>
   <!-- To suppress multiple warnings, you can use multiple NoWarn elements -->
   <NoWarn>$(NoWarn);SYSLIB0002</NoWarn>
   <NoWarn>$(NoWarn);SYSLIB0003</NoWarn>
   <!-- Alternatively, you can suppress multiple warnings by using a semicolon-delimited list -->
   <NoWarn>$(NoWarn);SYSLIB0001;SYSLIB0002;SYSLIB0003</NoWarn>
  </PropertyGroup>
</Project>
```

> [!NOTE]
> <span data-ttu-id="fc5fa-146">이런 식으로 경고를 표시하지 않으면 지정한 사용하지 않음 경고만 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-146">Suppressing warnings in this way only disables the obsoletion warnings you specify.</span></span> <span data-ttu-id="fc5fa-147">진단 ID가 다른 사용하지 않음 경고를 포함하여 다른 모든 경고는 사용하지 않도록 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc5fa-147">It doesn't disable any other warnings, including obsoletion warnings with different diagnostic IDs.</span></span>
