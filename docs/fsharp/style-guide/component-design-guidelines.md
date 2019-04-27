---
title: F#구성 요소 디자인 지침
description: 쓰기에 대 한 지침을 알아보려면 F# 다른 호출자가 사용 하기 위한 구성 요소입니다.
ms.date: 05/14/2018
ms.openlocfilehash: c61e4cd9098388b356c71c325d66c760fa866cf0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902163"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="a6306-103">F#구성 요소 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="a6306-103">F# component design guidelines</span></span>

<span data-ttu-id="a6306-104">이 문서에 대 한 구성 요소 디자인 지침의 집합이 F# 기반 프로그래밍을 F# 구성 요소 디자인 지침, Microsoft Research v14, 및 [다른 버전](https://fsharp.org/specs/component-design-guidelines/) 원래 큐 레이트 하 고 유지 관리 하는 F# Software Foundation입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and [another version](https://fsharp.org/specs/component-design-guidelines/) originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="a6306-105">이 문서에 잘 알고 있다면 가정 F# 프로그래밍입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="a6306-106">덕분에 많은 F# 이 가이드의 다양 한 버전에 대 한 유용한 피드백와 작성 글에 대 한 커뮤니티입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="a6306-107">개요</span><span class="sxs-lookup"><span data-stu-id="a6306-107">Overview</span></span>

<span data-ttu-id="a6306-108">이 문서는 관련 된 문제 중 일부를 살펴보고 F# 구성 요소 디자인 및 코딩 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="a6306-109">구성 요소를 다음 중 하나를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="a6306-110">계층에 F# 프로젝트 내에서 외부 소비자에 게 지정 된 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="a6306-111">사용 하기 위한 라이브러리 F# 어셈블리 경계를 넘어 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="a6306-112">어셈블리 경계에 걸쳐 모든.NET 언어에서 사용 하기 위한 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="a6306-113">라이브러리와 같은 패키지 리포지토리를 통해 배포를 위한 [NuGet](https://nuget.org)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="a6306-114">이 문서에 설명 된 방법에 따라 합니다 [good의 다섯 가지 원칙 F# 코드](index.md#five-principles-of-good-f-code), 따라서 기능을 활용 하 고 적절 하 게 프로그래밍 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="a6306-115">방법론을에 관계 없이 구성 요소 및 라이브러리 디자이너 개발자가 가장 쉽게 사용할 수 있는 API를 작성 하려고 할 때 많은 실용적이 고 사용할 수 있는 문제를 향하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="a6306-116">에 대해 인식 하 고 응용 프로그램을 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md) 일관 된 즐겁게 사용할 수 있는 Api 집합을 만들기 위한 유도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="a6306-117">일반 지침</span><span class="sxs-lookup"><span data-stu-id="a6306-117">General guidelines</span></span>

