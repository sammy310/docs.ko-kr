---
title: F# 구성 요소 디자인 지침
description: '다른 호출자가 사용 하기 위한 F # 구성 요소를 작성 하기 위한 지침에 대해 알아봅니다.'
ms.date: 05/14/2018
ms.openlocfilehash: 590bda0660d54ea73c590d31e694f3d499e0fd9f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209138"
---
# <a name="f-component-design-guidelines"></a><span data-ttu-id="1c931-103">F# 구성 요소 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="1c931-103">F# component design guidelines</span></span>

<span data-ttu-id="1c931-104">이 문서는 f # 구성 요소 디자인 지침, v14, Microsoft Research 및 F # Software Foundation에서 원래 큐 레이트 및 유지 관리 된 버전을 기반으로 하는 F # 프로그래밍에 대 한 구성 요소 디자인 지침의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-104">This document is a set of component design guidelines for F# programming, based on the F# Component Design Guidelines, v14, Microsoft Research, and a version that was originally curated and maintained by the F# Software Foundation.</span></span>

<span data-ttu-id="1c931-105">이 문서에서는 F # 프로그래밍에 대해 잘 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-105">This document assumes you are familiar with F# programming.</span></span> <span data-ttu-id="1c931-106">이 가이드의 다양 한 버전에 대 한 유용한 피드백 및 유용한 피드백을 위해 F # 커뮤니티에 감사 드립니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-106">Many thanks to the F# community for their contributions and helpful feedback on various versions of this guide.</span></span>

## <a name="overview"></a><span data-ttu-id="1c931-107">개요</span><span class="sxs-lookup"><span data-stu-id="1c931-107">Overview</span></span>

<span data-ttu-id="1c931-108">이 문서에서는 F # 구성 요소 디자인 및 코딩 관련 문제 중 일부를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-108">This document looks at some of the issues related to F# component design and coding.</span></span> <span data-ttu-id="1c931-109">구성 요소는 다음 중 하나를 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-109">A component can mean any of the following:</span></span>

