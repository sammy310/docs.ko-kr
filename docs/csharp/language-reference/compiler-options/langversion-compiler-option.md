---
title: -langversion(C# 컴파일러 옵션)
ms.date: 08/23/2019
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 007b10f6f27233c43caad4c1910e3d1158682950
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920363"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="11152-102">-langversion(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="11152-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="11152-103">컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="11152-104">구문</span><span class="sxs-lookup"><span data-stu-id="11152-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="11152-105">인수</span><span class="sxs-lookup"><span data-stu-id="11152-105">Arguments</span></span>

`option`

<span data-ttu-id="11152-106">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="11152-106">The following values are valid:</span></span>

|<span data-ttu-id="11152-107">옵션</span><span class="sxs-lookup"><span data-stu-id="11152-107">Option</span></span>|<span data-ttu-id="11152-108">의미</span><span class="sxs-lookup"><span data-stu-id="11152-108">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="11152-109">미리 보기</span><span class="sxs-lookup"><span data-stu-id="11152-109">preview</span></span>|<span data-ttu-id="11152-110">컴파일러는 지원할 수 있는 최신 미리 보기 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-110">The compiler accepts all valid language syntax from the latest preview version that it can support.</span></span>|
|<span data-ttu-id="11152-111">latest</span><span class="sxs-lookup"><span data-stu-id="11152-111">latest</span></span>|<span data-ttu-id="11152-112">컴파일러는 지원할 수 있는 최신 버전(부 버전 포함)의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-112">The compiler accepts all valid language syntax from the latest version (including minor releases) that it can support.</span></span>|
|<span data-ttu-id="11152-113">latestMajor</span><span class="sxs-lookup"><span data-stu-id="11152-113">latestMajor</span></span>|<span data-ttu-id="11152-114">컴파일러는 지원할 수 있는 최신 주 버전의 유효한 언어 구문을 모두 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-114">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="11152-115">8.0</span><span class="sxs-lookup"><span data-stu-id="11152-115">8.0</span></span>|<span data-ttu-id="11152-116">컴파일러는 C# 8.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-116">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="11152-117">7.3</span><span class="sxs-lookup"><span data-stu-id="11152-117">7.3</span></span>|<span data-ttu-id="11152-118">컴파일러는 C# 7.3 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-118">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="11152-119">7.2</span><span class="sxs-lookup"><span data-stu-id="11152-119">7.2</span></span>|<span data-ttu-id="11152-120">컴파일러는 C# 7.2 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-120">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="11152-121">7.1</span><span class="sxs-lookup"><span data-stu-id="11152-121">7.1</span></span>|<span data-ttu-id="11152-122">컴파일러는 C# 7.1 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-122">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="11152-123">7</span><span class="sxs-lookup"><span data-stu-id="11152-123">7</span></span>|<span data-ttu-id="11152-124">컴파일러는 C# 7.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-124">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="11152-125">6</span><span class="sxs-lookup"><span data-stu-id="11152-125">6</span></span>|<span data-ttu-id="11152-126">컴파일러는 C# 6.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-126">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="11152-127">5</span><span class="sxs-lookup"><span data-stu-id="11152-127">5</span></span>|<span data-ttu-id="11152-128">컴파일러는 C# 5.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-128">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="11152-129">4</span><span class="sxs-lookup"><span data-stu-id="11152-129">4</span></span>|<span data-ttu-id="11152-130">컴파일러는 C# 4.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-130">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="11152-131">3</span><span class="sxs-lookup"><span data-stu-id="11152-131">3</span></span>|<span data-ttu-id="11152-132">컴파일러는 C# 3.0 이하에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-132">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="11152-133">ISO-2</span><span class="sxs-lookup"><span data-stu-id="11152-133">ISO-2</span></span>|<span data-ttu-id="11152-134">컴파일러는 ISO/IEC 23270:2006 C#(2.0)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-134">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span>|
|<span data-ttu-id="11152-135">ISO-1</span><span class="sxs-lookup"><span data-stu-id="11152-135">ISO-1</span></span>|<span data-ttu-id="11152-136">컴파일러는 ISO/IEC 23270:2003 C#(1.0/1.2)에 포함된 구문만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-136">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span>|

<span data-ttu-id="11152-137">기본 언어 버전은 애플리케이션의 대상 프레임워크 및 SDK 또는 Visual Studio의 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="11152-137">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="11152-138">해당 규칙은 [언어 버전 구성](../configure-language-version.md#defaults) 문서에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11152-138">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="11152-139">설명</span><span class="sxs-lookup"><span data-stu-id="11152-139">Remarks</span></span>

<span data-ttu-id="11152-140">C# 애플리케이션에서 참조된 메타데이터에는 **-langversion** 컴파일러 옵션이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11152-140">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="11152-141">각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **-langversion**은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11152-141">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="11152-142">또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하는 반면, 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11152-142">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="11152-143">새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .NET API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11152-143">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="11152-144">사용하는 **-langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="11152-144">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="11152-145">한 가지 예외는 friend 어셈블리와 [-moduleassemblyname(C# 컴파일러 옵션)](./moduleassemblyname-compiler-option.md)으로, **-langversion:ISO-1**에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="11152-145">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="11152-146">C# 언어 버전을 지정하는 다른 방법은 [C# 언어 버전 선택](../configure-language-version.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="11152-146">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="11152-147">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="11152-147">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="11152-148">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="11152-148">C# language specification</span></span>

|<span data-ttu-id="11152-149">Version</span><span class="sxs-lookup"><span data-stu-id="11152-149">Version</span></span>|<span data-ttu-id="11152-150">링크</span><span class="sxs-lookup"><span data-stu-id="11152-150">Link</span></span>|<span data-ttu-id="11152-151">설명</span><span class="sxs-lookup"><span data-stu-id="11152-151">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="11152-152">C# 7.0 이상</span><span class="sxs-lookup"><span data-stu-id="11152-152">C# 7.0 and later</span></span>||<span data-ttu-id="11152-153">현재 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="11152-153">not currently available</span></span>|
|<span data-ttu-id="11152-154">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="11152-154">C# 6.0</span></span>|[<span data-ttu-id="11152-155">링크</span><span class="sxs-lookup"><span data-stu-id="11152-155">Link</span></span>](/dotnet/csharp/language-reference/language-specification/introduction)|<span data-ttu-id="11152-156">C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="11152-156">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="11152-157">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="11152-157">C# 5.0</span></span>|[<span data-ttu-id="11152-158">PDF 다운로드</span><span class="sxs-lookup"><span data-stu-id="11152-158">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|<span data-ttu-id="11152-159">표준 ECMA-334 다섯 번째 버전</span><span class="sxs-lookup"><span data-stu-id="11152-159">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="11152-160">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="11152-160">C# 3.0</span></span>|[<span data-ttu-id="11152-161">DOC 다운로드</span><span class="sxs-lookup"><span data-stu-id="11152-161">Download DOC</span></span>](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="11152-162">C# 언어 사양 버전 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="11152-162">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="11152-163">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="11152-163">C# 2.0</span></span>|[<span data-ttu-id="11152-164">PDF 다운로드</span><span class="sxs-lookup"><span data-stu-id="11152-164">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="11152-165">표준 ECMA-334 네 번째 버전</span><span class="sxs-lookup"><span data-stu-id="11152-165">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="11152-166">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="11152-166">C# 1.2</span></span>|[<span data-ttu-id="11152-167">DOC 다운로드</span><span class="sxs-lookup"><span data-stu-id="11152-167">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|<span data-ttu-id="11152-168">C# 언어 사양 버전 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="11152-168">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="11152-169">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="11152-169">C# 1.0</span></span>|[<span data-ttu-id="11152-170">DOC 다운로드</span><span class="sxs-lookup"><span data-stu-id="11152-170">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|<span data-ttu-id="11152-171">C# 언어 사양 버전 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="11152-171">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="11152-172">모든 언어 기능을 지원하는 데 필요한 최소 SDK 버전</span><span class="sxs-lookup"><span data-stu-id="11152-172">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="11152-173">다음 표에서는 해당 언어 버전을 지원하는 C# 컴파일러가 포함된 SDK의 최소 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="11152-173">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

|<span data-ttu-id="11152-174">C# 버전</span><span class="sxs-lookup"><span data-stu-id="11152-174">C# version</span></span>|<span data-ttu-id="11152-175">최소 SDK 버전</span><span class="sxs-lookup"><span data-stu-id="11152-175">Minimum SDK version</span></span>|
|----------|-------------------|
|<span data-ttu-id="11152-176">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="11152-176">C# 8.0</span></span>| <span data-ttu-id="11152-177">Microsoft Visual Studio/Build Tools 2019, 버전 16.3 또는 .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="11152-177">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span> |
|<span data-ttu-id="11152-178">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="11152-178">C# 7.3</span></span>| <span data-ttu-id="11152-179">Microsoft Visual Studio/Build Tools 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="11152-179">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span> |
|<span data-ttu-id="11152-180">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="11152-180">C# 7.2</span></span>| <span data-ttu-id="11152-181">Microsoft Visual Studio/Build Tools 2017 버전 15.5</span><span class="sxs-lookup"><span data-stu-id="11152-181">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span> |
|<span data-ttu-id="11152-182">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="11152-182">C# 7.1</span></span>| <span data-ttu-id="11152-183">Microsoft Visual Studio/Build Tools 2017 버전 15.3</span><span class="sxs-lookup"><span data-stu-id="11152-183">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span> |
|<span data-ttu-id="11152-184">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="11152-184">C# 7.0</span></span>| <span data-ttu-id="11152-185">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="11152-185">Microsoft Visual Studio/Build Tools 2017</span></span> |
|<span data-ttu-id="11152-186">C# 6</span><span class="sxs-lookup"><span data-stu-id="11152-186">C# 6</span></span>| <span data-ttu-id="11152-187">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="11152-187">Microsoft Visual Studio/Build Tools 2015</span></span> |
|<span data-ttu-id="11152-188">C# 5</span><span class="sxs-lookup"><span data-stu-id="11152-188">C# 5</span></span>| <span data-ttu-id="11152-189">Microsoft Visual Studio/Build Tools 2012 또는 번들 .NET Framework 4.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="11152-189">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span> |
|<span data-ttu-id="11152-190">C# 4</span><span class="sxs-lookup"><span data-stu-id="11152-190">C# 4</span></span>| <span data-ttu-id="11152-191">Microsoft Visual Studio/Build Tools 2010 또는 번들 .NET Framework 4.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="11152-191">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span> |
|<span data-ttu-id="11152-192">C# 3</span><span class="sxs-lookup"><span data-stu-id="11152-192">C# 3</span></span>| <span data-ttu-id="11152-193">Microsoft Visual Studio/Build Tools 2008 또는 번들 .NET Framework 3.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="11152-193">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span> |
|<span data-ttu-id="11152-194">C# 2</span><span class="sxs-lookup"><span data-stu-id="11152-194">C# 2</span></span>| <span data-ttu-id="11152-195">Microsoft Visual Studio/Build Tools 2005 또는 번들 .NET Framework 2.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="11152-195">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span> |
|<span data-ttu-id="11152-196">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="11152-196">C# 1.0/1.2</span></span> | <span data-ttu-id="11152-197">Microsoft Visual Studio/Build Tools .NET 2002 또는 번들된 .NET Framework 1.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="11152-197">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="11152-198">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11152-198">See also</span></span>

- [<span data-ttu-id="11152-199">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="11152-199">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="11152-200">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="11152-200">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