<span data-ttu-id="a6306-118">에 적용 되는 몇 가지 유니버설 지침 F# 라이브러리를 라이브러리에 대 한 대상에 관계 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="a6306-119">.NET 라이브러리 디자인 지침에 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="a6306-120">종류에 관계 없이 F# 코딩 수행 하는에 대 한 실무 지식이 있어야 합니다 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="a6306-121">대부분의 다른 F# 를.NET 프로그래머에 게 이러한 지침을 숙지 되며.NET 코드에 대 한 준수를 예상 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="a6306-122">첫 번째는 유용한 다양 한 디자인 지침에 대 한 참조 지점.NET 라이브러리 디자인 지침을 이름, 클래스 및 인터페이스 디자인, 멤버 디자인 (속성, 메서드, 이벤트 등)에 대 한 일반적인 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="a6306-123">코드에 XML 문서 주석 추가</span><span class="sxs-lookup"><span data-stu-id="a6306-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="a6306-124">공용 Api에 대 한 XML 설명서 라이브러리에 대 한 파일을 이러한 형식 및 멤버 및 사용 설명서 작성을 사용 하 여 때 유용한 Intellisense 및 Quickinfo 사용자가 액세스할 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-124">XML documentation on public APIs ensure that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="a6306-125">참조 된 [XML 문서](../language-reference/xml-documentation.md) xmldoc 주석 내의 추가 태그에 사용할 수 있는 다양 한 xml 태그에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="a6306-126">약식 XML 주석을 사용할 수 있습니다 (`/// comment`), 또는 표준 XML 주석 (`///<summary>comment</summary>`).</span><span class="sxs-lookup"><span data-stu-id="a6306-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="a6306-127">안정적인 라이브러리 및 Api 구성 요소에 대 한 명시적 서명 파일 (.fsi)를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="a6306-128">명시적 서명 파일을 사용 하는 F# 는 전체 공용 제공을 명확히 구분 공개 문서도 라이브러리의 노출 및 내부를 확인 하는 데 도움이 공용 API의 간결한 요약을 제공 하는 라이브러리 구현 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which both helps to ensure that you know the full public surface of your library, as well as provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="a6306-129">서명 파일 공용 API를 구현 및 서명 파일에 대해 적용할 변경 사항을 요구 하 여 변화 하는 마찰을 추가 하는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-129">Note that signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="a6306-130">결과적으로, 서명 파일은 일반적으로 도입 될 API 그 수에 더 이상 크게 변경 해야 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="a6306-131">.NET에서 문자열 사용에 대 한 모범 사례를 따르고 항상</span><span class="sxs-lookup"><span data-stu-id="a6306-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="a6306-132">따릅니다 [.NET에서 문자열 사용에 대 한 모범 사례](../../standard/base-types/best-practices-strings.md) 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="a6306-133">특히, 항상 명시적 *문화적 의도* 변환 및 문자열 비교 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="a6306-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="a6306-134">에 대 한 지침 F#-연결 라이브러리</span><span class="sxs-lookup"><span data-stu-id="a6306-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="a6306-135">이 섹션에서는 공용 개발을 위한 권장 사항 표시 F#-연결 라이브러리입니다. 사용할 수 있는 공용 Api를 노출 하는 라이브러리, 즉 F# 개발자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="a6306-136">다양 한 라이브러리 디자인 권장 사항에 맞게 해당는 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="a6306-137">특정 권장 사항가 없으면.NET 라이브러리 디자인 지침에는 대체 (fallback) 지침.</span><span class="sxs-lookup"><span data-stu-id="a6306-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="a6306-138">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="a6306-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="a6306-139">.NET 명명 및 대/소문자 규칙을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="a6306-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="a6306-140">다음 표에서.NET 이름 지정 및 대/소문자 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="a6306-141">작은 추가 포함 하는 F# 를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="a6306-142">구문</span><span class="sxs-lookup"><span data-stu-id="a6306-142">Construct</span></span> | <span data-ttu-id="a6306-143">사례</span><span class="sxs-lookup"><span data-stu-id="a6306-143">Case</span></span> | <span data-ttu-id="a6306-144">파트</span><span class="sxs-lookup"><span data-stu-id="a6306-144">Part</span></span> | <span data-ttu-id="a6306-145">예제</span><span class="sxs-lookup"><span data-stu-id="a6306-145">Examples</span></span> | <span data-ttu-id="a6306-146">노트</span><span class="sxs-lookup"><span data-stu-id="a6306-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="a6306-147">구체적인 형식</span><span class="sxs-lookup"><span data-stu-id="a6306-147">Concrete types</span></span> | <span data-ttu-id="a6306-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-148">PascalCase</span></span> | <span data-ttu-id="a6306-149">명사 adjective /</span><span class="sxs-lookup"><span data-stu-id="a6306-149">Noun/ adjective</span></span> | <span data-ttu-id="a6306-150">목록, Double, 복잡 한</span><span class="sxs-lookup"><span data-stu-id="a6306-150">List, Double, Complex</span></span> | <span data-ttu-id="a6306-151">구체적인 형식은 구조체, 클래스, 열거형, 대리자, 레코드 및 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="a6306-152">형식 이름은 일반적으로 OCaml에서 소문자 있지만 F# 는 형식에 대 한.NET 명명 체계를 채택 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="a6306-153">DLL</span><span class="sxs-lookup"><span data-stu-id="a6306-153">DLLs</span></span>           | <span data-ttu-id="a6306-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-154">PascalCase</span></span> |                 | <span data-ttu-id="a6306-155">Fabrikam.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a6306-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="a6306-156">공용 구조체 태그</span><span class="sxs-lookup"><span data-stu-id="a6306-156">Union tags</span></span>     | <span data-ttu-id="a6306-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-157">PascalCase</span></span> | <span data-ttu-id="a6306-158">명사</span><span class="sxs-lookup"><span data-stu-id="a6306-158">Noun</span></span> | <span data-ttu-id="a6306-159">일부 추가, 성공</span><span class="sxs-lookup"><span data-stu-id="a6306-159">Some, Add, Success</span></span> | <span data-ttu-id="a6306-160">공용 Api에서 접두사를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a6306-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="a6306-161">필요에 따라 내부와 같은 경우에 접두사를 사용 하 여 `type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="a6306-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="a6306-162">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="a6306-162">Event</span></span>          | <span data-ttu-id="a6306-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-163">PascalCase</span></span> | <span data-ttu-id="a6306-164">동사</span><span class="sxs-lookup"><span data-stu-id="a6306-164">Verb</span></span> | <span data-ttu-id="a6306-165">ValueChanged / ValueChanging</span><span class="sxs-lookup"><span data-stu-id="a6306-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="a6306-166">예외</span><span class="sxs-lookup"><span data-stu-id="a6306-166">Exceptions</span></span>     | <span data-ttu-id="a6306-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-167">PascalCase</span></span> |      | <span data-ttu-id="a6306-168">WebException</span><span class="sxs-lookup"><span data-stu-id="a6306-168">WebException</span></span> | <span data-ttu-id="a6306-169">이름을 "Exception" 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-169">Name should end with “Exception”.</span></span> |
| <span data-ttu-id="a6306-170">필드</span><span class="sxs-lookup"><span data-stu-id="a6306-170">Field</span></span>          | <span data-ttu-id="a6306-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-171">PascalCase</span></span> | <span data-ttu-id="a6306-172">명사</span><span class="sxs-lookup"><span data-stu-id="a6306-172">Noun</span></span> | <span data-ttu-id="a6306-173">CurrentName</span><span class="sxs-lookup"><span data-stu-id="a6306-173">CurrentName</span></span>  | |
| <span data-ttu-id="a6306-174">인터페이스 형식</span><span class="sxs-lookup"><span data-stu-id="a6306-174">Interface types</span></span> |  <span data-ttu-id="a6306-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-175">PascalCase</span></span> | <span data-ttu-id="a6306-176">명사 adjective /</span><span class="sxs-lookup"><span data-stu-id="a6306-176">Noun/ adjective</span></span> | <span data-ttu-id="a6306-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="a6306-177">IDisposable</span></span> | <span data-ttu-id="a6306-178">이름 "I"로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-178">Name should start with “I”.</span></span> |
| <span data-ttu-id="a6306-179">메서드</span><span class="sxs-lookup"><span data-stu-id="a6306-179">Method</span></span> |  <span data-ttu-id="a6306-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-180">PascalCase</span></span> |  <span data-ttu-id="a6306-181">동사</span><span class="sxs-lookup"><span data-stu-id="a6306-181">Verb</span></span> | <span data-ttu-id="a6306-182">ToString</span><span class="sxs-lookup"><span data-stu-id="a6306-182">ToString</span></span> | |
| <span data-ttu-id="a6306-183">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="a6306-183">Namespace</span></span> | <span data-ttu-id="a6306-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-184">PascalCase</span></span> | | <span data-ttu-id="a6306-185">Microsoft.FSharp.Core</span><span class="sxs-lookup"><span data-stu-id="a6306-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="a6306-186">일반적으로 사용 하 여 `<Organization>.<Technology>[.<Subnamespace>]`, 하지만 기술을 조직 으로부터 독립적인 경우 조직은 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="a6306-187">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a6306-187">Parameters</span></span> | <span data-ttu-id="a6306-188">camelCase</span><span class="sxs-lookup"><span data-stu-id="a6306-188">camelCase</span></span> | <span data-ttu-id="a6306-189">명사</span><span class="sxs-lookup"><span data-stu-id="a6306-189">Noun</span></span> |  <span data-ttu-id="a6306-190">typeName, 변환, 범위</span><span class="sxs-lookup"><span data-stu-id="a6306-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="a6306-191">값 (내부) 수</span><span class="sxs-lookup"><span data-stu-id="a6306-191">let values (internal)</span></span> | <span data-ttu-id="a6306-192">camelCase 또는 PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-192">camelCase or PascalCase</span></span> | <span data-ttu-id="a6306-193">명사 / 동사</span><span class="sxs-lookup"><span data-stu-id="a6306-193">Noun/ verb</span></span> |  <span data-ttu-id="a6306-194">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="a6306-194">getValue, myTable</span></span> |
| <span data-ttu-id="a6306-195">값 (외부)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-195">let values (external)</span></span> | <span data-ttu-id="a6306-196">camelCase 또는 PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-196">camelCase or PascalCase</span></span> | <span data-ttu-id="a6306-197">명사/동사</span><span class="sxs-lookup"><span data-stu-id="a6306-197">Noun/verb</span></span>  | <span data-ttu-id="a6306-198">List.map Dates.Today</span><span class="sxs-lookup"><span data-stu-id="a6306-198">List.map, Dates.Today</span></span> | <span data-ttu-id="a6306-199">let 바인딩 값 기존의 함수형 디자인 패턴을 따를 경우 공용 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="a6306-200">그러나 일반적으로 사용 하 여 PascalCase 때 식별자는 다른.NET 언어에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="a6306-201">속성</span><span class="sxs-lookup"><span data-stu-id="a6306-201">Property</span></span>  | <span data-ttu-id="a6306-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="a6306-202">PascalCase</span></span>  | <span data-ttu-id="a6306-203">명사 adjective /</span><span class="sxs-lookup"><span data-stu-id="a6306-203">Noun/ adjective</span></span>  | <span data-ttu-id="a6306-204">IsEndOfFile, BackColor</span><span class="sxs-lookup"><span data-stu-id="a6306-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="a6306-205">부울 속성 일반적으로 사용할 수 있으며 긍정적인 IsEndOfFile, 없습니다 IsNotEndOfFile 같이 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="a6306-206">약어를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-206">Avoid abbreviations</span></span>