* <span data-ttu-id="1c931-110">해당 프로젝트 내에 외부 소비자가 있는 F # 프로젝트의 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-110">A layer in your F# project that has external consumers within that project.</span></span>
* <span data-ttu-id="1c931-111">어셈블리 경계에서 F # 코드를 사용 하기 위한 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-111">A library intended for consumption by F# code across assembly boundaries.</span></span>
* <span data-ttu-id="1c931-112">어셈블리 경계 전체에서 .NET 언어를 사용 하기 위한 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-112">A library intended for consumption by any .NET language across assembly boundaries.</span></span>
* <span data-ttu-id="1c931-113">[NuGet](https://nuget.org)과 같은 패키지 리포지토리를 통해 배포 하기 위한 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-113">A library intended for distribution via a package repository, such as [NuGet](https://nuget.org).</span></span>

<span data-ttu-id="1c931-114">이 문서에서 설명 하는 기술은 [좋은 F # 코드의 5 가지 원칙](index.md#five-principles-of-good-f-code)을 따르고 기능 및 개체 프로그래밍을 모두 적절 하 게 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-114">Techniques described in this article follow the [Five principles of good F# code](index.md#five-principles-of-good-f-code), and thus utilize both functional and object programming as appropriate.</span></span>

<span data-ttu-id="1c931-115">방법론에 관계 없이 구성 요소 및 라이브러리 디자이너는 개발자가 가장 쉽게 사용할 수 있는 API를 작성 하려고 할 때 많은 실용적이 고 prosaic 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-115">Regardless of the methodology, the component and library designer faces a number of practical and prosaic issues when trying to craft an API that is most easily usable by developers.</span></span> <span data-ttu-id="1c931-116">[.Net 라이브러리 디자인 지침](../../standard/design-guidelines/index.md) 의 Conscientious 응용 프로그램은 사용이 편리한 일관 된 api 집합을 만드는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-116">Conscientious application of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md) will steer you towards creating a consistent set of APIs that are pleasant to consume.</span></span>

## <a name="general-guidelines"></a><span data-ttu-id="1c931-117">일반 지침</span><span class="sxs-lookup"><span data-stu-id="1c931-117">General guidelines</span></span>

<span data-ttu-id="1c931-118">라이브러리에 대 한 의도 된 대상에 관계 없이 F # 라이브러리에 적용 되는 몇 가지 범용 지침이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-118">There are a few universal guidelines that apply to F# libraries, regardless of the intended audience for the library.</span></span>

### <a name="learn-the-net-library-design-guidelines"></a><span data-ttu-id="1c931-119">.NET 라이브러리 디자인 지침 알아보기</span><span class="sxs-lookup"><span data-stu-id="1c931-119">Learn the .NET Library Design Guidelines</span></span>

<span data-ttu-id="1c931-120">수행 중인 F # 코딩의 종류에 관계 없이 [.Net 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)에 대 한 실무 지식을 보유 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-120">Regardless of the kind of F# coding you are doing, it is valuable to have a working knowledge of the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="1c931-121">대부분의 다른 F # 및 .NET 프로그래머는 이러한 지침에 익숙하고 .NET 코드가 이러한 지침을 준수 하는 것으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-121">Most other F# and .NET programmers will be familiar with these guidelines, and expect .NET code to conform to them.</span></span>

<span data-ttu-id="1c931-122">.NET 라이브러리 디자인 지침은 이름 지정, 클래스 및 인터페이스 디자인, 멤버 디자인 (속성, 메서드, 이벤트 등) 등을 위한 일반적인 지침을 제공 하며, 다양 한 디자인 지침에 대 한 첫 번째 참조 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-122">The .NET Library Design Guidelines provide general guidance regarding naming, designing classes and interfaces, member design (properties, methods, events, etc.) and more, and are a useful first point of reference for a variety of design guidance.</span></span>

### <a name="add-xml-documentation-comments-to-your-code"></a><span data-ttu-id="1c931-123">코드에 XML 문서 주석 추가</span><span class="sxs-lookup"><span data-stu-id="1c931-123">Add XML documentation comments to your code</span></span>

<span data-ttu-id="1c931-124">공용 Api에 대 한 XML 문서를 통해 사용자는 이러한 형식과 멤버를 사용할 때 뛰어난 Intellisense 및 Quickinfo을 얻을 수 있으며 라이브러리의 문서 파일을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-124">XML documentation on public APIs ensures that users can get great Intellisense and Quickinfo when using these types and members, and enable building documentation files for the library.</span></span> <span data-ttu-id="1c931-125">Xmldoc 주석의 주석 내에서 추가 태그에 사용할 수 있는 다양 한 xml 태그에 대 한 [Xml 문서](../language-reference/xml-documentation.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c931-125">See the [XML Documentation](../language-reference/xml-documentation.md) about various xml tags that can be used for additional markup within xmldoc comments.</span></span>

```fsharp
/// A class for representing (x,y) coordinates
type Point =

    /// Computes the distance between this point and another
    member DistanceTo: otherPoint:Point -> float
```

<span data-ttu-id="1c931-126">약식 XML 주석 ( `/// comment` ) 또는 표준 xml 주석 () 중 하나를 사용할 수 있습니다 `///<summary>comment</summary>` .</span><span class="sxs-lookup"><span data-stu-id="1c931-126">You can use either the short form XML comments (`/// comment`), or standard XML comments (`///<summary>comment</summary>`).</span></span>

### <a name="consider-using-explicit-signature-files-fsi-for-stable-library-and-component-apis"></a><span data-ttu-id="1c931-127">안정적인 라이브러리 및 구성 요소 Api에 대 한 명시적 서명 파일 (. fsi.exe)을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-127">Consider using explicit signature files (.fsi) for stable library and component APIs</span></span>

<span data-ttu-id="1c931-128">F # 라이브러리의 명시적 서명 파일을 사용 하면 공용 API에 대 한 간결한 요약을 제공 하 여 라이브러리의 전체 공개 화면을 파악 하 고 공용 설명서와 내부 구현 세부 정보를 명확 하 게 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-128">Using explicit signatures files in an F# library provides a succinct summary of public API, which helps to ensure that you know the full public surface of your library, and provides a clean separation between public documentation and internal implementation details.</span></span> <span data-ttu-id="1c931-129">서명 파일은 구현 및 서명 파일에서 변경 내용을 적용 하도록 요구 하 여 공용 API를 변경 하는 것을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-129">Signature files add friction to changing the public API, by requiring changes to be made in both the implementation and signature files.</span></span> <span data-ttu-id="1c931-130">따라서 일반적으로 API가 solidified 되 고 더 이상 변경 될 것으로 예상 되지 않는 경우에만 서명 파일이 도입 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-130">As a result, signature files should typically only be introduced when an API has become solidified and is no longer expected to change significantly.</span></span>

### <a name="always-follow-best-practices-for-using-strings-in-net"></a><span data-ttu-id="1c931-131">.NET에서 문자열 사용에 대 한 모범 사례 항상 따르기</span><span class="sxs-lookup"><span data-stu-id="1c931-131">Always follow best practices for using strings in .NET</span></span>

<span data-ttu-id="1c931-132">[.Net 지침에서 문자열 사용에 대 한 모범 사례](../../standard/base-types/best-practices-strings.md) 를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-132">Follow [Best Practices for Using Strings in .NET](../../standard/base-types/best-practices-strings.md) guidance.</span></span> <span data-ttu-id="1c931-133">특히 문자열 (해당 하는 경우)의 변환과 비교 시 항상 *문화권* 을 명시적으로 명시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-133">In particular, always explicitly state *cultural intent* in the conversion and comparison of strings (where applicable).</span></span>

## <a name="guidelines-for-f-facing-libraries"></a><span data-ttu-id="1c931-134">F # 연결 라이브러리에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="1c931-134">Guidelines for F#-facing libraries</span></span>

<span data-ttu-id="1c931-135">이 섹션에서는 공용 F # 연결 라이브러리를 개발 하기 위한 권장 사항을 제공 합니다. 즉, F # 개발자가 사용 하기 위한 공용 Api를 노출 하는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-135">This section presents recommendations for developing public F#-facing libraries; that is, libraries exposing public APIs that are intended to be consumed by F# developers.</span></span> <span data-ttu-id="1c931-136">F #에 적용할 수 있는 다양 한 라이브러리 디자인 권장 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-136">There are a variety of library-design recommendations applicable specifically to F#.</span></span> <span data-ttu-id="1c931-137">다음에 나오는 특정 권장 사항이 없으면 .NET 라이브러리 디자인 지침을 대체 지침으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-137">In the absence of the specific recommendations that follow, the .NET Library Design Guidelines are the fallback guidance.</span></span>

### <a name="naming-conventions"></a><span data-ttu-id="1c931-138">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="1c931-138">Naming conventions</span></span>

#### <a name="use-net-naming-and-capitalization-conventions"></a><span data-ttu-id="1c931-139">.NET 명명 및 대문자화 규칙 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-139">Use .NET naming and capitalization conventions</span></span>

<span data-ttu-id="1c931-140">다음 표에서는 .NET 명명 및 대문자화 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-140">The following table follows .NET naming and capitalization conventions.</span></span> <span data-ttu-id="1c931-141">F # 구문을 포함 하는 데에는 약간의 추가 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-141">There are small additions to also include F# constructs.</span></span>

| <span data-ttu-id="1c931-142">구문</span><span class="sxs-lookup"><span data-stu-id="1c931-142">Construct</span></span> | <span data-ttu-id="1c931-143">사례</span><span class="sxs-lookup"><span data-stu-id="1c931-143">Case</span></span> | <span data-ttu-id="1c931-144">부분</span><span class="sxs-lookup"><span data-stu-id="1c931-144">Part</span></span> | <span data-ttu-id="1c931-145">예</span><span class="sxs-lookup"><span data-stu-id="1c931-145">Examples</span></span> | <span data-ttu-id="1c931-146">참고</span><span class="sxs-lookup"><span data-stu-id="1c931-146">Notes</span></span> |
|-----------|------|------|----------|-------|
| <span data-ttu-id="1c931-147">구체적 형식</span><span class="sxs-lookup"><span data-stu-id="1c931-147">Concrete types</span></span> | <span data-ttu-id="1c931-148">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-148">PascalCase</span></span> | <span data-ttu-id="1c931-149">명사/형용사</span><span class="sxs-lookup"><span data-stu-id="1c931-149">Noun/ adjective</span></span> | <span data-ttu-id="1c931-150">목록, Double, 복합</span><span class="sxs-lookup"><span data-stu-id="1c931-150">List, Double, Complex</span></span> | <span data-ttu-id="1c931-151">구체적 형식은 구조체, 클래스, 열거형, 대리자, 레코드 및 공용 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-151">Concrete types are structs, classes, enumerations, delegates, records, and unions.</span></span> <span data-ttu-id="1c931-152">형식 이름은 일반적으로 OCaml에서 소문자 이지만 F #은 형식에 대 한 .NET 명명 스키마를 채택 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-152">Though type names are traditionally lowercase in OCaml, F# has adopted the .NET naming scheme for types.</span></span>
| <span data-ttu-id="1c931-153">DLL</span><span class="sxs-lookup"><span data-stu-id="1c931-153">DLLs</span></span>           | <span data-ttu-id="1c931-154">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-154">PascalCase</span></span> |                 | <span data-ttu-id="1c931-155">Fabrikam. Core .dll</span><span class="sxs-lookup"><span data-stu-id="1c931-155">Fabrikam.Core.dll</span></span> |  |
| <span data-ttu-id="1c931-156">공용 구조체 태그</span><span class="sxs-lookup"><span data-stu-id="1c931-156">Union tags</span></span>     | <span data-ttu-id="1c931-157">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-157">PascalCase</span></span> | <span data-ttu-id="1c931-158">명사</span><span class="sxs-lookup"><span data-stu-id="1c931-158">Noun</span></span> | <span data-ttu-id="1c931-159">일부, 추가, 성공</span><span class="sxs-lookup"><span data-stu-id="1c931-159">Some, Add, Success</span></span> | <span data-ttu-id="1c931-160">공용 Api에는 접두사를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1c931-160">Do not use a prefix in public APIs.</span></span> <span data-ttu-id="1c931-161">필요에 따라 internal 인 경우 접두사를 사용 합니다 (예:).`type Teams = TAlpha | TBeta | TDelta.`</span><span class="sxs-lookup"><span data-stu-id="1c931-161">Optionally use a prefix when internal, such as `type Teams = TAlpha | TBeta | TDelta.`</span></span> |
| <span data-ttu-id="1c931-162">이벤트</span><span class="sxs-lookup"><span data-stu-id="1c931-162">Event</span></span>          | <span data-ttu-id="1c931-163">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-163">PascalCase</span></span> | <span data-ttu-id="1c931-164">동사</span><span class="sxs-lookup"><span data-stu-id="1c931-164">Verb</span></span> | <span data-ttu-id="1c931-165">ValueChanged/ValueChanging</span><span class="sxs-lookup"><span data-stu-id="1c931-165">ValueChanged / ValueChanging</span></span> |  |
| <span data-ttu-id="1c931-166">예외</span><span class="sxs-lookup"><span data-stu-id="1c931-166">Exceptions</span></span>     | <span data-ttu-id="1c931-167">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-167">PascalCase</span></span> |      | <span data-ttu-id="1c931-168">WebException</span><span class="sxs-lookup"><span data-stu-id="1c931-168">WebException</span></span> | <span data-ttu-id="1c931-169">이름은 "Exception"으로 끝나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-169">Name should end with "Exception".</span></span> |
| <span data-ttu-id="1c931-170">필드</span><span class="sxs-lookup"><span data-stu-id="1c931-170">Field</span></span>          | <span data-ttu-id="1c931-171">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-171">PascalCase</span></span> | <span data-ttu-id="1c931-172">명사</span><span class="sxs-lookup"><span data-stu-id="1c931-172">Noun</span></span> | <span data-ttu-id="1c931-173">CurrentName</span><span class="sxs-lookup"><span data-stu-id="1c931-173">CurrentName</span></span>  | |
| <span data-ttu-id="1c931-174">인터페이스 형식</span><span class="sxs-lookup"><span data-stu-id="1c931-174">Interface types</span></span> |  <span data-ttu-id="1c931-175">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-175">PascalCase</span></span> | <span data-ttu-id="1c931-176">명사/형용사</span><span class="sxs-lookup"><span data-stu-id="1c931-176">Noun/ adjective</span></span> | <span data-ttu-id="1c931-177">IDisposable</span><span class="sxs-lookup"><span data-stu-id="1c931-177">IDisposable</span></span> | <span data-ttu-id="1c931-178">이름은 "I"로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-178">Name should start with "I".</span></span> |
| <span data-ttu-id="1c931-179">메서드</span><span class="sxs-lookup"><span data-stu-id="1c931-179">Method</span></span> |  <span data-ttu-id="1c931-180">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-180">PascalCase</span></span> |  <span data-ttu-id="1c931-181">동사</span><span class="sxs-lookup"><span data-stu-id="1c931-181">Verb</span></span> | <span data-ttu-id="1c931-182">ToString</span><span class="sxs-lookup"><span data-stu-id="1c931-182">ToString</span></span> | |
| <span data-ttu-id="1c931-183">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="1c931-183">Namespace</span></span> | <span data-ttu-id="1c931-184">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-184">PascalCase</span></span> | | <span data-ttu-id="1c931-185">Fsharp.core</span><span class="sxs-lookup"><span data-stu-id="1c931-185">Microsoft.FSharp.Core</span></span> | <span data-ttu-id="1c931-186">일반적으로는 `<Organization>.<Technology>[.<Subnamespace>]` 기술이 조직과 독립적인 경우 조직을 삭제 하지만는 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-186">Generally use `<Organization>.<Technology>[.<Subnamespace>]`, though drop the organization if the technology is independent of organization.</span></span> |
| <span data-ttu-id="1c931-187">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1c931-187">Parameters</span></span> | <span data-ttu-id="1c931-188">camelCase</span><span class="sxs-lookup"><span data-stu-id="1c931-188">camelCase</span></span> | <span data-ttu-id="1c931-189">명사</span><span class="sxs-lookup"><span data-stu-id="1c931-189">Noun</span></span> |  <span data-ttu-id="1c931-190">typeName, transform, range</span><span class="sxs-lookup"><span data-stu-id="1c931-190">typeName, transform, range</span></span> | |
| <span data-ttu-id="1c931-191">값 허용 (내부)</span><span class="sxs-lookup"><span data-stu-id="1c931-191">let values (internal)</span></span> | <span data-ttu-id="1c931-192">camelCase 또는-Calcase</span><span class="sxs-lookup"><span data-stu-id="1c931-192">camelCase or PascalCase</span></span> | <span data-ttu-id="1c931-193">명사/동사</span><span class="sxs-lookup"><span data-stu-id="1c931-193">Noun/ verb</span></span> |  <span data-ttu-id="1c931-194">getValue, myTable</span><span class="sxs-lookup"><span data-stu-id="1c931-194">getValue, myTable</span></span> |
| <span data-ttu-id="1c931-195">값 허용 (외부)</span><span class="sxs-lookup"><span data-stu-id="1c931-195">let values (external)</span></span> | <span data-ttu-id="1c931-196">camelCase 또는-Calcase</span><span class="sxs-lookup"><span data-stu-id="1c931-196">camelCase or PascalCase</span></span> | <span data-ttu-id="1c931-197">명사/동사</span><span class="sxs-lookup"><span data-stu-id="1c931-197">Noun/verb</span></span>  | <span data-ttu-id="1c931-198">목록. 지도, 날짜. 오늘</span><span class="sxs-lookup"><span data-stu-id="1c931-198">List.map, Dates.Today</span></span> | <span data-ttu-id="1c931-199">let 바인딩 값은 일반적인 기능 디자인 패턴을 수행 하는 경우 일반적으로 public입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-199">let-bound values are often public when following traditional functional design patterns.</span></span> <span data-ttu-id="1c931-200">그러나는 다른 .NET 언어에서 식별자를 사용할 수 있는 경우 일반적으로가와 같은 경우를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-200">However, generally use PascalCase when the identifier can be used from other .NET languages.</span></span> |
| <span data-ttu-id="1c931-201">속성</span><span class="sxs-lookup"><span data-stu-id="1c931-201">Property</span></span>  | <span data-ttu-id="1c931-202">PascalCase</span><span class="sxs-lookup"><span data-stu-id="1c931-202">PascalCase</span></span>  | <span data-ttu-id="1c931-203">명사/형용사</span><span class="sxs-lookup"><span data-stu-id="1c931-203">Noun/ adjective</span></span>  | <span data-ttu-id="1c931-204">IsEndOfFile, 배경색</span><span class="sxs-lookup"><span data-stu-id="1c931-204">IsEndOfFile, BackColor</span></span>  | <span data-ttu-id="1c931-205">일반적으로 사용 되는 부울 속성은 IsNotEndOfFile가 아니라 IsEndOfFile에서와 같이 찬성 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-205">Boolean properties generally use Is and Can and should be affirmative, as in IsEndOfFile, not IsNotEndOfFile.</span></span>

#### <a name="avoid-abbreviations"></a><span data-ttu-id="1c931-206">약어 사용 안 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-206">Avoid abbreviations</span></span>

<span data-ttu-id="1c931-207">.NET 지침은 약어를 사용 하지 않습니다 (예: "이 아닌 사용 `OnButtonClick` `OnBtnClick` ").</span><span class="sxs-lookup"><span data-stu-id="1c931-207">The .NET guidelines discourage the use of abbreviations (for example, "use `OnButtonClick` rather than `OnBtnClick`").</span></span> <span data-ttu-id="1c931-208">"비동기"와 같은 일반적인 약어를 `Async` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-208">Common abbreviations, such as `Async` for "Asynchronous", are tolerated.</span></span> <span data-ttu-id="1c931-209">이 지침은 종종 함수형 프로그래밍에 대해 무시 됩니다. 예를 들어는 `List.iter` "반복"에 약어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-209">This guideline is sometimes ignored for functional programming; for example, `List.iter` uses an abbreviation for "iterate".</span></span> <span data-ttu-id="1c931-210">이러한 이유로, 약어를 사용 하는 것은 F #-F # 프로그래밍에서 더 높은 수준으로 허용 되지만 일반적으로 공용 구성 요소 디자인에서는 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-210">For this reason, using abbreviations tends to be tolerated to a greater degree in F#-to-F# programming, but should still generally be avoided in public component design.</span></span>

#### <a name="avoid-casing-name-collisions"></a><span data-ttu-id="1c931-211">대/소문자 이름 충돌 방지</span><span class="sxs-lookup"><span data-stu-id="1c931-211">Avoid casing name collisions</span></span>

<span data-ttu-id="1c931-212">일부 클라이언트 언어 (예: Visual Basic)는 대/소문자를 구분 하지 않으므로 .NET 지침에서는 이름 충돌을 명확 하 게 구분 하는 데 대/소문자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-212">The .NET guidelines say that casing alone cannot be used to disambiguate name collisions, since some client languages (for example, Visual Basic) are case-insensitive.</span></span>

#### <a name="use-acronyms-where-appropriate"></a><span data-ttu-id="1c931-213">적절 한 경우 머리글자어 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-213">Use acronyms where appropriate</span></span>

<span data-ttu-id="1c931-214">XML과 같은 머리글자어는 약어가 아니며 Xml (uncapitalized form)의 .NET 라이브러리에서 널리 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-214">Acronyms such as XML are not abbreviations and are widely used in .NET libraries in uncapitalized form (Xml).</span></span> <span data-ttu-id="1c931-215">잘 알려진 널리 알려진 머리글자어만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-215">Only well-known, widely recognized acronyms should be used.</span></span>

#### <a name="use-pascalcase-for-generic-parameter-names"></a><span data-ttu-id="1c931-216">제네릭 매개 변수 이름에 대 한 대/소문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-216">Use PascalCase for generic parameter names</span></span>

<span data-ttu-id="1c931-217">F # 연결 라이브러리를 비롯 하 여 공용 Api에서 제네릭 매개 변수 이름에 대해 대/소문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-217">Do use PascalCase for generic parameter names in public APIs, including for F#-facing libraries.</span></span> <span data-ttu-id="1c931-218">특히,,, `T` 임의의 제네릭 매개 변수에 대해,,와 같은 이름을 사용 하 `U` `T1` `T2` 고 특정 이름이 적합 한 경우 F # 연결 라이브러리에 대해,,와 같은 이름을 사용 `Key` `Value` `Arg` 합니다. 예를 들어는 그렇지 않습니다 `TKey` .</span><span class="sxs-lookup"><span data-stu-id="1c931-218">In particular, use names like `T`, `U`, `T1`, `T2` for arbitrary generic parameters, and when specific names make sense, then for F#-facing libraries use names like `Key`, `Value`, `Arg` (but not for example, `TKey`).</span></span>

#### <a name="use-either-pascalcase-or-camelcase-for-public-functions-and-values-in-f-modules"></a><span data-ttu-id="1c931-219">F # 모듈에서 public 함수 및 값에 대해 camelCase를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-219">Use either PascalCase or camelCase for public functions and values in F# modules</span></span>

<span data-ttu-id="1c931-220">camelCase는 정규화 되지 않은 (예: `invalidArg` )와 "표준 컬렉션 함수" (예: .map)에 대해 사용 하도록 디자인 된 공용 함수에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-220">camelCase is used for public functions that are designed to be used unqualified (for example, `invalidArg`), and for the "standard collection functions" (for example, List.map).</span></span> <span data-ttu-id="1c931-221">이러한 두 경우 모두 함수 이름은 언어의 키워드와 매우 유사 하 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-221">In both these cases, the function names act much like keywords in the language.</span></span>

### <a name="object-type-and-module-design"></a><span data-ttu-id="1c931-222">개체, 형식 및 모듈 디자인</span><span class="sxs-lookup"><span data-stu-id="1c931-222">Object, Type, and Module design</span></span>

#### <a name="use-namespaces-or-modules-to-contain-your-types-and-modules"></a><span data-ttu-id="1c931-223">네임 스페이스 또는 모듈을 사용 하 여 형식 및 모듈 포함</span><span class="sxs-lookup"><span data-stu-id="1c931-223">Use namespaces or modules to contain your types and modules</span></span>

<span data-ttu-id="1c931-224">구성 요소의 각 F # 파일은 네임 스페이스 선언 또는 모듈 선언으로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-224">Each F# file in a component should begin with either a namespace declaration or a module declaration.</span></span>

```fsharp
namespace Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
     ...

module CommonOperations =
    ...
```

<span data-ttu-id="1c931-225">또는</span><span class="sxs-lookup"><span data-stu-id="1c931-225">or</span></span>

```fsharp
module Fabrikam.BasicOperationsAndTypes

type ObjectType1() =
    ...

type ObjectType2() =
    ...

module CommonOperations =
    ...
```

<span data-ttu-id="1c931-226">모듈 및 네임 스페이스를 사용 하 여 최상위 수준에서 코드를 구성 하는 경우의 차이점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-226">The differences between using modules and namespaces to organize code at the top level are as follows:</span></span>

* <span data-ttu-id="1c931-227">네임 스페이스는 여러 파일에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-227">Namespaces can span multiple files</span></span>
* <span data-ttu-id="1c931-228">네임 스페이스는 내부 모듈 내에 있지 않은 경우 F # 함수를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-228">Namespaces cannot contain F# functions unless they are within an inner module</span></span>
* <span data-ttu-id="1c931-229">지정 된 모듈의 코드는 단일 파일 내에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-229">The code for any given module must be contained within a single file</span></span>
* <span data-ttu-id="1c931-230">최상위 모듈은 내부 모듈이 없어도 F # 함수를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-230">Top-level modules can contain F# functions without the need for an inner module</span></span>

<span data-ttu-id="1c931-231">최상위 네임 스페이스 또는 모듈 중에서 선택한 항목은 컴파일된 코드 형식에 영향을 주므로 다른 .NET 언어의 뷰에 영향을 줍니다. 그러면 API가 F # 코드 외부에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-231">The choice between a top-level namespace or module affects the compiled form of the code, and thus will affect the view from other .NET languages should your API eventually be consumed outside of F# code.</span></span>

#### <a name="use-methods-and-properties-for-operations-intrinsic-to-object-types"></a><span data-ttu-id="1c931-232">개체 형식에 대 한 기본 작업에 대 한 메서드 및 속성 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-232">Use methods and properties for operations intrinsic to object types</span></span>

<span data-ttu-id="1c931-233">개체를 사용할 때 사용할 수 있는 기능이 해당 형식에 대 한 메서드 및 속성으로 구현 되는지 확인 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-233">When working with objects, it is best to ensure that consumable functionality is implemented as methods and properties on that type.</span></span>

```fsharp
type HardwareDevice() =

    member this.ID = ...

    member this.SupportedProtocols = ...

type HashTable<'Key,'Value>(comparer: IEqualityComparer<'Key>) =

    member this.Add(key, value) = ...

    member this.ContainsKey(key) = ...

    member this.ContainsValue(value) = ...
```

<span data-ttu-id="1c931-234">지정 된 멤버에 대 한 대부분의 기능은 반드시 해당 멤버에 구현 해야 하는 것은 아니지만 해당 기능을 사용할 수 있는 부분은 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-234">The bulk of functionality for a given member need not necessarily be implemented in that member, but the consumable piece of that functionality should be.</span></span>

#### <a name="use-classes-to-encapsulate-mutable-state"></a><span data-ttu-id="1c931-235">클래스를 사용 하 여 변경 가능한 상태 캡슐화</span><span class="sxs-lookup"><span data-stu-id="1c931-235">Use classes to encapsulate mutable state</span></span>

<span data-ttu-id="1c931-236">F #에서는 클로저, 시퀀스 식 또는 비동기 계산과 같은 다른 언어 구문으로 해당 상태가 아직 캡슐화 되지 않은 경우에만이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-236">In F#, this only needs to be done where that state is not already encapsulated by another language construct, such as a closure, sequence expression, or asynchronous computation.</span></span>

```fsharp
type Counter() =
    // let-bound values are private in classes.
    let mutable count = 0

    member this.Next() =
        count <- count + 1
        count
```

#### <a name="use-interfaces-to-group-related-operations"></a><span data-ttu-id="1c931-237">인터페이스를 사용 하 여 관련 작업 그룹화</span><span class="sxs-lookup"><span data-stu-id="1c931-237">Use interfaces to group related operations</span></span>

<span data-ttu-id="1c931-238">인터페이스 형식을 사용 하 여 일련의 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-238">Use interface types to represent a set of operations.</span></span> <span data-ttu-id="1c931-239">함수 튜플 또는 함수 레코드와 같은 다른 옵션에는이 방법이 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-239">This is preferred to other options, such as tuples of functions or records of functions.</span></span>

```fsharp
type Serializer =
    abstract Serialize<'T>: preserveRefEq: bool -> value: 'T -> string
    abstract Deserialize<'T>: preserveRefEq: bool -> pickle: string -> 'T
```

<span data-ttu-id="1c931-240">기본 설정:</span><span class="sxs-lookup"><span data-stu-id="1c931-240">In preference to:</span></span>

```fsharp
type Serializer<'T> = {
    Serialize: bool -> 'T -> string
    Deserialize: bool -> string -> 'T
}
```

<span data-ttu-id="1c931-241">인터페이스는 일반적으로 함수에서 제공 하는 기능을 얻기 위해 사용할 수 있는 .NET의 최고 수준의 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-241">Interfaces are first-class concepts in .NET, which you can use to achieve what Functors would normally give you.</span></span> <span data-ttu-id="1c931-242">또한 함수 레코드를 사용 하 여 존재 형식을 프로그램으로 인코딩할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-242">Additionally, they can be used to encode existential types into your program, which records of functions cannot.</span></span>

#### <a name="use-a-module-to-group-functions-that-act-on-collections"></a><span data-ttu-id="1c931-243">모듈을 사용 하 여 컬렉션에 대해 작동 하는 함수 그룹화</span><span class="sxs-lookup"><span data-stu-id="1c931-243">Use a module to group functions that act on collections</span></span>

<span data-ttu-id="1c931-244">컬렉션 형식을 정의할 때 `CollectionType.map` `CollectionType.iter` 새 컬렉션 형식에 대해 및와 같은 표준 작업 집합을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-244">When you define a collection type, consider providing a standard set of operations like `CollectionType.map` and `CollectionType.iter`) for new collection types.</span></span>

```fsharp
module CollectionType =
    let map f c =
        ...
    let iter f c =
        ...
```

<span data-ttu-id="1c931-245">이러한 모듈을 포함 하는 경우 Fsharp.core에 있는 함수에 대 한 표준 명명 규칙을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1c931-245">If you include such a module, follow the standard naming conventions for functions found in FSharp.Core.</span></span>

#### <a name="use-a-module-to-group-functions-for-common-canonical-functions-especially-in-math-and-dsl-libraries"></a><span data-ttu-id="1c931-246">모듈을 사용 하 여 일반적인 정식 함수에 대 한 함수를 그룹화 합니다. 특히 수학 및 DSL 라이브러리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-246">Use a module to group functions for common, canonical functions, especially in math and DSL libraries</span></span>

<span data-ttu-id="1c931-247">예를 들어 `Microsoft.FSharp.Core.Operators` 는 `abs` fsharp.core에서 제공 하는 자동으로 열린 최상위 함수 (예: 및)의 컬렉션입니다 `sin` .</span><span class="sxs-lookup"><span data-stu-id="1c931-247">For example, `Microsoft.FSharp.Core.Operators` is an automatically opened collection of top-level functions (like `abs` and `sin`) provided by FSharp.Core.dll.</span></span>

<span data-ttu-id="1c931-248">마찬가지로, 통계 라이브러리에는 함수 및가 포함 된 모듈이 포함 될 수 있습니다 `erf` `erfc` . 여기서이 모듈은 명시적 또는 자동으로 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-248">Likewise, a statistics library might include a module with functions `erf` and `erfc`, where this module is designed to be explicitly or automatically opened.</span></span>

#### <a name="consider-using-requirequalifiedaccess-and-carefully-apply-autoopen-attributes"></a><span data-ttu-id="1c931-249">RequireQualifiedAccess 사용을 고려 하 고 AutoOpen 특성을 신중 하 게 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-249">Consider using RequireQualifiedAccess and carefully apply AutoOpen attributes</span></span>

<span data-ttu-id="1c931-250">모듈에 특성을 추가 하면 모듈이 `[<RequireQualifiedAccess>]` 열리지 않을 수 있으며 모듈의 요소에 대 한 참조에 명시적으로 정규화 된 액세스가 필요 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-250">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="1c931-251">예를 들어 `Microsoft.FSharp.Collections.List` 모듈에이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-251">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="1c931-252">이는 모듈의 함수 및 값에 다른 모듈의 이름과 충돌할 가능성이 있는 이름이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-252">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="1c931-253">정규화 된 액세스를 요구 하면 라이브러리의 장기 유지 관리 및 진화 크게 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-253">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

<span data-ttu-id="1c931-254">특성을 `[<AutoOpen>]` 모듈에 추가 하면 포함 하는 네임 스페이스를 열 때 모듈이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-254">Adding the `[<AutoOpen>]` attribute to a module means the module will be opened when the containing namespace is opened.</span></span> <span data-ttu-id="1c931-255">어셈블리 `[<AutoOpen>]` 에 특성을 적용 하 여 어셈블리를 참조할 때 자동으로 열리는 모듈을 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-255">The `[<AutoOpen>]` attribute may also be applied to an assembly to indicate a module that is automatically opened when the assembly is referenced.</span></span>

<span data-ttu-id="1c931-256">예를 들어, 통계 라이브러리 **MathsHeaven** 에는 포함 하는 `module MathsHeaven.Statistics.Operators` 함수 `erf` 및가 포함 될 수 있습니다. `erfc`</span><span class="sxs-lookup"><span data-stu-id="1c931-256">For example, a statistics library **MathsHeaven.Statistics** might contain a `module MathsHeaven.Statistics.Operators` containing functions `erf` and `erfc`.</span></span> <span data-ttu-id="1c931-257">이 모듈을로 표시 하는 것이 합리적입니다 `[<AutoOpen>]` .</span><span class="sxs-lookup"><span data-stu-id="1c931-257">It is reasonable to mark this module as `[<AutoOpen>]`.</span></span> <span data-ttu-id="1c931-258">즉, `open MathsHeaven.Statistics` 이 모듈을 열고 이름과 범위를 가져옵니다 `erf` `erfc` .</span><span class="sxs-lookup"><span data-stu-id="1c931-258">This means `open MathsHeaven.Statistics` will also open this module and bring the names `erf` and `erfc` into scope.</span></span> <span data-ttu-id="1c931-259">의 또 다른 용도 `[<AutoOpen>]` 는 확장 메서드를 포함 하는 모듈에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-259">Another good use of `[<AutoOpen>]` is for modules containing extension methods.</span></span>

<span data-ttu-id="1c931-260">를 과도 `[<AutoOpen>]` 하 게 사용 하면 충돌 하는 네임 스페이스로 이어질 수 있으며 특성은 주의 해 서 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-260">Overuse of `[<AutoOpen>]` leads to polluted namespaces, and the attribute should be used with care.</span></span> <span data-ttu-id="1c931-261">특정 도메인의 특정 라이브러리에 대해를 적절히 사용 하면 `[<AutoOpen>]` 유용성이 향상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-261">For specific libraries in specific domains, judicious use of `[<AutoOpen>]` can lead to better usability.</span></span>

#### <a name="consider-defining-operator-members-on-classes-where-using-well-known-operators-is-appropriate"></a><span data-ttu-id="1c931-262">잘 알려진 연산자를 사용 하는 경우 클래스에서 연산자 멤버를 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-262">Consider defining operator members on classes where using well-known operators is appropriate</span></span>

<span data-ttu-id="1c931-263">때로는 클래스를 사용 하 여 벡터와 같은 수학적 구문을 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-263">Sometimes classes are used to model mathematical constructs such as Vectors.</span></span> <span data-ttu-id="1c931-264">모델링 되는 도메인에 잘 알려진 연산자가 있는 경우 클래스의 내장 멤버로 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-264">When the domain being modeled has well-known operators, defining them as members intrinsic to the class is helpful.</span></span>

```fsharp
type Vector(x: float) =

    member v.X = x

    static member (*) (vector: Vector, scalar: float) = Vector(vector.X * scalar)

    static member (+) (vector1: Vector, vector2: Vector) = Vector(vector1.X + vector2.X)

let v = Vector(5.0)

let u = v * 10.0
```

<span data-ttu-id="1c931-265">이 지침은 이러한 유형에 대 한 일반 .NET 지침에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-265">This guidance corresponds to general .NET guidance for these types.</span></span> <span data-ttu-id="1c931-266">그러나 F # 코딩에서는 이러한 형식을 F # 함수 및 멤버 제약 조건이 있는 메서드 (예: sumBy)와 함께 사용할 수 있기 때문에이를 추가로 중요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-266">However, it can be additionally important in F# coding as this allows these types to be used in conjunction with F# functions and methods with member constraints, such as List.sumBy.</span></span>

#### <a name="consider-using-compiledname-to-provide-a-net-friendly-name-for-other-net-language-consumers"></a><span data-ttu-id="1c931-267">CompiledName를 사용 하 여를 제공 하는 것이 좋습니다. 다른 .NET 언어 소비자의 순 이름</span><span class="sxs-lookup"><span data-stu-id="1c931-267">Consider using CompiledName to provide a .NET-friendly name for other .NET language consumers</span></span>

<span data-ttu-id="1c931-268">경우에 따라 F # 소비자에 대해 한 가지 스타일로 이름을 바꿀 수 있습니다. 예를 들어 소문자가 모듈 바인딩 함수인 것 처럼 표시 되도록 하는 경우에는이 클래스를 어셈블리에 컴파일할 때 이름에 대 한 다른 스타일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-268">Sometimes you may wish to name something in one style for F# consumers (such as a static member in lower case so that it appears as if it were a module-bound function), but have a different style for the name when it is compiled into an assembly.</span></span> <span data-ttu-id="1c931-269">특성을 사용 `[<CompiledName>]` 하 여 어셈블리를 사용 하는 F # 코드가 아닌 다른 스타일을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-269">You can use the `[<CompiledName>]` attribute to provide a different style for non F# code consuming the assembly.</span></span>

```fsharp
type Vector(x:float, y:float) =

    member v.X = x
    member v.Y = y

    [<CompiledName("Create")>]
    static member create x y = Vector (x, y)

let v = Vector.create 5.0 3.0
```

<span data-ttu-id="1c931-270">를 사용 하면 `[<CompiledName>]` 어셈블리의 비 F # 소비자에 대해 .net 명명 규칙을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-270">By using `[<CompiledName>]`, you can use .NET naming conventions for non F# consumers of the assembly.</span></span>

#### <a name="use-method-overloading-for-member-functions-if-doing-so-provides-a-simpler-api"></a><span data-ttu-id="1c931-271">멤버 함수에 대 한 메서드 오버 로드를 사용 합니다 .이 경우 더 간단한 API를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-271">Use method overloading for member functions, if doing so provides a simpler API</span></span>

<span data-ttu-id="1c931-272">메서드 오버 로드는 다른 옵션 또는 인수를 사용 하 여 유사한 기능을 수행 해야 할 수 있는 API를 단순화 하는 강력한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-272">Method overloading is a powerful tool for simplifying an API that may need to perform similar functionality, but with different options or arguments.</span></span>

```fsharp
type Logger() =

    member this.Log(message) =
        ...
    member this.Log(message, retryPolicy) =
        ...
```

<span data-ttu-id="1c931-273">F #에서는 인수 형식이 아닌 인수 수에 대 한 오버 로드에 더 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-273">In F#, it is more common to overload on number of arguments rather than types of arguments.</span></span>

#### <a name="hide-the-representations-of-record-and-union-types-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="1c931-274">이러한 형식의 디자인이 개선 될 가능성이 있는 경우 record 및 union 형식의 표현을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-274">Hide the representations of record and union types if the design of these types is likely to evolve</span></span>

<span data-ttu-id="1c931-275">개체의 구체적인 표현은 노출 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1c931-275">Avoid revealing concrete representations of objects.</span></span> <span data-ttu-id="1c931-276">예를 들어, 값의 구체적인 표현은 <xref:System.DateTime> .net 라이브러리 디자인의 외부 공용 API에 의해 노출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-276">For example, the concrete representation of <xref:System.DateTime> values is not revealed by the external, public API of the .NET library design.</span></span> <span data-ttu-id="1c931-277">런타임에 공용 언어 런타임은 실행 전체에서 사용 되는 커밋된 구현을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-277">At run time, the Common Language Runtime knows the committed implementation that will be used throughout execution.</span></span> <span data-ttu-id="1c931-278">그러나 컴파일된 코드 자체가 구체적 표현에 대 한 종속성을 선택 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-278">However, compiled code doesn't itself pick up dependencies on the concrete representation.</span></span>

#### <a name="avoid-the-use-of-implementation-inheritance-for-extensibility"></a><span data-ttu-id="1c931-279">확장성을 위한 구현 상속 사용 방지</span><span class="sxs-lookup"><span data-stu-id="1c931-279">Avoid the use of implementation inheritance for extensibility</span></span>

<span data-ttu-id="1c931-280">F #에서 구현 상속은 거의 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-280">In F#, implementation inheritance is rarely used.</span></span> <span data-ttu-id="1c931-281">또한 상속 계층 구조는 복잡 하 고 새로운 요구 사항이 도착할 때 변경 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-281">Furthermore, inheritance hierarchies are often complex and difficult to change when new requirements arrive.</span></span> <span data-ttu-id="1c931-282">상속 구현은 여전히 F #에서 문제에 대 한 최상의 솔루션인 경우 이지만, 인터페이스 구현과 같이 다형성을 디자인할 때 F # 프로그램에서 대체 기술을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-282">Inheritance implementation still exists in F# for compatibility and rare cases where it is the best solution to a problem, but alternative techniques should be sought in your F# programs when designing for polymorphism, such as interface implementation.</span></span>

### <a name="function-and-member-signatures"></a><span data-ttu-id="1c931-283">함수 및 멤버 시그니처</span><span class="sxs-lookup"><span data-stu-id="1c931-283">Function and member signatures</span></span>

#### <a name="use-tuples-for-return-values-when-returning-a-small-number-of-multiple-unrelated-values"></a><span data-ttu-id="1c931-284">여러 개의 관련 없는 값을 반환 하는 경우 반환 값에 튜플 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-284">Use tuples for return values when returning a small number of multiple unrelated values</span></span>

<span data-ttu-id="1c931-285">반환 형식에서 튜플을 사용 하는 좋은 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-285">Here is a good example of using a tuple in a return type:</span></span>

```fsharp
val divrem: BigInteger -> BigInteger -> BigInteger * BigInteger
```

<span data-ttu-id="1c931-286">많은 구성 요소를 포함 하는 반환 형식 또는 구성 요소가 식별 가능한 단일 엔터티와 관련 된 경우 튜플 대신 명명 된 형식을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-286">For return types containing many components, or where the components are related to a single identifiable entity, consider using a named type instead of a tuple.</span></span>

#### <a name="use-asynct-for-async-programming-at-f-api-boundaries"></a><span data-ttu-id="1c931-287">`Async<T>`F # API 경계에서 비동기 프로그래밍에 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-287">Use `Async<T>` for async programming at F# API boundaries</span></span>

<span data-ttu-id="1c931-288">을 반환 하는 라는 해당 동기 작업이 있는 경우 비동기 작업은를 반환 하거나를 반환 하면 `Operation` `T` 이름을 지정 해야 합니다 `AsyncOperation` `Async<T>` `OperationAsync` `Task<T>` .</span><span class="sxs-lookup"><span data-stu-id="1c931-288">If there is a corresponding synchronous operation named `Operation` that returns a `T`, then the async operation should be named `AsyncOperation` if it returns `Async<T>` or `OperationAsync` if it returns `Task<T>`.</span></span> <span data-ttu-id="1c931-289">Begin/End 메서드를 노출 하는 일반적으로 사용 되는 .NET 형식의 경우를 사용 하 여 `Async.FromBeginEnd` 확장 메서드를 외관으로 작성 하 여 해당 .Net api에 F # 비동기 프로그래밍 모델을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-289">For commonly used .NET types that expose Begin/End methods, consider using `Async.FromBeginEnd` to write extension methods as a façade to provide the F# async programming model to those .NET APIs.</span></span>

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

### <a name="exceptions"></a><span data-ttu-id="1c931-290">예외</span><span class="sxs-lookup"><span data-stu-id="1c931-290">Exceptions</span></span>

<span data-ttu-id="1c931-291">예외, 결과 및 옵션의 적절 한 사용에 대 한 자세한 내용은 [오류 관리](conventions.md#error-management) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1c931-291">See [Error Management](conventions.md#error-management) to learn about appropriate use of exceptions, results, and options.</span></span>

### <a name="extension-members"></a><span data-ttu-id="1c931-292">확장 멤버</span><span class="sxs-lookup"><span data-stu-id="1c931-292">Extension Members</span></span>

#### <a name="carefully-apply-f-extension-members-in-f-to-f-components"></a><span data-ttu-id="1c931-293">F #-F # 구성 요소에서 F # 확장 멤버를 신중 하 게 적용</span><span class="sxs-lookup"><span data-stu-id="1c931-293">Carefully apply F# extension members in F#-to-F# components</span></span>

<span data-ttu-id="1c931-294">F # 확장 멤버는 일반적으로 대부분의 사용 모드에서 형식과 연결 된 내장 작업을 종료 하는 작업에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-294">F# extension members should generally only be used for operations that are in the closure of intrinsic operations associated with a type in the majority of its modes of use.</span></span> <span data-ttu-id="1c931-295">일반적인 한 가지 용도는 다양 한 .NET 형식의 F #에 더 자연 스러운 Api를 제공 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-295">One common use is to provide APIs that are more idiomatic to F# for various .NET types:</span></span>

```fsharp
type System.ServiceModel.Channels.IInputChannel with
    member this.AsyncReceive() =
        Async.FromBeginEnd(this.BeginReceive, this.EndReceive)

type System.Collections.Generic.IDictionary<'Key,'Value> with
    member this.TryGet key =
        let ok, v = this.TryGetValue key
        if ok then Some v else None
```

### <a name="union-types"></a><span data-ttu-id="1c931-296">공용 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="1c931-296">Union Types</span></span>

#### <a name="use-discriminated-unions-instead-of-class-hierarchies-for-tree-structured-data"></a><span data-ttu-id="1c931-297">트리 구조 데이터에 대 한 클래스 계층 구조 대신 구별 된 공용 구조체 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-297">Use discriminated unions instead of class hierarchies for tree-structured data</span></span>

<span data-ttu-id="1c931-298">트리 형태의 구조는 재귀적으로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-298">Tree-like structures are recursively defined.</span></span> <span data-ttu-id="1c931-299">이는 상속에는 적합 하지 않지만 구별 된 공용 구조체에는 세련 된 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-299">This is awkward with inheritance, but elegant with Discriminated Unions.</span></span>

```fsharp
type BST<'T> =
    | Empty
    | Node of 'T * BST<'T> * BST<'T>
```

<span data-ttu-id="1c931-300">구별 된 공용 구조체를 사용 하 여 트리 형태의 데이터를 표시 하면 패턴 일치에 exhaustiveness의 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-300">Representing tree-like data with Discriminated Unions also allows you to benefit from exhaustiveness in pattern matching.</span></span>

#### <a name="use-requirequalifiedaccess-on-union-types-whose-case-names-are-not-sufficiently-unique"></a><span data-ttu-id="1c931-301">`[<RequireQualifiedAccess>]`대/소문자 이름이 충분히 고유 하지 않은 공용 구조체 형식에 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-301">Use `[<RequireQualifiedAccess>]` on union types whose case names are not sufficiently unique</span></span>

<span data-ttu-id="1c931-302">동일한 이름이 구별 된 공용 구조체 케이스와 같은 다른 항목에 대 한 최상의 이름인 도메인에서 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-302">You may find yourself in a domain where the same name is the best name for different things, such as Discriminated Union cases.</span></span> <span data-ttu-id="1c931-303">를 사용 하 여 `[<RequireQualifiedAccess>]` 문의 순서에 따라 발생 하는 섀도잉으로 인 한 혼동을 방지 하기 위해를 사용 하 여 대/소문자 이름을 구분할 수 있습니다. `open`</span><span class="sxs-lookup"><span data-stu-id="1c931-303">You can use `[<RequireQualifiedAccess>]` to disambiguate case names in order to avoid triggering confusing errors due to shadowing dependent on the ordering of `open` statements</span></span>

#### <a name="hide-the-representations-of-discriminated-unions-for-binary-compatible-apis-if-the-design-of-these-types-is-likely-to-evolve"></a><span data-ttu-id="1c931-304">이러한 형식의 디자인이 개선 될 가능성이 있는 경우 이진 호환 Api에 대 한 구별 된 공용 구조체의 표현을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-304">Hide the representations of discriminated unions for binary compatible APIs if the design of these types is likely to evolve</span></span>

<span data-ttu-id="1c931-305">공용 구조체 형식은 간결한 프로그래밍 모델에 대 한 F # 패턴 일치 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-305">Unions types rely on F# pattern-matching forms for a succinct programming model.</span></span> <span data-ttu-id="1c931-306">앞에서 설명한 것 처럼 이러한 형식의 디자인이 발전 될 가능성이 있는 경우 구체적인 데이터 표현을 노출 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-306">As mentioned previously, you should avoid revealing concrete data representations if the design of these types is likely to evolve.</span></span>

<span data-ttu-id="1c931-307">예를 들어, private 또는 internal 선언을 사용 하거나 서명 파일을 사용 하 여 구별 된 공용 구조체의 표현을 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-307">For example, the representation of a discriminated union can be hidden using a private or internal declaration, or by using a signature file.</span></span>

```fsharp
type Union =
    private
    | CaseA of int
    | CaseB of string
```

<span data-ttu-id="1c931-308">구별 된 공용 구조체 무제한 증가할을 표시 하는 경우 사용자 코드를 손상 시 키 지 않고 라이브러리의 버전을 확인 하는 것이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-308">If you reveal discriminated unions indiscriminately, you may find it hard to version your library without breaking user code.</span></span> <span data-ttu-id="1c931-309">대신, 형식의 값에 대 한 패턴 일치를 허용 하는 하나 이상의 활성 패턴을 노출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-309">Instead, consider revealing one or more active patterns to permit pattern matching over values of your type.</span></span>

<span data-ttu-id="1c931-310">활성 패턴은 F # 공용 구조체 형식을 직접 노출 하지 않고 F # 소비자에 게 패턴 일치를 제공 하는 대체 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-310">Active patterns provide an alternate way to provide F# consumers with pattern matching while avoiding exposing F# Union Types directly.</span></span>

### <a name="inline-functions-and-member-constraints"></a><span data-ttu-id="1c931-311">인라인 함수 및 멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="1c931-311">Inline Functions and Member Constraints</span></span>

#### <a name="define-generic-numeric-algorithms-using-inline-functions-with-implied-member-constraints-and-statically-resolved-generic-types"></a><span data-ttu-id="1c931-312">암시적 멤버 제약 조건 및 정적으로 확인 된 제네릭 형식으로 인라인 함수를 사용 하 여 제네릭 숫자 알고리즘 정의</span><span class="sxs-lookup"><span data-stu-id="1c931-312">Define generic numeric algorithms using inline functions with implied member constraints and statically resolved generic types</span></span>

<span data-ttu-id="1c931-313">산술 멤버 제약 조건 및 F # 비교 제약 조건은 F # 프로그래밍에 대 한 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-313">Arithmetic member constraints and F# comparison constraints are a standard for F# programming.</span></span> <span data-ttu-id="1c931-314">예를 들어, 다음 코드를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="1c931-314">For example, consider the following code:</span></span>

```fsharp
let inline highestCommonFactor a b =
    let rec loop a b =
        if a = LanguagePrimitives.GenericZero<_> then b
        elif a < b then loop a (b - a)
        else loop (a - b) b
    loop a b
```

<span data-ttu-id="1c931-315">이 함수의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-315">The type of this function is as follows:</span></span>

```fsharp
val inline highestCommonFactor : ^T -> ^T -> ^T
                when ^T : (static member Zero : ^T)
                and ^T : (static member ( - ) : ^T * ^T -> ^T)
                and ^T : equality
                and ^T : comparison
```

<span data-ttu-id="1c931-316">이는 수학적 라이브러리의 공용 API에 적합 한 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-316">This is a suitable function for a public API in a mathematical library.</span></span>

#### <a name="avoid-using-member-constraints-to-simulate-type-classes-and-duck-typing"></a><span data-ttu-id="1c931-317">멤버 제약 조건을 사용 하 여 형식 클래스 및 오리 형식화를 시뮬레이션 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-317">Avoid using member constraints to simulate type classes and duck typing</span></span>

<span data-ttu-id="1c931-318">F # 멤버 제약 조건을 사용 하 여 "오리 입력"을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-318">It is possible to simulate "duck typing" using F# member constraints.</span></span> <span data-ttu-id="1c931-319">그러나이를 사용 하는 멤버는 일반적으로 F #-F # 라이브러리 디자인에서 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-319">However, members that make use of this should not in general be used in F#-to-F# library designs.</span></span> <span data-ttu-id="1c931-320">이는 익숙하지 않은 암시적 또는 비표준 암시적 제약 조건을 기반으로 하는 라이브러리 디자인이 사용자 코드를 특정 한 프레임 워크 패턴에 연결 하는 경향이 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-320">This is because library designs based on unfamiliar or non-standard implicit constraints tend to cause user code to become inflexible and tied to one particular framework pattern.</span></span>

<span data-ttu-id="1c931-321">또한 이러한 방식으로 멤버 제약 조건을 많이 사용 하면 컴파일 시간이 길어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-321">Additionally, there is a good chance that heavy use of member constraints in this manner can result in very long compile times.</span></span>

### <a name="operator-definitions"></a><span data-ttu-id="1c931-322">연산자 정의</span><span class="sxs-lookup"><span data-stu-id="1c931-322">Operator Definitions</span></span>

#### <a name="avoid-defining-custom-symbolic-operators"></a><span data-ttu-id="1c931-323">사용자 지정 기호화 된 연산자 정의 방지</span><span class="sxs-lookup"><span data-stu-id="1c931-323">Avoid defining custom symbolic operators</span></span>

<span data-ttu-id="1c931-324">사용자 지정 연산자는 일부 상황에서 필수적 이며, 구현 코드의 큰 본문 내에서 매우 유용한 표기법 밑수 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-324">Custom operators are essential in some situations and are highly useful notational devices within a large body of implementation code.</span></span> <span data-ttu-id="1c931-325">라이브러리의 새 사용자의 경우 명명 된 함수를 사용 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-325">For new users of a library, named functions are often easier to use.</span></span> <span data-ttu-id="1c931-326">또한 사용자 지정 기호화 된 연산자는 문서화 하기 어려울 수 있으며, 사용자는 IDE와 검색 엔진의 기존 제한 사항으로 인해 운영자에 대 한 도움말을 조회 하는 것이 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-326">In addition, custom symbolic operators can be hard to document, and users find it more difficult to look up help on operators, due to existing limitations in IDE and search engines.</span></span>

<span data-ttu-id="1c931-327">따라서 기능을 명명 된 함수 및 멤버와 함께 게시 하는 것이 가장 좋지만,이 기능에 대 한 표기법 밑수 혜택을 통해 설명서 및 인식 비용 보다 더 큰 경우에만이 기능에 대 한 연산자를 추가로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-327">As a result, it is best to publish your functionality as named functions and members, and additionally expose operators for this functionality only if the notational benefits outweigh the documentation and cognitive cost of having them.</span></span>

### <a name="units-of-measure"></a><span data-ttu-id="1c931-328">측정 단위</span><span class="sxs-lookup"><span data-stu-id="1c931-328">Units of Measure</span></span>

#### <a name="carefully-use-units-of-measure-for-added-type-safety-in-f-code"></a><span data-ttu-id="1c931-329">F # 코드에서 추가 형식 안전을 위해 측정 단위를 신중히 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-329">Carefully use units of measure for added type safety in F# code</span></span>

<span data-ttu-id="1c931-330">측정 단위에 대 한 추가 정보 입력 정보는 다른 .NET 언어에서 볼 때 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-330">Additional typing information for units of measure is erased when viewed by other .NET languages.</span></span> <span data-ttu-id="1c931-331">.NET 구성 요소, 도구 및 리플렉션에서는 형식-san을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-331">Be aware that .NET components, tools, and reflection will see types-sans-units.</span></span> <span data-ttu-id="1c931-332">예를 들어 c # 소비자는가 아닌를 표시 합니다 `float` `float<kg>` .</span><span class="sxs-lookup"><span data-stu-id="1c931-332">For example, C# consumers will see `float` rather than `float<kg>`.</span></span>

### <a name="type-abbreviations"></a><span data-ttu-id="1c931-333">형식 약어</span><span class="sxs-lookup"><span data-stu-id="1c931-333">Type Abbreviations</span></span>

#### <a name="carefully-use-type-abbreviations-to-simplify-f-code"></a><span data-ttu-id="1c931-334">신중 하 게 형식 약어를 사용 하 여 F # 코드 간소화</span><span class="sxs-lookup"><span data-stu-id="1c931-334">Carefully use type abbreviations to simplify F# code</span></span>

<span data-ttu-id="1c931-335">.NET 구성 요소, 도구 및 리플렉션에서는 형식에 대 한 약식 이름이 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-335">.NET components, tools, and reflection will not see abbreviated names for types.</span></span> <span data-ttu-id="1c931-336">형식 약어의 중요 한 사용으로 인해 실제로는 도메인 보다 더 복잡 하 게 표시 되어 소비자를 혼동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-336">Significant usage of type abbreviations can also make a domain appear more complex than it actually is, which could confuse consumers.</span></span>

#### <a name="avoid-type-abbreviations-for-public-types-whose-members-and-properties-should-be-intrinsically-different-to-those-available-on-the-type-being-abbreviated"></a><span data-ttu-id="1c931-337">해당 멤버 및 속성이 약식으로 사용 가능한 형식에 대해 사용 가능한 멤버와 속성이 본질적으로 다른 공용 형식에 대 한 형식 약어를 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-337">Avoid type abbreviations for public types whose members and properties should be intrinsically different to those available on the type being abbreviated</span></span>

<span data-ttu-id="1c931-338">이 경우 약식으로 표시 되는 형식은 정의할 실제 형식의 표현에 대해 너무 많이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-338">In this case, the type being abbreviated reveals too much about the representation of the actual type being defined.</span></span> <span data-ttu-id="1c931-339">대신 클래스 형식 또는 단일 대/소문자 구분 된 공용 구조체에 약어를 래핑하는 것이 좋습니다. 또는 성능이 중요 한 경우에는 구조체 형식을 사용 하 여 약어를 래핑하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-339">Instead, consider wrapping the abbreviation in a class type or a single-case discriminated union (or, when performance is essential, consider using a struct type to wrap the abbreviation).</span></span>

<span data-ttu-id="1c931-340">예를 들어 F # 맵의 특수 한 경우에 다중 맵을 정의 하는 것이 좋습니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-340">For example, it is tempting to define a multi-map as a special case of an F# map, for example:</span></span>

```fsharp
type MultiMap<'Key,'Value> = Map<'Key,'Value list>
```

<span data-ttu-id="1c931-341">그러나이 형식에 대 한 논리 점 표기법 연산은 맵의 작업과 동일 하지 않습니다. 예를 들어 조회 연산자가 매핑됩니다. [key] 키가 사전에 없는 경우 예외를 발생 시 키 지 않고 빈 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-341">However, the logical dot-notation operations on this type are not the same as the operations on a Map – for example, it is reasonable that the lookup operator map.[key] return the empty list if the key is not in the dictionary, rather than raising an exception.</span></span>

## <a name="guidelines-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="1c931-342">다른 .NET 언어에서 사용 하는 라이브러리에 대 한 지침</span><span class="sxs-lookup"><span data-stu-id="1c931-342">Guidelines for libraries for Use from other .NET Languages</span></span>

<span data-ttu-id="1c931-343">다른 .NET 언어에서 사용할 라이브러리를 디자인할 때는 [.Net 라이브러리 디자인 지침](../../standard/design-guidelines/index.md)을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-343">When designing libraries for use from other .NET languages, it is important to adhere to the [.NET Library Design Guidelines](../../standard/design-guidelines/index.md).</span></span> <span data-ttu-id="1c931-344">이 문서에서 이러한 라이브러리는 제한 없이 F # 구문을 사용 하는 F # 연결 라이브러리와는 달리 바닐라 .NET 라이브러리로 레이블이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-344">In this document, these libraries are labeled as vanilla .NET libraries, as opposed to F#-facing libraries that use F# constructs without restriction.</span></span> <span data-ttu-id="1c931-345">바닐라 .NET 라이브러리 디자인은 공용 API에서 F # 관련 구문의 사용을 최소화 하 여 친숙 하 고 자연 스러운 Api를 나머지 .NET Framework와 일치 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-345">Designing vanilla .NET libraries means providing familiar and idiomatic APIs consistent with the rest of the .NET Framework by minimizing the use of F#-specific constructs in the public API.</span></span> <span data-ttu-id="1c931-346">규칙은 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-346">The rules are explained in the following sections.</span></span>

### <a name="namespace-and-type-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="1c931-347">네임 스페이스 및 형식 디자인 (다른 .NET 언어에서 사용 하는 라이브러리의 경우)</span><span class="sxs-lookup"><span data-stu-id="1c931-347">Namespace and Type design (for libraries for use from other .NET Languages)</span></span>

#### <a name="apply-the-net-naming-conventions-to-the-public-api-of-your-components"></a><span data-ttu-id="1c931-348">구성 요소의 공용 API에 .NET 명명 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-348">Apply the .NET naming conventions to the public API of your components</span></span>

<span data-ttu-id="1c931-349">약식 이름 및 .NET 대문자화 지침 사용에 특히 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-349">Pay special attention to the use of abbreviated names and the .NET capitalization guidelines.</span></span>

```fsharp
type pCoord = ...
    member this.theta = ...

type PolarCoordinate = ...
    member this.Theta = ...
```

#### <a name="use-namespaces-types-and-members-as-the-primary-organizational-structure-for-your-components"></a><span data-ttu-id="1c931-350">네임 스페이스, 형식 및 멤버를 구성 요소의 기본 조직 구조로 사용</span><span class="sxs-lookup"><span data-stu-id="1c931-350">Use namespaces, types, and members as the primary organizational structure for your components</span></span>

<span data-ttu-id="1c931-351">Public 기능을 포함 하는 모든 파일은 선언으로 시작 해야 `namespace` 하며 네임 스페이스의 공용 엔터티는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-351">All files containing public functionality should begin with a `namespace` declaration, and the only public-facing entities in namespaces should be types.</span></span> <span data-ttu-id="1c931-352">F # 모듈은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1c931-352">Do not use F# modules.</span></span>

<span data-ttu-id="1c931-353">공용이 아닌 모듈을 사용 하 여 구현 코드, 유틸리티 형식 및 유틸리티 함수를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-353">Use non-public modules to hold implementation code, utility types, and utility functions.</span></span>

<span data-ttu-id="1c931-354">정적 형식은 F # 모듈 내에서 사용할 수 없는 오버 로드 및 기타 .NET API 디자인 개념을 사용 하기 위해 나중에 API를 발전 시킬 수 있으므로 모듈 보다 우선적으로 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-354">Static types should be preferred over modules, as they allow for future evolution of the API to use overloading and other .NET API design concepts that may not be used within F# modules.</span></span>

<span data-ttu-id="1c931-355">예를 들어 다음과 같은 공용 API 대신</span><span class="sxs-lookup"><span data-stu-id="1c931-355">For example, in place of the following public API:</span></span>

```fsharp
module Fabrikam

module Utilities =
    let Name = "Bob"
    let Add2 x y = x + y
    let Add3 x y z = x + y + z
```

<span data-ttu-id="1c931-356">대신 다음을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1c931-356">Consider instead:</span></span>

```fsharp
namespace Fabrikam

[<AbstractClass; Sealed>]
type Utilities =
    static member Name = "Bob"
    static member Add(x,y) = x + y
    static member Add(x,y,z) = x + y + z
```

#### <a name="use-f-record-types-in-vanilla-net-apis-if-the-design-of-the-types-wont-evolve"></a><span data-ttu-id="1c931-357">형식의 디자인이 진화 하지 않는 경우 바닐라 .NET Api에서 F # 레코드 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-357">Use F# record types in vanilla .NET APIs if the design of the types won't evolve</span></span>

<span data-ttu-id="1c931-358">F # 레코드 형식은 간단한 .NET 클래스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-358">F# record types compile to a simple .NET class.</span></span> <span data-ttu-id="1c931-359">이는 Api의 몇 가지 단순 하 고 안정적인 형식에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-359">These are suitable for some simple, stable types in APIs.</span></span> <span data-ttu-id="1c931-360">`[<NoEquality>]` `[<NoComparison>]` 인터페이스의 자동 생성을 억제 하려면 및 특성을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-360">Consider using the `[<NoEquality>]` and `[<NoComparison>]` attributes to suppress the automatic generation of interfaces.</span></span> <span data-ttu-id="1c931-361">또한 바닐라 .NET Api에서 변경 가능한 레코드 필드를 사용 하지 마십시오. 이러한 필드는 public 필드를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-361">Also avoid using mutable record fields in vanilla .NET APIs as these expose a public field.</span></span> <span data-ttu-id="1c931-362">항상 클래스가 향후 API의 진화에 보다 유연한 옵션을 제공 하는지 여부를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-362">Always consider whether a class would provide a more flexible option for future evolution of the API.</span></span>

<span data-ttu-id="1c931-363">예를 들어 다음 F # 코드는 c # 소비자에 게 공용 API를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-363">For example, the following F# code exposes the public API to a C# consumer:</span></span>

<span data-ttu-id="1c931-364">F#:</span><span class="sxs-lookup"><span data-stu-id="1c931-364">F#:</span></span>

```fsharp
[<NoEquality; NoComparison>]
type MyRecord =
    { FirstThing: int
        SecondThing: string }
```

<span data-ttu-id="1c931-365">C#:</span><span class="sxs-lookup"><span data-stu-id="1c931-365">C#:</span></span>

```csharp
public sealed class MyRecord
{
    public MyRecord(int firstThing, string secondThing);
    public int FirstThing { get; }
    public string SecondThing { get; }
}
```

#### <a name="hide-the-representation-of-f-union-types-in-vanilla-net-apis"></a><span data-ttu-id="1c931-366">바닐라 .NET Api에서 F # 공용 구조체 형식의 표현을 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-366">Hide the representation of F# union types in vanilla .NET APIs</span></span>

<span data-ttu-id="1c931-367">F # 공용 구조체 형식은 F #-F # 코딩에도 불구 하 고 일반적으로 구성 요소 경계에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-367">F# union types are not commonly used across component boundaries, even for F#-to-F# coding.</span></span> <span data-ttu-id="1c931-368">구성 요소와 라이브러리 내에서 내부적으로 사용 되는 경우에는 뛰어난 구현 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-368">They are an excellent implementation device when used internally within components and libraries.</span></span>

<span data-ttu-id="1c931-369">바닐라 .NET API를 디자인할 때 전용 선언이 나 서명 파일을 사용 하 여 공용 구조체 형식의 표현을 숨기는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-369">When designing a vanilla .NET API, consider hiding the representation of a union type by using either a private declaration or a signature file.</span></span>

```fsharp
type PropLogic =
    private
    | And of PropLogic * PropLogic
    | Not of PropLogic
    | True
```

<span data-ttu-id="1c931-370">또한 멤버와 내부적으로 공용 구조체 표현을 사용 하는 형식을 보강 하 여 원하는를 제공할 수 있습니다. 네트워크 연결 API.</span><span class="sxs-lookup"><span data-stu-id="1c931-370">You may also augment types that use a union representation internally with members to provide a desired .NET-facing API.</span></span>

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

#### <a name="design-gui-and-other-components-using-the-design-patterns-of-the-framework"></a><span data-ttu-id="1c931-371">프레임 워크의 디자인 패턴을 사용 하 여 GUI 및 기타 구성 요소 디자인</span><span class="sxs-lookup"><span data-stu-id="1c931-371">Design GUI and other components using the design patterns of the framework</span></span>

<span data-ttu-id="1c931-372">.NET 내에서는 WinForms, WPF, ASP.NET 등 다양 한 프레임 워크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-372">There are many different frameworks available within .NET, such as WinForms, WPF, and ASP.NET.</span></span> <span data-ttu-id="1c931-373">이러한 프레임 워크에 사용할 구성 요소를 디자인 하는 경우 각각에 대 한 명명 및 디자인 규칙을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-373">Naming and design conventions for each should be used if you are designing components for use in these frameworks.</span></span> <span data-ttu-id="1c931-374">예를 들어 WPF 프로그래밍의 경우 디자인 중인 클래스에 대해 WPF 디자인 패턴을 채택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-374">For example, for WPF programming, adopt WPF design patterns for the classes you are designing.</span></span> <span data-ttu-id="1c931-375">사용자 인터페이스 프로그래밍의 모델의 경우 이벤트 및 알림 기반 컬렉션과 같은 디자인 패턴 (예:)을 사용 <xref:System.Collections.ObjectModel> 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-375">For models in user interface programming, use design patterns such as events and notification-based collections such as those found in <xref:System.Collections.ObjectModel>.</span></span>

### <a name="object-and-member-design-for-libraries-for-use-from-other-net-languages"></a><span data-ttu-id="1c931-376">개체 및 멤버 디자인 (다른 .NET 언어에서 사용 하는 라이브러리의 경우)</span><span class="sxs-lookup"><span data-stu-id="1c931-376">Object and Member design (for libraries for use from other .NET Languages)</span></span>

#### <a name="use-the-clievent-attribute-to-expose-net-events"></a><span data-ttu-id="1c931-377">CLIEvent 특성을 사용 하 여 .NET 이벤트 노출</span><span class="sxs-lookup"><span data-stu-id="1c931-377">Use the CLIEvent attribute to expose .NET events</span></span>

<span data-ttu-id="1c931-378">`DelegateEvent` `EventArgs` `Event` `FSharpHandler` 이벤트가 다른 .net 언어에 익숙한 방식으로 게시 되도록 개체와 (기본적으로 형식을 사용 하는)를 사용 하는 특정 .net 대리자 형식을 사용 하 여를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-378">Construct a `DelegateEvent` with a specific .NET delegate type that takes an object and `EventArgs` (rather than an `Event`, which just uses the `FSharpHandler` type by default) so that the events are published in the familiar way to other .NET languages.</span></span>

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

#### <a name="expose-asynchronous-operations-as-methods-that-return-net-tasks"></a><span data-ttu-id="1c931-379">.NET 작업을 반환 하는 메서드로 비동기 작업 노출</span><span class="sxs-lookup"><span data-stu-id="1c931-379">Expose asynchronous operations as methods that return .NET tasks</span></span>

<span data-ttu-id="1c931-380">작업은 활성 비동기 계산을 나타내기 위해 .NET에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-380">Tasks are used in .NET to represent active asynchronous computations.</span></span> <span data-ttu-id="1c931-381">작업은 `Async<T>` "이미 실행 중인" 작업을 나타내지만 병렬 컴퍼지션을 수행 하는 방식으로 함께 구성 될 수 없거나 취소 신호 및 기타 컨텍스트 매개 변수의 전파를 숨기 므로 F # 개체 보다 일반적으로 compositional.</span><span class="sxs-lookup"><span data-stu-id="1c931-381">Tasks are in general less compositional than F# `Async<T>` objects, since they represent "already executing" tasks and can't be composed together in ways that perform parallel composition, or which hide the propagation of cancellation signals and other contextual parameters.</span></span>

<span data-ttu-id="1c931-382">그러나이 경우에도 작업을 반환 하는 메서드는 .NET의 비동기 프로그래밍에 대 한 표준 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-382">However, despite this, methods that return Tasks are the standard representation of asynchronous programming on .NET.</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =

    let compute (x: int): Async<int> = async { ... }

    member this.ComputeAsync(x) = compute x |> Async.StartAsTask
```

<span data-ttu-id="1c931-383">또한 명시적 취소 토큰을 허용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-383">You will frequently also want to accept an explicit cancellation token:</span></span>

```fsharp
/// A type in a component designed for use from other .NET languages
type MyType() =
    let compute(x: int): Async<int> = async { ... }
    member this.ComputeAsTask(x, cancellationToken) = Async.StartAsTask(compute x, cancellationToken)
```

#### <a name="use-net-delegate-types-instead-of-f-function-types"></a><span data-ttu-id="1c931-384">F # 함수 형식 대신 .NET 대리자 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-384">Use .NET delegate types instead of F# function types</span></span>

<span data-ttu-id="1c931-385">여기에서 "F # 함수 형식"은와 같은 "화살표" 형식을 의미 `int -> int` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-385">Here "F# function types" mean "arrow" types like `int -> int`.</span></span>

<span data-ttu-id="1c931-386">대신 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-386">Instead of this:</span></span>

```fsharp
member this.Transform(f: int->int) =
    ...
```

<span data-ttu-id="1c931-387">방법:</span><span class="sxs-lookup"><span data-stu-id="1c931-387">Do this:</span></span>

```fsharp
member this.Transform(f: Func<int,int>) =
    ...
```

<span data-ttu-id="1c931-388">F # 함수 형식은 `class FSharpFunc<T,U>` 다른 .net 언어에 표시 되며, 대리자 형식을 이해 하는 언어 기능 및 도구에는 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-388">The F# function type appears as `class FSharpFunc<T,U>` to other .NET languages, and is less suitable for language features and tooling that understands delegate types.</span></span> <span data-ttu-id="1c931-389">.NET Framework 3.5 이상을 대상으로 하는 고차 메서드를 작성 하는 경우, `System.Func` 및 `System.Action` 대리자는 .net 개발자가 이러한 api를 낮은 수준으로 사용할 수 있도록 게시 하는 데 적합 한 api입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-389">When authoring a higher-order method targeting .NET Framework 3.5 or higher, the `System.Func` and `System.Action` delegates are the right APIs to publish to enable .NET developers to consume these APIs in a low-friction manner.</span></span> <span data-ttu-id="1c931-390">.NET Framework 2.0를 대상으로 지정 하는 경우 시스템 정의 대리자 형식이 더 제한적입니다. 또는와 같은 미리 정의 된 대리자 형식을 사용 `System.Converter<T,U>` 하거나 특정 대리자 형식을 정의 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-390">(When targeting .NET Framework 2.0, the system-defined delegate types are more limited; consider using predefined delegate types such as `System.Converter<T,U>` or defining a specific delegate type.)</span></span>

<span data-ttu-id="1c931-391">대칭 이동 측면에서 .NET 대리자는 F # 연결 라이브러리에 대해 자연스럽 게 되지 않습니다 (F # 연결 라이브러리의 다음 섹션 참조).</span><span class="sxs-lookup"><span data-stu-id="1c931-391">On the flip side, .NET delegates are not natural for F#-facing libraries (see the next Section on F#-facing libraries).</span></span> <span data-ttu-id="1c931-392">결과적으로 바닐라 .NET 라이브러리에 대해 고차 메서드를 개발할 때 일반적인 구현 전략은 F # 함수 형식을 사용 하 여 모든 구현을 작성 한 다음 실제 F # 구현에서 가장 왼쪽에 있는 씬 외관으로 대리자를 사용 하 여 공용 API를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-392">As a result, a common implementation strategy when developing higher-order methods for vanilla .NET libraries is to author all the implementation using F# function types, and then create the public API using delegates as a thin façade atop the actual F# implementation.</span></span>

#### <a name="use-the-trygetvalue-pattern-instead-of-returning-f-option-values-and-prefer-method-overloading-to-taking-f-option-values-as-arguments"></a><span data-ttu-id="1c931-393">F # 옵션 값을 반환 하는 대신 TryGetValue 패턴을 사용 하 고 F # 옵션 값을 인수로 사용 하는 메서드 오버 로드를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-393">Use the TryGetValue pattern instead of returning F# option values, and prefer method overloading to taking F# option values as arguments</span></span>

<span data-ttu-id="1c931-394">Api에서 F # 옵션 형식에 대 한 일반적인 사용 패턴은 표준 .NET 디자인 기술을 사용 하 여 바닐라 .NET Api에서 구현 하는 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-394">Common patterns of use for the F# option type in APIs are better implemented in vanilla .NET APIs using standard .NET design techniques.</span></span> <span data-ttu-id="1c931-395">F # 옵션 값을 반환 하는 대신 bool 반환 형식과 out 매개 변수를 "TryGetValue" 패턴과 함께 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-395">Instead of returning an F# option value, consider using the bool return type plus an out parameter as in the "TryGetValue" pattern.</span></span> <span data-ttu-id="1c931-396">F # 옵션 값을 매개 변수로 사용 하는 대신 메서드 오버 로드 또는 선택적 인수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-396">And instead of taking F# option values as parameters, consider using method overloading or optional arguments.</span></span>

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

#### <a name="use-the-net-collection-interface-types-ienumerablet-and-idictionarykeyvalue-for-parameters-and-return-values"></a><span data-ttu-id="1c931-397">.NET 컬렉션 인터페이스 형식 IEnumerable \< T \> 및 IDictionary \< 키, \> 매개 변수 및 반환 값에 대 한 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-397">Use the .NET collection interface types IEnumerable\<T\> and IDictionary\<Key,Value\> for parameters and return values</span></span>

<span data-ttu-id="1c931-398">.NET 배열 `T[]` , F # 형식 `list<T>` , 및와 같은 `Map<Key,Value>` `Set<T>` .net 구체적 컬렉션 형식과 `Dictionary<Key,Value>` 같은 구체적인 컬렉션 형식을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1c931-398">Avoid the use of concrete collection types such as .NET arrays `T[]`, F# types `list<T>`, `Map<Key,Value>` and `Set<T>`, and .NET concrete collection types such as `Dictionary<Key,Value>`.</span></span> <span data-ttu-id="1c931-399">.NET 라이브러리 디자인 지침에는와 같은 다양 한 컬렉션 형식을 사용 해야 하는 경우에 대 한 적절 한 조언이 있습니다 `IEnumerable<T>` .</span><span class="sxs-lookup"><span data-stu-id="1c931-399">The .NET Library Design Guidelines have good advice regarding when to use various collection types like `IEnumerable<T>`.</span></span> <span data-ttu-id="1c931-400">일부 경우에는 성능 grounds 일부 배열 ()을 사용할 `T[]` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-400">Some use of arrays (`T[]`) is acceptable in some circumstances, on performance grounds.</span></span> <span data-ttu-id="1c931-401">특히 `seq<T>` ,에 대 한 F # 별칭입니다 `IEnumerable<T>` . 따라서 seq는 종종 바닐라 .net API에 적합 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-401">Note especially that `seq<T>` is just the F# alias for `IEnumerable<T>`, and thus seq is often an appropriate type for a vanilla .NET API.</span></span>

<span data-ttu-id="1c931-402">F # 목록 대신:</span><span class="sxs-lookup"><span data-stu-id="1c931-402">Instead of F# lists:</span></span>

```fsharp
member this.PrintNames(names: string list) =
    ...
```

<span data-ttu-id="1c931-403">F # 시퀀스 사용:</span><span class="sxs-lookup"><span data-stu-id="1c931-403">Use F# sequences:</span></span>

```fsharp
member this.PrintNames(names: seq<string>) =
    ...
```

#### <a name="use-the-unit-type-as-the-only-input-type-of-a-method-to-define-a-zero-argument-method-or-as-the-only-return-type-to-define-a-void-returning-method"></a><span data-ttu-id="1c931-404">0 인수 메서드를 정의 하는 메서드의 유일한 입력 형식으로 단위 형식을 사용 하거나, void 반환 메서드를 정의 하는 유일한 반환 형식으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-404">Use the unit type as the only input type of a method to define a zero-argument method, or as the only return type to define a void-returning method</span></span>

<span data-ttu-id="1c931-405">단위 형식의 다른 용도를 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-405">Avoid other uses of the unit type.</span></span> <span data-ttu-id="1c931-406">이는 다음과 같이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-406">These are good:</span></span>

```fsharp
✔ member this.NoArguments() = 3

✔ member this.ReturnVoid(x: int) = ()
```

<span data-ttu-id="1c931-407">이것은 잘못 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-407">This is bad:</span></span>

```fsharp
member this.WrongUnit( x: unit, z: int) = ((), ())
```

#### <a name="check-for-null-values-on-vanilla-net-api-boundaries"></a><span data-ttu-id="1c931-408">바닐라 .NET API 경계에서 null 값 확인</span><span class="sxs-lookup"><span data-stu-id="1c931-408">Check for null values on vanilla .NET API boundaries</span></span>

<span data-ttu-id="1c931-409">F # 구현 코드는 변경 불가능 한 디자인 패턴 및 F # 형식에 대 한 null 리터럴 사용에 대 한 제한으로 인해 null 값이 줄어드는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-409">F# implementation code tends to have fewer null values, due to immutable design patterns and restrictions on use of null literals for F# types.</span></span> <span data-ttu-id="1c931-410">다른 .NET 언어에서는 종종 null을 값으로 자주 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-410">Other .NET languages often use null as a value much more frequently.</span></span> <span data-ttu-id="1c931-411">이로 인해 바닐라 .NET API를 노출 하는 F # 코드는 API 경계에서 null에 대 한 매개 변수를 확인 하 고 이러한 값이 F # 구현 코드로 더 심층적으로 이동 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-411">Because of this, F# code that is exposing a vanilla .NET API should check parameters for null at the API boundary, and prevent these values from flowing deeper into the F# implementation code.</span></span> <span data-ttu-id="1c931-412">`isNull`패턴에서 함수 또는 패턴 일치를 `null` 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-412">The `isNull` function or pattern matching on the `null` pattern can be used.</span></span>

```fsharp
let checkNonNull argName (arg: obj) =
    match arg with
    | null -> nullArg argName
    | _ -> ()

let checkNonNull` argName (arg: obj) =
    if isNull arg then nullArg argName
    else ()
```

#### <a name="avoid-using-tuples-as-return-values"></a><span data-ttu-id="1c931-413">튜플을 반환 값으로 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-413">Avoid using tuples as return values</span></span>

<span data-ttu-id="1c931-414">대신 집계 데이터를 포함 하는 명명 된 형식을 반환 하거나 out 매개 변수를 사용 하 여 여러 값을 반환 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-414">Instead, prefer returning a named type holding the aggregate data, or using out parameters to return multiple values.</span></span> <span data-ttu-id="1c931-415">튜플 및 구조체 튜플은 .NET에 존재 하지만 (구조체 튜플에 대 한 c # 언어 지원 포함) .NET 개발자에 게 이상적이 고 예상 되는 API를 제공 하지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-415">Although tuples and struct tuples exist in .NET (including C# language support for struct tuples), they will most often not provide the ideal and expected API for .NET developers.</span></span>

#### <a name="avoid-the-use-of-currying-of-parameters"></a><span data-ttu-id="1c931-416">Currying 매개 변수 사용 방지</span><span class="sxs-lookup"><span data-stu-id="1c931-416">Avoid the use of currying of parameters</span></span>

<span data-ttu-id="1c931-417">대신 .NET 호출 규칙을 사용 `Method(arg1,arg2,…,argN)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-417">Instead, use .NET calling conventions `Method(arg1,arg2,…,argN)`.</span></span>

```fsharp
member this.TupledArguments(str, num) = String.replicate num str
```

<span data-ttu-id="1c931-418">팁: 모든 .NET 언어에서 사용할 수 있도록 라이브러리를 디자인 하는 경우 실제로 이러한 언어에서 "느낌" 라이브러리가 되도록 일부 실험적 c # 및 Visual Basic 프로그래밍을 수행 하는 것은 대체 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-418">Tip: If you're designing libraries for use from any .NET language, then there's no substitute for actually doing some experimental C# and Visual Basic programming to ensure that your libraries "feel right" from these languages.</span></span> <span data-ttu-id="1c931-419">.NET 반영자 및 Visual Studio 개체 브라우저와 같은 도구를 사용 하 여 라이브러리와 해당 설명서가 개발자에 게 예상 대로 표시 되도록 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-419">You can also use tools such as .NET Reflector and the Visual Studio Object Browser to ensure that libraries and their documentation appear as expected to developers.</span></span>

## <a name="appendix"></a><span data-ttu-id="1c931-420">부록</span><span class="sxs-lookup"><span data-stu-id="1c931-420">Appendix</span></span>

### <a name="end-to-end-example-of-designing-f-code-for-use-by-other-net-languages"></a><span data-ttu-id="1c931-421">다른 .NET 언어에서 사용할 F # 코드를 디자인 하는 종단 간 예제</span><span class="sxs-lookup"><span data-stu-id="1c931-421">End-to-end example of designing F# code for use by other .NET languages</span></span>

<span data-ttu-id="1c931-422">다음 클래스를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="1c931-422">Consider the following class:</span></span>

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

<span data-ttu-id="1c931-423">이 클래스의 유추 된 F # 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-423">The inferred F# type of this class is as follows:</span></span>

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

<span data-ttu-id="1c931-424">이 F # 형식이 다른 .NET 언어를 사용 하 여 프로그래머에 게 표시 되는 방식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-424">Let's take a look at how this F# type appears to a programmer using another .NET language.</span></span> <span data-ttu-id="1c931-425">예를 들어 대략적인 c # "signature"는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-425">For example, the approximate C# "signature" is as follows:</span></span>

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

<span data-ttu-id="1c931-426">여기에서 F #이 생성 하는 방법에 대 한 몇 가지 중요 한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-426">There are some important points to notice about how F# represents constructs here.</span></span> <span data-ttu-id="1c931-427">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-427">For example:</span></span>

* <span data-ttu-id="1c931-428">인수 이름과 같은 메타 데이터는 유지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-428">Metadata such as argument names has been preserved.</span></span>

* <span data-ttu-id="1c931-429">두 인수를 사용 하는 F # 메서드는 두 개의 인수를 사용 하는 c # 메서드가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-429">F# methods that take two arguments become C# methods that take two arguments.</span></span>

* <span data-ttu-id="1c931-430">함수 및 목록은 F # 라이브러리의 해당 형식에 대 한 참조가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-430">Functions and lists become references to corresponding types in the F# library.</span></span>

<span data-ttu-id="1c931-431">다음 코드에서는 이러한 항목을 고려 하도록이 코드를 조정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-431">The following code shows how to adjust this code to take these things into account.</span></span>

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

<span data-ttu-id="1c931-432">코드의 유추 된 F # 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-432">The inferred F# type of the code is as follows:</span></span>

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

<span data-ttu-id="1c931-433">이제 c # 시그니처는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-433">The C# signature is now as follows:</span></span>

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

<span data-ttu-id="1c931-434">바닐라 .NET 라이브러리의 일부로 사용 하기 위해이 형식을 준비 하는 수정 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-434">The fixes made to prepare this type for use as part of a vanilla .NET library are as follows:</span></span>

* <span data-ttu-id="1c931-435">,, 및가 각각,, 및로 조정 `Point1` `n` `l` `f` `RadialPoint` `count` `factor` `transform` 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-435">Adjusted several names: `Point1`, `n`, `l`, and `f` became `RadialPoint`, `count`, `factor`, and `transform`, respectively.</span></span>

* <span data-ttu-id="1c931-436">를 사용 하 여에서 `seq<RadialPoint>` `RadialPoint list` 시퀀스 생성으로 목록 생성을 변경 하는 대신의 반환 형식을 사용 `[ ... ]` `IEnumerable<RadialPoint>` 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-436">Used a return type of `seq<RadialPoint>` instead of `RadialPoint list` by changing a list construction using `[ ... ]` to a sequence construction using `IEnumerable<RadialPoint>`.</span></span>

* <span data-ttu-id="1c931-437">`System.Func`F # 함수 형식 대신 .net 대리자 형식을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1c931-437">Used the .NET delegate type `System.Func` instead of an F# function type.</span></span>

<span data-ttu-id="1c931-438">이렇게 하면 c # 코드를 사용 하는 것이 훨씬 더 좋은.</span><span class="sxs-lookup"><span data-stu-id="1c931-438">This makes it far nicer to consume in C# code.</span></span>
