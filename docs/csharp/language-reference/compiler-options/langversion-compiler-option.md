---
description: -langversion(C# 컴파일러 옵션)
title: -langversion(C# 컴파일러 옵션)
ms.date: 05/20/2020
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 987177cc203b4c6202e8c14d8a9f4b41721e836f
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104876"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="c8f0a-103">-langversion(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="c8f0a-103">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="c8f0a-104">컴파일러가 선택한 C# 언어 사양에 포함된 구문만 허용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-104">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="c8f0a-105">구문</span><span class="sxs-lookup"><span data-stu-id="c8f0a-105">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="c8f0a-106">인수</span><span class="sxs-lookup"><span data-stu-id="c8f0a-106">Arguments</span></span>

`option`

<span data-ttu-id="c8f0a-107">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-107">The following values are valid:</span></span>

[!INCLUDE [lang-versions-table](../includes/langversion-table.md)]

<span data-ttu-id="c8f0a-108">기본 언어 버전은 애플리케이션의 대상 프레임워크 및 SDK 또는 Visual Studio의 버전에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-108">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="c8f0a-109">해당 규칙은 [언어 버전 구성](../configure-language-version.md#defaults) 문서에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-109">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8f0a-110">설명</span><span class="sxs-lookup"><span data-stu-id="c8f0a-110">Remarks</span></span>

<span data-ttu-id="c8f0a-111">C# 애플리케이션에서 참조된 메타데이터에는 **-langversion** 컴파일러 옵션이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-111">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="c8f0a-112">각 C# 컴파일러 버전에 언어 사양의 확장이 포함되어 있으므로 **-langversion** 은 이전 컴파일러 버전의 동등한 기능을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-112">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="c8f0a-113">또한 C# 버전 업데이트는 일반적으로 주 .NET Framework 릴리스와 일치하는 반면, 새 구문과 기능이 반드시 특정 프레임워크 버전에 연결되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-113">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="c8f0a-114">새로운 기능에는 C# 버전과 함께 릴리스된 새 컴파일러 업데이트가 분명히 필요하지만, 각 특정 기능에 고유한 최소 .NET API 또는 공용 언어 런타임 요구 사항이 있으므로 NuGet 패키지 또는 다른 라이브러리를 포함하여 하위 수준 프레임워크에서 실행이 허용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-114">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="c8f0a-115">사용하는 **-langversion** 설정과 관계없이 현재 버전의 공용 언어 런타임을 사용하여 고유한 .exe 또는 .dll을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-115">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="c8f0a-116">한 가지 예외는 friend 어셈블리와 [-moduleassemblyname(C# 컴파일러 옵션)](./moduleassemblyname-compiler-option.md)으로, **-langversion:ISO-1** 에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-116">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="c8f0a-117">C# 언어 버전을 지정하는 다른 방법은 [C# 언어 버전 선택](../configure-language-version.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-117">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="c8f0a-118">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-118">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c8f0a-119">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="c8f0a-119">C# language specification</span></span>

| <span data-ttu-id="c8f0a-120">버전</span><span class="sxs-lookup"><span data-stu-id="c8f0a-120">Version</span></span>          | <span data-ttu-id="c8f0a-121">링크</span><span class="sxs-lookup"><span data-stu-id="c8f0a-121">Link</span></span>                       | <span data-ttu-id="c8f0a-122">설명</span><span class="sxs-lookup"><span data-stu-id="c8f0a-122">Description</span></span>                                                             |
|------------------|----------------------------|-------------------------------------------------------------------------|
| <span data-ttu-id="c8f0a-123">C# 7.0 이상</span><span class="sxs-lookup"><span data-stu-id="c8f0a-123">C# 7.0 and later</span></span> |                            | <span data-ttu-id="c8f0a-124">현재 사용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c8f0a-124">Not currently available</span></span>                                                 |
| <span data-ttu-id="c8f0a-125">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-125">C# 6.0</span></span>           | <span data-ttu-id="c8f0a-126">[링크][csharp-6]</span><span class="sxs-lookup"><span data-stu-id="c8f0a-126">[Link][csharp-6]</span></span>           | <span data-ttu-id="c8f0a-127">C# 언어 사양 버전 6 - 비공식 초안: .NET Foundation</span><span class="sxs-lookup"><span data-stu-id="c8f0a-127">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span> |
| <span data-ttu-id="c8f0a-128">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-128">C# 5.0</span></span>           | <span data-ttu-id="c8f0a-129">[PDF 다운로드][csharp-5]</span><span class="sxs-lookup"><span data-stu-id="c8f0a-129">[Download PDF][csharp-5]</span></span>   | <span data-ttu-id="c8f0a-130">표준 ECMA-334 다섯 번째 버전</span><span class="sxs-lookup"><span data-stu-id="c8f0a-130">Standard ECMA-334 5th Edition</span></span>                                           |
| <span data-ttu-id="c8f0a-131">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-131">C# 3.0</span></span>           | <span data-ttu-id="c8f0a-132">[DOC 다운로드][csharp-3]</span><span class="sxs-lookup"><span data-stu-id="c8f0a-132">[Download DOC][csharp-3]</span></span>   | <span data-ttu-id="c8f0a-133">C# 언어 사양 버전 3.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="c8f0a-133">C# Language Specification Version 3.0: Microsoft Corporation</span></span>            |
| <span data-ttu-id="c8f0a-134">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-134">C# 2.0</span></span>           | <span data-ttu-id="c8f0a-135">[PDF 다운로드][csharp-2]</span><span class="sxs-lookup"><span data-stu-id="c8f0a-135">[Download PDF][csharp-2]</span></span>   | <span data-ttu-id="c8f0a-136">표준 ECMA-334 네 번째 버전</span><span class="sxs-lookup"><span data-stu-id="c8f0a-136">Standard ECMA-334 4th Edition</span></span>                                           |
| <span data-ttu-id="c8f0a-137">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="c8f0a-137">C# 1.2</span></span>           | <span data-ttu-id="c8f0a-138">[DOC 다운로드][csharp-1.2]</span><span class="sxs-lookup"><span data-stu-id="c8f0a-138">[Download DOC][csharp-1.2]</span></span> | <span data-ttu-id="c8f0a-139">C# 언어 사양 버전 1.2: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="c8f0a-139">C# Language Specification Version 1.2: Microsoft Corporation</span></span>            |
| <span data-ttu-id="c8f0a-140">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-140">C# 1.0</span></span>           | <span data-ttu-id="c8f0a-141">[DOC 다운로드][csharp-1]</span><span class="sxs-lookup"><span data-stu-id="c8f0a-141">[Download DOC][csharp-1]</span></span>   | <span data-ttu-id="c8f0a-142">C# 언어 사양 버전 1.0: Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="c8f0a-142">C# Language Specification Version 1.0: Microsoft Corporation</span></span>            |

[csharp-6]: /dotnet/csharp/language-reference/language-specification/introduction
[csharp-5]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_5th_edition_december_2017.pdf
[csharp-3]: https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc
[csharp-2]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_4th_edition_june_2006.pdf
[csharp-1.2]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_2nd_edition_december_2002.pdf
[csharp-1]: https://www.ecma-international.org/wp-content/uploads/ECMA-334_1st_edition_december_2001.pdf

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="c8f0a-143">모든 언어 기능을 지원하는 데 필요한 최소 SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c8f0a-143">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="c8f0a-144">다음 표에서는 해당 언어 버전을 지원하는 C# 컴파일러가 포함된 SDK의 최소 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8f0a-144">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

| <span data-ttu-id="c8f0a-145">C# 버전</span><span class="sxs-lookup"><span data-stu-id="c8f0a-145">C# version</span></span> | <span data-ttu-id="c8f0a-146">최소 SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c8f0a-146">Minimum SDK version</span></span>                                                                  |
|------------|--------------------------------------------------------------------------------------|
| <span data-ttu-id="c8f0a-147">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-147">C# 8.0</span></span>     | <span data-ttu-id="c8f0a-148">Microsoft Visual Studio/Build Tools 2019, 버전 16.3 또는 .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="c8f0a-148">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span>         |
| <span data-ttu-id="c8f0a-149">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="c8f0a-149">C# 7.3</span></span>     | <span data-ttu-id="c8f0a-150">Microsoft Visual Studio/Build Tools 2017 버전 15.7</span><span class="sxs-lookup"><span data-stu-id="c8f0a-150">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>                               |
| <span data-ttu-id="c8f0a-151">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="c8f0a-151">C# 7.2</span></span>     | <span data-ttu-id="c8f0a-152">Microsoft Visual Studio/Build Tools 2017 버전 15.5</span><span class="sxs-lookup"><span data-stu-id="c8f0a-152">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>                               |
| <span data-ttu-id="c8f0a-153">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="c8f0a-153">C# 7.1</span></span>     | <span data-ttu-id="c8f0a-154">Microsoft Visual Studio/Build Tools 2017 버전 15.3</span><span class="sxs-lookup"><span data-stu-id="c8f0a-154">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>                               |
| <span data-ttu-id="c8f0a-155">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="c8f0a-155">C# 7.0</span></span>     | <span data-ttu-id="c8f0a-156">Microsoft Visual Studio/Build Tools 2017</span><span class="sxs-lookup"><span data-stu-id="c8f0a-156">Microsoft Visual Studio/Build Tools 2017</span></span>                                             |
| <span data-ttu-id="c8f0a-157">C# 6</span><span class="sxs-lookup"><span data-stu-id="c8f0a-157">C# 6</span></span>       | <span data-ttu-id="c8f0a-158">Microsoft Visual Studio/Build Tools 2015</span><span class="sxs-lookup"><span data-stu-id="c8f0a-158">Microsoft Visual Studio/Build Tools 2015</span></span>                                             |
| <span data-ttu-id="c8f0a-159">C# 5</span><span class="sxs-lookup"><span data-stu-id="c8f0a-159">C# 5</span></span>       | <span data-ttu-id="c8f0a-160">Microsoft Visual Studio/Build Tools 2012 또는 번들 .NET Framework 4.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c8f0a-160">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>      |
| <span data-ttu-id="c8f0a-161">C# 4</span><span class="sxs-lookup"><span data-stu-id="c8f0a-161">C# 4</span></span>       | <span data-ttu-id="c8f0a-162">Microsoft Visual Studio/Build Tools 2010 또는 번들 .NET Framework 4.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c8f0a-162">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>      |
| <span data-ttu-id="c8f0a-163">C# 3</span><span class="sxs-lookup"><span data-stu-id="c8f0a-163">C# 3</span></span>       | <span data-ttu-id="c8f0a-164">Microsoft Visual Studio/Build Tools 2008 또는 번들 .NET Framework 3.5 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c8f0a-164">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>      |
| <span data-ttu-id="c8f0a-165">C# 2</span><span class="sxs-lookup"><span data-stu-id="c8f0a-165">C# 2</span></span>       | <span data-ttu-id="c8f0a-166">Microsoft Visual Studio/Build Tools 2005 또는 번들 .NET Framework 2.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c8f0a-166">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>      |
| <span data-ttu-id="c8f0a-167">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="c8f0a-167">C# 1.0/1.2</span></span> | <span data-ttu-id="c8f0a-168">Microsoft Visual Studio/Build Tools .NET 2002 또는 번들된 .NET Framework 1.0 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c8f0a-168">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="c8f0a-169">참조</span><span class="sxs-lookup"><span data-stu-id="c8f0a-169">See also</span></span>

- [<span data-ttu-id="c8f0a-170">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="c8f0a-170">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="c8f0a-171">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="c8f0a-171">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