<span data-ttu-id="a6306-207">.NET 지침에는 약어를 사용 하지 못하도록 (예를 들어 "사용 `OnButtonClick` 대신 `OnBtnClick`").</span><span class="sxs-lookup"><span data-stu-id="a6306-207">The .NET guidelines discourage the use of abbreviations (for example, “use `OnButtonClick` rather than `OnBtnClick`”).</span></span> <span data-ttu-id="a6306-208">일반적인 약어와 같은 `Async` "비동기"에 대 한 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-208">Common abbreviations, such as `Async` for “Asynchronous”, are tolerated.</span></span> <span data-ttu-id="a6306-209">이 지침은 함수형 프로그래밍;에 대 한 경우에 따라 무시 됩니다. 예를 들어 `List.iter` "반복"에 대 한 약어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for “iterate”.</span></span> <span data-ttu-id="a6306-210">이러한 이유로 보다 심층적 정확해 경향이 약어를 사용 하 여 F#에서F# 프로그래밍, 하지만 공용 구성 요소 디자인에서 일반적으로 계속 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="a6306-211">이름 충돌을 대/소문자를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-211">Avoid casing name collisions</span></span>

<span data-ttu-id="a6306-212">.NET 지침 예를 들어 일부 클라이언트 언어 (예: Visual Basic)는 대/소문자 이름 충돌을 명확 하 게 대/소문자가 단독으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="a6306-213">적합 한 머리글자어 사용</span><span class="sxs-lookup"><span data-stu-id="a6306-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="a6306-214">XML과 같은 머리 글자어 약어 않으며 소문자로 시작된 양식 (Xml)에.NET 라이브러리에서 널리 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="a6306-215">유명한, 잘 알려진 머리글자어 사용 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="a6306-216">PascalCase를 사용 하 여 제네릭 매개 변수 이름에 대 한</span><span class="sxs-lookup"><span data-stu-id="a6306-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="a6306-217">PascalCase를 사용 하 여 제네릭 매개 변수 이름에 대 한 포함 하 여 공용 Api에 대 한 수행 F#-라이브러리를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="a6306-218">특히과 같은 이름을 사용 `T`, `U`, `T1`, `T2` 임의의 제네릭 매개 변수 및 특정 이름을 적합 한 다음에 대 한 F#-연결 라이브러리와 같은 이름을 사용 하 여 `Key`, `Value`, `Arg` (하지만 하지 예를 들어 `TKey`).</span><span class="sxs-lookup"><span data-stu-id="a6306-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="a6306-219">PascalCase 또는 camelCase를 사용 하 여 공용 함수 및 값에 대 한 F# 모듈</span><span class="sxs-lookup"><span data-stu-id="a6306-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="a6306-220">camelCase 사용할 수 있도록 설계는 공용 함수는 정규화 되지 않은 (예를 들어 `invalidArg`), (예를 들어 List.map) "표준 컬렉션 기능"입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the “standard collection functions” (for example, List.map).</span></span> <span data-ttu-id="a6306-221">두이 경우 모두에서 함수 이름을 훨씬 언어에서 키워드 처럼 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="a6306-222">개체, 형식 및 모듈 디자인</span><span class="sxs-lookup"><span data-stu-id="a6306-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="a6306-223">네임 스페이스 또는 모듈을 사용 하 여 형식 및 모듈에 포함</span><span class="sxs-lookup"><span data-stu-id="a6306-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="a6306-224">각 F# 구성 요소에서 파일 네임 스페이스 선언 또는 모듈 선언 중 하나를 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="a6306-225">또는</span><span class="sxs-lookup"><span data-stu-id="a6306-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="a6306-226">모듈 및 네임 스페이스를 사용 하 여 최상위 수준에서 코드를 구성할 수 간의 차이 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="a6306-227">네임 스페이스에는 여러 파일 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="a6306-228">네임 스페이스를 포함할 수 없습니다 F# 는 내부 모듈 내에서 있지 않는 한 함수</span><span class="sxs-lookup"><span data-stu-id="a6306-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="a6306-229">지정 된 모든 모듈에 대 한 코드를 단일 파일에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="a6306-230">최상위 모듈에 포함 될 수 있습니다 F# 함수는 내부 모듈에 대 한 필요 없이</span><span class="sxs-lookup"><span data-stu-id="a6306-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="a6306-231">최상위 네임 스페이스 또는 모듈 간의 선택 코드의 컴파일된 형태에 영향을 줍니다 및 따라서는 뷰에 영향을 기타.NET 언어에서 API 결국 사용 해야 외부 F# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="a6306-232">개체 형식에 내장 된 작업에 대 한 메서드 및 속성 사용</span><span class="sxs-lookup"><span data-stu-id="a6306-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="a6306-233">개체를 사용할 때는 메서드와 해당 유형에 대 한 속성으로 구현 하는 사용할 수 있는 기능을 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="a6306-234">필요한 지정된 된 멤버에 대 한 기능 대량의 반드시 해당 멤버에서 구현 되지 하지만 기능을 사용할 수 있는 부분 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="a6306-235">변경 가능한 상태를 캡슐화 할 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="a6306-236">F#에 수행할 수 있는 상태는 이미 클로저, 시퀀스 식, 비동기 계산 등의 다른 언어 구문으로 캡슐화 되지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="a6306-237">인터페이스를 사용 하 여 그룹화 관련 작업</span><span class="sxs-lookup"><span data-stu-id="a6306-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="a6306-238">인터페이스 형식을 사용 하 여 작업 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="a6306-239">이 함수는 튜플 또는 함수의 레코드 등의 기타 옵션에는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="a6306-240">우선적으로:</span><span class="sxs-lookup"><span data-stu-id="a6306-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="a6306-241">인터페이스는 새로운 함수는 일반적으로 제공을 달성 하기 위해 사용할 수 있는.net에서 최고급 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="a6306-242">또한 이러한 수 수 형식을 인코딩하는 데 존재 레코드 함수 일 수 없습니다. 프로그램에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-which-act-on-collections"></a><span data-ttu-id="a6306-243">컬렉션에 대해 작동 하는 그룹 함수 모듈을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-243">Use a module to group functions which act on collections</span></span>

<span data-ttu-id="a6306-244">컬렉션 형식을 정의 하는 경우와 같은 표준 작업 집합이 제공 고려해 야 `CollectionType.map` 고 `CollectionType.iter`) 새 컬렉션 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="a6306-245">이러한 모듈을 포함 하는 경우 FSharp.Core 있는 함수에 대 한 표준 명명 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="a6306-246">수치 연산 및 DSL 라이브러리에서 특히 일반적이 고 정식 함수에 대 한 모듈 그룹 기능을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="a6306-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="a6306-247">예를 들어 `Microsoft.FSharp.Core.Operators` 최상위 함수의 자동으로 열린된 컬렉션입니다 (같은 `abs` 및 `sin`) FSharp.Core.dll에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="a6306-248">통계 라이브러리 함수를 사용 하 여 모듈에 포함 될 수 있습니다 마찬가지로 `erf` 및 `erfc`, 여기서이 모듈은 자동으로 또는 명시적으로 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="a6306-249">RequireQualifiedAccess를 사용 하 여 고려 하 고 신중 하 게 AutoOpen 특성 적용</span><span class="sxs-lookup"><span data-stu-id="a6306-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="a6306-250">추가 된 `[<RequireQualifiedAccess>]` 모듈을 열 수 있습니다 하 액세스를 정규화 하는 모듈의 요소에 대 한 참조가 필요 명시적 특성을 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="a6306-251">예를 들어를 `Microsoft.FSharp.Collections.List` 모듈에이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="a6306-252">이 함수 및 모듈의 값 이름이 다른 모듈에서 이름이 충돌할 가능성이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="a6306-253">정규화 된 액세스가 필요한 장기적 유지 관리성 및 라이브러리의 진화를 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="a6306-254">추가 된 `[<AutoOpen>]` 특성을 모듈에 포함 된 네임 스페이스가 열릴 때 모듈을 열 수를 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="a6306-255">`[<AutoOpen>]` 어셈블리를 참조할 때 자동으로 열리는 모듈을 표시 하기 위해 어셈블리에도 특성이 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="a6306-256">예를 들어 통계 라이브러리 **MathsHeaven.Statistics** 포함 될 수 있습니다는 `module MathsHeaven.Statistics.Operators` 함수를 포함 하 `erf` 고 `erfc`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="a6306-257">이 모듈을 표시 하는 것이 적합 `[<AutoOpen>]`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="a6306-258">즉, `open MathsHeaven.Statistics` 는 또한이 모듈을 열고 이름을 가져올 `erf` 고 `erfc` 범위로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="a6306-259">또 다른 좋은 사용 `[<AutoOpen>]` 확장 메서드를 포함 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="a6306-260">과 용 `[<AutoOpen>]` 잠재 고객 오염된 네임 스페이스 및 특성을 신중 하 게 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="a6306-261">특정 도메인에 적절히 사용 하는 특정 라이브러리에 대 한 `[<AutoOpen>]` 유용성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="a6306-262">잘 알려진 연산자를 사용 하는 적절 한 클래스에서 연산자 멤버를 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="a6306-263">경우에 따라 클래스 벡터와 같은 수학적 구문을 모델링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="a6306-264">도메인 모델링 되는 잘 알려진 연산자에 있는 경우 유용 내장 함수를 클래스 멤버로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="a6306-265">이 설명서는 이러한 형식에 대 한 일반.NET 설명서에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="a6306-266">그러나 또한에 중요할 수 있습니다 F# 이러한 형식을 함께에서 사용할 수 있도록 코딩 F# 함수와 List.sumBy 같은 멤버 제약 조건과 함께 메서드.</span><span class="sxs-lookup"><span data-stu-id="a6306-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="a6306-267">CompiledName를 사용 하 여 제공 하는 합니다. 다른.NET 언어 소비자 NET 이름</span><span class="sxs-lookup"><span data-stu-id="a6306-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="a6306-268">하나의 스타일 이름을 지정 하려는 경우에 따라 F# 소비자 (소문자로 표시 되도록 정적 멤버와 같은 모듈 기반 함수 처럼)에 있으 나 다른 스타일 이름에 대 한 어셈블리로 컴파일할 때.</span><span class="sxs-lookup"><span data-stu-id="a6306-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="a6306-269">사용할 수는 `[<CompiledName>]` 에 대 한 다른 스타일을 제공 하는 특성 아닌 F# 어셈블리를 사용 하는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="a6306-270">사용 하 여 `[<CompiledName>]`에 대 한.NET 명명 규칙을 사용할 수 있습니다 아닌 F# 어셈블리의 소비자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="a6306-271">이렇게 하면 간단한 API를 제공 하는 경우 멤버 함수에 대 한 메서드 오버 로드 사용</span><span class="sxs-lookup"><span data-stu-id="a6306-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="a6306-272">메서드 오버 로드는 하지만 다른 옵션이 나 인수가 유사한 기능을 수행 해야 할 수 있는 API를 간소화 하기 위한 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="a6306-273">F#, 인수의 형식 보다는 수의 인수 오버 로드에 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="a6306-274">이러한 종류의 디자인 변경 될 수 있으므로 공용 구조체 형식과 레코드의 표현을 숨기기</span><span class="sxs-lookup"><span data-stu-id="a6306-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="a6306-275">구체적인 표현의 개체를 노출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a6306-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="a6306-276">예를 들어 구체적인 표현을 <xref:System.DateTime> 값이.NET 라이브러리 디자인의 외부, 공용 API에서 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="a6306-277">런타임 시 공용 언어 런타임 실행 전체에서 사용 되는 커밋된 구현을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="a6306-278">그러나 컴파일된 코드 자체는 선택 하지 않습니다 구체적인 표현에 대 한 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="a6306-279">확장성에 대 한 구현 상속을 사용 하지 못하도록</span><span class="sxs-lookup"><span data-stu-id="a6306-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="a6306-280">F#를 구현 상속은 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="a6306-281">또한 상속 계층 구조는 종종 복잡 하 고 새 요구 사항을 도착할 때 변경 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="a6306-282">상속 구현에 여전히 존재 F# 호환성 및 것이 문제를 위한 최선의 솔루션 하지만 대안 기법의에서 찾아야 할 드문 경우에 F# 인터페이스와 같은 다형성을 디자인할 때 프로그램 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="a6306-283">함수 및 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="a6306-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="a6306-284">소수의 관련 없는 여러 값을 반환 하는 경우 반환 값에 대 한 튜플을 사용합니다</span><span class="sxs-lookup"><span data-stu-id="a6306-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="a6306-285">반환 형식에 튜플을 사용의 좋은 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="a6306-286">에 대 한 많은 구성 요소가 포함 된 형식을 반환 하거나 구성 요소 식별이 가능한 단일 엔터티를 관련 된 경우 튜플을 대신 명명 된 형식을 사용 하 여 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="a6306-287">사용 하 여 `Async<T>` 비동기 프로그래밍에 대 한 F# API 경계</span><span class="sxs-lookup"><span data-stu-id="a6306-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="a6306-288">라는 해당 동기 작업 인지 `Operation` 반환 하는 `T`, 다음 비동기 작업 이름을 지정 해야 `AsyncOperation` 반환 하는 경우 `Async<T>` 또는 `OperationAsync` 반환 하는 경우 `Task<T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="a6306-289">Begin/End 메서드를 노출 하는 자주 사용 되는.NET 형식을 사용 하는 것이 좋습니다에 대 한 `Async.FromBeginEnd` 제공 하는 외관 확장 메서드를 작성 하는 F# .NET Api에 비동기 프로그래밍 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

```fsharp
type SomeType =
    member this.Compute(x:int): int =
        ...
    member this.AsyncCompute(x:int): Async<int> =
        ...

type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        ...
```

### <a name="exceptions"></a><span data-ttu-id="a6306-290">예외</span><span class="sxs-lookup"><span data-stu-id="a6306-290">Exceptions</span></span>

<span data-ttu-id="a6306-291">참조 [오류 관리](conventions.md#error-management) 에 예외, 결과 및 옵션의 적절 한 사용에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="a6306-292">확장 멤버</span><span class="sxs-lookup"><span data-stu-id="a6306-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="a6306-293">신중 하 게 적용 F# 에서 확장 멤버 F#에서F# 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a6306-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="a6306-294">F#일반적으로 대부분의 해당 모드를 사용 하 여 형식과 연결 된 기본 작업의 클로저에 작업에 대 한 확장 멤버에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="a6306-295">일반적 용도 중 하나를 더 자연 스러운 수 있는 Api를 제공 하는 것 F# 다양 한.NET 형식:</span><span class="sxs-lookup"><span data-stu-id="a6306-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="a6306-296">공용 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="a6306-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="a6306-297">클래스 계층 구조 대신 구별 된 공용 구조체를 사용 하 여 트리 구조의 데이터에 대 한</span><span class="sxs-lookup"><span data-stu-id="a6306-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="a6306-298">트리 구조는 재귀적으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="a6306-299">이 상속을 사용 하 여 불편 하지만 구별 된 공용 구조체를 사용 하 여 세련 된입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="a6306-300">또한 구별 된 공용 구조체를 사용 하 여 트리 형태의 데이터를 나타내는 패턴 일치에서 exhaustiveness에서 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="a6306-301">사용 하 여 `[<RequireQualifiedAccess>]` 공용 구조체 형식의 경우 이름이 충분히 고유 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="a6306-302">이름이 같은 구별 된 공용 구조체 케이스와 같은 다른 작업에 가장 적합 한 이름을 여기서는 도메인의 상황이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="a6306-303">사용할 수 있습니다 `[<RequireQualifiedAccess>]` 를 혼란 스러운 오류 섀도잉 인해 순서에 따라 달라 집니다 방지 하기 위해 경우 대/소문자를 구분 하 `open` 문</span><span class="sxs-lookup"><span data-stu-id="a6306-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="a6306-304">이러한 형식의 디자인 발전 시킬 가능성이 있는 경우 이진 호환 되는 Api에 대 한 구별 된 공용 구조체의 표현을 숨기기</span><span class="sxs-lookup"><span data-stu-id="a6306-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="a6306-305">공용 구조체 형식은 F# 는 간결한 프로그래밍 모델에 대 한 forms 패턴 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="a6306-306">이전에 설명한 대로 이러한 종류의 디자인 변경 될 수 있으므로 경우 구체적인 데이터 표현을 노출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a6306-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="a6306-307">예를 들어 구별 된 공용 구조체의 표시를 숨길 수 있습니다는 private 또는 internal 선언을 사용 하 여 또는 서명 파일을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="a6306-308">구별 된 공용 구조체를 무차별적으로 표시 하는 경우 것 버전 하기가 라이브러리 사용자 코드를 중단 하지 않고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="a6306-309">대신, 형식의 값에 대 한 패턴 일치를 허용 하도록 하나 이상의 활성 패턴을 노출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="a6306-310">활성 패턴을 제공 하는 대체 방법을 제공 F# 고객에 게 노출 방지 하는 동안 일치 하는 패턴으로 F# 공용 구조체 형식을 직접.</span><span class="sxs-lookup"><span data-stu-id="a6306-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="a6306-311">인라인 함수 및 멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="a6306-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="a6306-312">인라인 함수를 사용 하 여 정적으로 확인 된 제네릭 형식 제약 조건이 암시적된 멤버와 일반 숫자 알고리즘을 정의</span><span class="sxs-lookup"><span data-stu-id="a6306-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="a6306-313">산술 멤버 제약 조건 및 F# 비교 제약 조건은 표준에 대 한 F# 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="a6306-314">예를 들어, 다음 코드를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="a6306-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="a6306-315">이 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="a6306-316">수학 라이브러리의 공용 API에 대 한 적합 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="a6306-317">형식 클래스 및 덕 형식 지정을 시뮬레이션 하기 위해 멤버 제약 조건을 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="a6306-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="a6306-318">"덕 형식 지정"를 사용 하 여 시뮬레이션할 수 있습니다 F# 멤버 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-318">It is possible to simulate “duck typing” using F# member constraints.</span></span> <span data-ttu-id="a6306-319">그러나 멤버는 사용 하 여이 아닌 일반 사용 해야 F#에서F# 라이브러리 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="a6306-320">즉, 알 수 없는 또는 비표준 암시적 제약 조건을 기반으로 하는 라이브러리 디자인 고정적인 해지고 하나의 특정 프레임 워크 패턴에 연결 하는 사용자 코드를 발생 시키는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="a6306-321">또한이 방식으로 멤버 제약 조건의 사용량이 매우 긴 컴파일 시간이 발생할 수 있는 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="a6306-322">연산자 정의</span><span class="sxs-lookup"><span data-stu-id="a6306-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="a6306-323">기호화 된 사용자 지정 연산자를 정의 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a6306-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="a6306-324">사용자 지정 연산자 일부 상황에서 필수적인 및 표기 장치가 구현 코드의 큰 본문이 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="a6306-325">라이브러리의 새 사용자에 대 한 명명 된 함수를 사용 하기 쉽게 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="a6306-326">또한 기호화 된 사용자 지정 연산자 문서 하기가 수 및 사용자를 찾을 IDE 및 검색 엔진의 기존 제한으로 인해 연산자에 대 한 도움말을 조회 하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="a6306-327">결과적으로, 명명 된 함수의 멤버와 기능을 게시 하 고 또한 cognitive 비용 있는 것을 확인 하 고 설명서 표기법 상의 이점을 능가 하는 경우에이 기능에 대 한 연산자를 노출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="a6306-328">측정 단위</span><span class="sxs-lookup"><span data-stu-id="a6306-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="a6306-329">신중 하 게 측정 단위를 사용 하 여 추가 형식 안전성에 대 한 F# 코드</span><span class="sxs-lookup"><span data-stu-id="a6306-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="a6306-330">측정 단위에 대 한 입력 추가 정보는 다른.NET 언어에서 볼 때 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="a6306-331">.NET 구성 요소, 도구 및 리플렉션 형식-sans-단위를 볼 수 있도록 주의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="a6306-332">예를 들어 C# 소비자가 표시 됩니다 `float` 대신 `float<kg>`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="a6306-333">형식 약어</span><span class="sxs-lookup"><span data-stu-id="a6306-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="a6306-334">신중 하 게 형식 약어를 사용 하 여 단순화 하기 위해 F# 코드</span><span class="sxs-lookup"><span data-stu-id="a6306-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="a6306-335">.NET 구성 요소, 도구 및 리플렉션 형식에 대 한 약식된 이름이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="a6306-336">형식 약어의 중요 한 사용 현황에 나타날 것 보다 훨씬 더 복잡할 실제로, 소비자가 혼동을 줄 수는 도메인을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="a6306-337">해당 멤버 및 속성 약어로 표시 되는 형식에서 사용할 수 있는 본질적으로 달라 야 하는 공용 형식에 대 한 형식 약어를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="a6306-338">이 경우 약어로 중인 형식을 정의 하 고 실제 형식의 표현에 대해 너무 많이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="a6306-339">대신, 단일 사례 구별된 된 공용 구조체 또는 클래스 형식 약어를 래핑하는 것이 좋습니다 (또는 성능 필수 이면 약어를 래핑할 구조체 형식을 사용 하 여).</span><span class="sxs-lookup"><span data-stu-id="a6306-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="a6306-340">특수 사례로 다중 맵을 정의 하 고 싶어 하는 예를 들어는 F# 지도, 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a6306-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="a6306-341">그러나이 형식에 대해 논리 점 표기법 작업이 맵에서 연산과 동일 하 게 하지 않습니다 – 예를 들어 하다는 lookup 연산자 매핑. [키] 반환 키 예외가 발생 하는 것이 아니라 사전에 없는 경우 빈 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="a6306-342">다른.NET 언어에서 사용 하기 위해 라이브러리에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="a6306-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="a6306-343">다른.NET 언어에서 사용 하기 위한 라이브러리를 디자인할 때을 준수 하는 것이 중요 합니다 [.NET 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="a6306-344">이 문서에서는 이러한 라이브러리는로 레이블이 지정 바닐라.NET 라이브러리와는 반대로 F#-연결 라이브러리를 사용 하는 F# 제한 없이 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="a6306-345">.NET Framework의 나머지 부분과 일치 친숙 하 고 자연 스러운 Api 사용을 최소화 하 여 제공 의미 바닐라.NET 라이브러리 디자인 F#-공용 API의 특정 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="a6306-346">규칙은 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="a6306-347">Namespace 및 형식 디자인 (다른.NET 언어에서 사용 하기 위한 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="a6306-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="a6306-348">구성 요소의 공용 API를.NET 명명 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="a6306-349">약식된 이름이.NET 글자를 대문자로 표시 지침을 사용 하 여 특별 한 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="a6306-350">구성 요소에 대 한 기본 조직 구조와 네임 스페이스, 형식 및 멤버를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="a6306-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="a6306-351">로 시작 해야 공용 기능을 포함 하는 모든 파일을 `namespace` 선언 및 네임 스페이스에만 공용 엔터티 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="a6306-352">사용 하지 않는 F# 모듈.</span><span class="sxs-lookup"><span data-stu-id="a6306-352">Do not use F# modules.</span></span>

<span data-ttu-id="a6306-353">구현 코드, 형식 유틸리티 및 유틸리티 함수를 포함 하려면 public이 아닌 모듈을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="a6306-354">정적 형식은 이어야 합니다. 기본 모듈을 통해 API의 향후 진화를 위한 내에서 사용할 수 없습니다는 오버 로드 및 다른.NET API 디자인 개념을 사용할 수 있으므로 F# 모듈.</span><span class="sxs-lookup"><span data-stu-id="a6306-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="a6306-355">예를 들어, 다음 공용 API 대신:</span><span class="sxs-lookup"><span data-stu-id="a6306-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="a6306-356">대신 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="a6306-357">사용 하 여 F# 형식의 디자인 않습니다 진화 하는 경우 바닐라.NET Api에서에서 레코드 종류</span><span class="sxs-lookup"><span data-stu-id="a6306-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="a6306-358">F#레코드 종류는 간단한.NET 클래스를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="a6306-359">이러한 Api의 일부 간단 하 고 안정적인 유형에 대해 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="a6306-360">사용을 고려해 야 합니다 `[<NoEquality>]` 및 `[<NoComparison>]` 특성을 인터페이스의 자동 생성 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-360">You should consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="a6306-361">또한 공용 필드에 이러한 노출으로 한 바닐라.NET Api의에서 변경 가능한 레코드 필드를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="a6306-361">Also avoid using mutable record fields in vanilla .NET APIs as these exposes a public field.</span></span> <span data-ttu-id="a6306-362">항상 클래스는 API의 향후 진화를 위한 유연한 옵션을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="a6306-363">예를 들어, 다음 F# 하는 공용 API를 노출 하는 코드를 C# 소비자:</span><span class="sxs-lookup"><span data-stu-id="a6306-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="a6306-364">F#:</span><span class="sxs-lookup"><span data-stu-id="a6306-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="a6306-365">C#: </span><span class="sxs-lookup"><span data-stu-id="a6306-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="a6306-366">표현의 숨기기 F# 바닐라.NET Api에서에서 공용 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="a6306-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="a6306-367">F#공용 구조체 형식을 자주 사용 되지 않는 구성 요소 경계에 대해서도 F#에서F# 코딩 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="a6306-368">구성 요소 및 라이브러리 내에서 내부적으로 사용 하는 경우에 뛰어난 구현 장치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="a6306-369">바닐라.NET API를 디자인할 때에 개인 선언 또는 서명 파일을 사용 하 여 공용 구조체 형식의 표현을 숨기기 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="a6306-370">또한 원하는 위해 내부적으로 멤버를 사용 하 여 공용 구조체 표현을 사용 하는 형식을 보강할 수 있습니다. NET 지향 API입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True

    /// A public member for use from C#
    member x.Evaluate =
        match x with
        | And(a,b) -> a.Evaluate && b.Evaluate
        | Not a -> not a.Evaluate
        | True -> true

    /// A public member for use from C#
    static member CreateAnd(a,b) = And(a,b)
```

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="a6306-371">GUI 디자인과 프레임 워크의 디자인 패턴을 사용 하 여 다른 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a6306-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="a6306-372">여러 다른 프레임 워크는 WinForms, WPF, ASP.NET 등.NET에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="a6306-373">이러한 프레임 워크에서 사용 하 여 구성 요소를 디자인 하는 경우 각각에 대 한 이름 지정 및 디자인 규칙 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="a6306-374">예를 들어 WPF 프로그래밍에 대 한 디자인 하는 클래스에 대 한 WPF 디자인 패턴을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="a6306-375">사용자 인터페이스 프로그래밍에서 모델에 대 한 이벤트와 같은 디자인 패턴을 사용 하 고 같은 알림 기반 컬렉션 <xref:System.Collections.ObjectModel>합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="a6306-376">개체 및 멤버 디자인 (다른.NET 언어에서 사용 하기 위한 라이브러리)</span><span class="sxs-lookup"><span data-stu-id="a6306-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="a6306-377">CLIEvent 특성을 사용 하 여.NET 이벤트를 노출 하려면</span><span class="sxs-lookup"><span data-stu-id="a6306-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="a6306-378">생성을 `DelegateEvent` 특정.NET을 사용 하 여 대리자 개체를 사용 하는 형식 및 `EventArgs` (아닌 `Event`만 사용 하는 `FSharpHandler` 기본적으로 형식으로) 다른.NET 언어에 익숙한 방식으로 이벤트를 게시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

```fsharp
type MyBadType() =
    let myEv = new Event<int>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish

type MyEventArgs(x: int) =
    inherit System.EventArgs()
    member this.X = x

    /// A type in a component designed for use from other .NET languages
type MyGoodType() =
    let myEv = new DelegateEvent<EventHandler<MyEventArgs>>()

    [<CLIEvent>]
    member this.MyEvent = myEv.Publish
```

#### <a name="expose-asynchronous-operations-as-methods-which-return-net-tasks"></a><span data-ttu-id="a6306-379">.NET 작업을 반환 하는 메서드로 비동기 작업 노출</span><span class="sxs-lookup"><span data-stu-id="a6306-379">Expose asynchronous operations as methods which return .NET tasks</span></span>

<span data-ttu-id="a6306-380">작업은 활성 비동기 계산을 나타내는.NET에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="a6306-381">보다 작은 구성 하는 일반적인 작업은 F# `Async<T>` 개체에 "이미 실행" 작업을 나타내며를 구성할 수 함께 수행 하는 병렬 컴퍼지션 또는 취소 신호 전파를 숨기는 방식 때문 및 다른 상황에 맞는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent “already executing” tasks and can’t be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="a6306-382">그러나 그럼에도 불구 하 고, 작업을 반환 하는 메서드는.NET에서 비동기 프로그래밍의 표준 표현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-382">However, despite this, methods which return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="a6306-383">자주 수행 하면 명시적 취소 토큰을 적용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="a6306-384">대신.NET 대리자 형식을 사용 하 여 F# 형식 함수</span><span class="sxs-lookup"><span data-stu-id="a6306-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="a6306-385">여기서 "F# 형식 함수"와 같은 "화살표" 형식은 의미 `int -> int`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-385">Here “F# function types” mean “arrow” types like `int -> int`.</span></span>

<span data-ttu-id="a6306-386">다음과 같이 변경 하는 대신</span><span class="sxs-lookup"><span data-stu-id="a6306-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="a6306-387">방법</span><span class="sxs-lookup"><span data-stu-id="a6306-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="a6306-388">F# 함수 형식으로 표시 됩니다 `class FSharpFunc<T,U>` 다른.NET 언어에 있으며 대리자 유형을 이해 하는 언어 기능 및 도구에 덜 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understand delegate types.</span></span> <span data-ttu-id="a6306-389">.NET Framework 3.5 이상을 대상으로 하는 고차 메서드를 작성할 때 합니다 `System.Func` 고 `System.Action` 대리자는.NET 개발자가 원활한 방식으로 이러한 Api를 사용할 수 있도록 게시할 오른쪽 Api.</span><span class="sxs-lookup"><span data-stu-id="a6306-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="a6306-390">(.NET Framework 2.0을 대상으로 하는 경우 시스템에 정의 된 대리자 형식 보다 제한적인는와 같은 미리 정의 된 대리자 형식을 사용 하는 것이 좋습니다 `System.Converter<T,U>` 또는 특정 대리자 형식을 정의 합니다.)</span><span class="sxs-lookup"><span data-stu-id="a6306-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="a6306-391">한편,.NET의 대리자는 자연 스러운 F#-연결 라이브러리 (다음 섹션을 참조 F#-연결 라이브러리).</span><span class="sxs-lookup"><span data-stu-id="a6306-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="a6306-392">모든 구현을 사용 하 여를 작성 하는 고차 메서드 바닐라.NET 라이브러리를 개발 하는 경우 일반적인 구현 전략 것 결과적으로, F# 형식 함수를 만든 다음 대리자를 사용 하 여 실제 F#구현입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="a6306-393">TryGetValue 패턴을 사용 하 여 반환 하는 대신 F# 값, 옵션 및 메서드 기록에 오버 로드 하는 것이 좋습니다. F# 값을 인수로 옵션</span><span class="sxs-lookup"><span data-stu-id="a6306-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="a6306-394">사용에 대 한 일반적인 패턴을 F# api에서 옵션 유형을 좋음 바닐라에 구현 된 표준.NET을 사용 하 여.NET Api 디자인 기술을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="a6306-395">반환 하는 대신는 F# 옵션 값, bool 반환 형식 및 패턴을 "TryGetValue"와 같이 out 매개 변수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="a6306-396">및 수행 하는 대신 F# 옵션 값을 매개 변수로, 메서드 오버 로드 또는 선택적 인수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

```fsharp
member this.ReturnOption() = Some 3

member this.ReturnBoolAndOut(outVal: byref<int>) =
    outVal <- 3
    true

member this.ParamOption(x: int, y: int option) =
    match y with
    | Some y2 -> x + y2
    | None -> x

member this.ParamOverload(x: int) = x

member this.ParamOverload(x: int, y: int) = x + y
```

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="a6306-397">.NET 컬렉션 인터페이스를 사용 하 여 형식을 IEnumerable\<T\> 및 IDictionary\<키, 값\> 매개 변수 및 반환 값</span><span class="sxs-lookup"><span data-stu-id="a6306-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="a6306-398">.NET 배열과 같은 구체적 컬렉션 형식의 사용 하지 않도록 `T[]`, F# 형식 `list<T>`, `Map<Key,Value>` 및 `Set<T>`, 및.NET 구체적 컬렉션 형식은 같은 `Dictionary<Key,Value>`.</span><span class="sxs-lookup"><span data-stu-id="a6306-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="a6306-399">.NET 라이브러리 디자인 지침과 같은 다양 한 컬렉션 형식을 사용 하는 경우에 대 한 적절 한 조언을 `IEnumerable<T>`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="a6306-400">배열의 일부 사용 (`T[]`) 성능 기준에 일부 경우에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="a6306-401">특히 유의 `seq<T>` 는 F# 별칭 `IEnumerable<T>`, 이므로 seq 종종는 바닐라.NET API에 대 한 적절 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="a6306-402">대신 F# 를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="a6306-403">사용 하 여 F# 시퀀스:</span><span class="sxs-lookup"><span data-stu-id="a6306-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="a6306-404">메서드의 유일한 입력된 형식으로 단위 유형을 사용 하 여 0 인수 메서드를 정의 또는 유일한으로 void 반환 메서드를 정의 하는 형식 반환</span><span class="sxs-lookup"><span data-stu-id="a6306-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="a6306-405">단위 형식의 다른 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="a6306-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="a6306-406">다음은 좋은입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="a6306-407">이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="a6306-408">바닐라.NET API 경계에 null 값에 대 한 확인</span><span class="sxs-lookup"><span data-stu-id="a6306-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="a6306-409">F#구현 코드를 변경할 수 없는 디자인 패턴 및 사용에 대 한 null 리터럴의 제한으로 인해 더 적은 수의 null 값이 있고 경향이 F# 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="a6306-410">다른.NET 언어 종종 null 값으로 훨씬 더 자주 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="a6306-411">이 인해 F# 는 바닐라.NET API를 노출 하는 코드에서 API 경계에서 null에 대 한 매개 변수를 확인 하 고에 대 한 자세한 흐름에서 이러한 값을 방지 해야 합니다 F# 구현 코드.</span><span class="sxs-lookup"><span data-stu-id="a6306-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="a6306-412">합니다 `isNull` 함수나에 패턴 일치는 `null` 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="a6306-413">튜플 반환 값으로 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="a6306-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="a6306-414">대신 데이터를 집계를 보유 하 고 있거나 out 매개 변수를 사용 하 여 여러 값을 반환 하는 명명 된 형식을 반환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="a6306-415">튜플과 구조체.net에서 있어도 (구조체 튜플에 대 한 C# 언어 지원 포함)는 가장 자주 제공 하지는 이상적인 및 예상 되는 API를.NET 개발자 용.</span><span class="sxs-lookup"><span data-stu-id="a6306-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="a6306-416">매개 변수 (currying)를 사용 하지 않도록</span><span class="sxs-lookup"><span data-stu-id="a6306-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="a6306-417">대신,.NET 호출 규칙을 사용 하 여 `Method(arg1,arg2,…,argN)`입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="a6306-418">팁: 모든.NET 언어에서 사용 하기 위한 라이브러리 디자인할 경우 몇 가지 실험적 맬웨어에 실제로 작업을 수행 하는 C# 및 Visual Basic 프로그래밍 "느낌 오른쪽" 이러한 언어에서 라이브러리 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-418">Tip: If you’re designing libraries for use from any .NET language, then there’s no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="a6306-419">또한 라이브러리 및 해당 설명서 개발자에 게 예상 대로 표시 되는지 확인 하려면 Visual Studio 개체 브라우저 및.NET Reflector와 같은 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="a6306-420">부록</span><span class="sxs-lookup"><span data-stu-id="a6306-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="a6306-421">디자인의 종단 간 예제 F# 다른.NET 언어 사용에 대 한 코드</span><span class="sxs-lookup"><span data-stu-id="a6306-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="a6306-422">다음 클래스를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-422">Consider the following class:</span></span>

```fsharp
open System

type Point1(angle,radius) =
    new() = Point1(angle=0.0, radius=0.0)
    member x.Angle = angle
    member x.Radius = radius
    member x.Stretch(l) = Point1(angle=x.Angle, radius=x.Radius * l)
    member x.Warp(f) = Point1(angle=f(x.Angle), radius=x.Radius)
    static member Circle(n) =
        [ for i in 1..n -> Point1(angle=2.0*Math.PI/float(n), radius=1.0) ]
```

<span data-ttu-id="a6306-423">유추 된 F# 형식의이 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-423">The inferred F# type of this class is as follows:</span></span>

```fsharp
type Point1 =
    new : unit -> Point1
    new : angle:double * radius:double -> Point1
    static member Circle : n:int -> Point1 list
    member Stretch : l:double -> Point1
    member Warp : f:(double -> double) -> Point1
    member Angle : double
    member Radius : double
```

<span data-ttu-id="a6306-424">하는 방법에 살펴보겠습니다이 F# 형식이 다른.NET 언어를 사용 하 여 프로그래머에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-424">Let’s take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="a6306-425">예를 들어, 대략적인 C# "서명"는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-425">For example, the approximate C# “signature” is as follows:</span></span>

```csharp
// C# signature for the unadjusted Point1 class
public class Point1
{
    public Point1();

    public Point1(double angle, double radius);

    public static Microsoft.FSharp.Collections.List<Point1> Circle(int count);

    public Point1 Stretch(double factor);

    public Point1 Warp(Microsoft.FSharp.Core.FastFunc<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="a6306-426">확인 방법에 대 한 중요 한 요소가 몇 가지 F# 나타냅니다 여기 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="a6306-427">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="a6306-427">For example:</span></span>

* <span data-ttu-id="a6306-428">인수 이름 같은 메타 데이터 유지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="a6306-429">F#될 두 개의 인수를 사용 하는 메서드와 C# 메서드를 두 개의 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="a6306-430">함수 및 목록에서 해당 형식에 대 한 참조 되는 F# 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="a6306-431">다음 코드에는 이러한 작업을 고려해 야 하는이 코드를 조정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-431">The following code shows how to adjust this code to take these things into account.</span></span>

```fsharp
namespace SuperDuperFSharpLibrary.Types

type RadialPoint(angle:double, radius:double) =

    /// Return a point at the origin
    new() = RadialPoint(angle=0.0, radius=0.0)

    /// The angle to the point, from the x-axis
    member x.Angle = angle

    /// The distance to the point, from the origin
    member x.Radius = radius

    /// Return a new point, with radius multiplied by the given factor
    member x.Stretch(factor) =
        RadialPoint(angle=angle, radius=radius * factor)

    /// Return a new point, with angle transformed by the function
    member x.Warp(transform:Func<_,_>) =
        RadialPoint(angle=transform.Invoke angle, radius=radius)

    /// Return a sequence of points describing an approximate circle using
    /// the given count of points
    static member Circle(count) =
        seq { for i in 1..count ->
                RadialPoint(angle=2.0*Math.PI/float(count), radius=1.0) }
```

<span data-ttu-id="a6306-432">유추 된 F# 코드의 종류는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-432">The inferred F# type of the code is as follows:</span></span>

```fsharp
type RadialPoint =
    new : unit -> RadialPoint
    new : angle:double * radius:double -> RadialPoint
    static member Circle : count:int -> seq<RadialPoint>
    member Stretch : factor:double -> RadialPoint
    member Warp : transform:System.Func<double,double> -> RadialPoint
    member Angle : double
    member Radius : double
```

<span data-ttu-id="a6306-433">C# 시그니처는 이제 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-433">The C# signature is now as follows:</span></span>

```csharp
public class RadialPoint
{
    public RadialPoint();

    public RadialPoint(double angle, double radius);

    public static System.Collections.Generic.IEnumerable<RadialPoint> Circle(int count);

    public RadialPoint Stretch(double factor);

    public RadialPoint Warp(System.Func<double,double> transform);

    public double Angle { get; }

    public double Radius { get; }
}
```

<span data-ttu-id="a6306-434">바닐라.NET 라이브러리의 일부는 다음과 같이이 형식을 사용 하 여 준비를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="a6306-435">여러 개의 이름을 조정: `Point1`, `n`, `l`, 및 `f` 되었습니다 `RadialPoint`를 `count`를 `factor`, 및 `transform`, 각각.</span><span class="sxs-lookup"><span data-stu-id="a6306-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="a6306-436">반환 형식을 사용한 `seq<RadialPoint>` 대신 `RadialPoint list` 사용 하 여 목록 생성을 변경 하 여 `[ ... ]` 사용 하 여 시퀀스 생성 `IEnumerable<RadialPoint>`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="a6306-437">.NET 대리자 형식을 사용한 `System.Func` 대신는 F# 함수 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="a6306-438">따라서 C# 코드에서 사용 하기 훨씬 편리한 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6306-438">This makes it far nicer to consume in C# code.</span></span>
