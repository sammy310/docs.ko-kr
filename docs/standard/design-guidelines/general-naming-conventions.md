---
title: 일반 명명 규칙
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], conflicts
- type names, conflicts
- language-specific type names
- names [.NET Framework], about naming guidelines
- names [.NET Framework], abbreviations
- abbreviation naming guidelines
- acronym naming guidelines
- Hungarian notation
- names [.NET Framework], type names
- names [.NET Framework], acronyms
ms.assetid: d3a77ea1-75d2-4969-a8c3-3e1e3e1aaedc
ms.openlocfilehash: ef4a8f571a67477739bbc59d3103ba78dea47177
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635913"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="ac159-102">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="ac159-102">General Naming Conventions</span></span>

<span data-ttu-id="ac159-103">이 섹션에서는 단어 선택과 관련된 일반적인 명명 규칙, 약어 및 머리글자어 사용에 대한 지침 및 언어별 이름을 사용하지 않는 방법에 대한 권장 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>

## <a name="word-choice"></a><span data-ttu-id="ac159-104">단어 선택</span><span class="sxs-lookup"><span data-stu-id="ac159-104">Word Choice</span></span>
 <span data-ttu-id="ac159-105">✔️ 쉽게 읽을 수 있는 식별자 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-105">✔️ DO choose easily readable identifier names.</span></span>

 <span data-ttu-id="ac159-106">예를 들어 명명된 `HorizontalAlignment` 속성은 에 보다 `AlignmentHorizontal`영어읽기가 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>

 <span data-ttu-id="ac159-107">✔️ 간결성보다 가독성을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-107">✔️ DO favor readability over brevity.</span></span>

 <span data-ttu-id="ac159-108">속성 이름은 `CanScrollHorizontally` (X `ScrollableX` 축에 대한 모호한 참조)보다 낫습니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>

 <span data-ttu-id="ac159-109">❌밑줄, 하이픈 또는 기타 알파인이 아닌 문자를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-109">❌ DO NOT use underscores, hyphens, or any other nonalphanumeric characters.</span></span>

 <span data-ttu-id="ac159-110">❌헝가리어 표기는 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-110">❌ DO NOT use Hungarian notation.</span></span>

 <span data-ttu-id="ac159-111">❌널리 사용되는 프로그래밍 언어의 키워드와 충돌하는 식별자를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-111">❌ AVOID using identifiers that conflict with keywords of widely used programming languages.</span></span>

 <span data-ttu-id="ac159-112">공통 언어 사양(CLS)의 규칙 4에 따라 모든 호환 언어는 해당 언어의 키워드를 식별자로 사용하는 명명된 항목에 대한 액세스를 허용하는 메커니즘을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="ac159-113">예를 들어 C#은 이 경우 @ 기호를 이스케이프 메커니즘으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="ac159-114">그러나 이스케이프 시퀀스가 없는 키워드보다 이스케이프 시퀀스를 사용하는 것이 훨씬 어렵기 때문에 일반적인 키워드를 사용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>

## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="ac159-115">약어 및 약어 사용</span><span class="sxs-lookup"><span data-stu-id="ac159-115">Using Abbreviations and Acronyms</span></span>
 <span data-ttu-id="ac159-116">❌식별자 이름의 일부로 약어 나 수축을 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-116">❌ DO NOT use abbreviations or contractions as part of identifier names.</span></span>

 <span data-ttu-id="ac159-117">예를 `GetWin`들어. `GetWindow`</span><span class="sxs-lookup"><span data-stu-id="ac159-117">For example, use `GetWindow` rather than `GetWin`.</span></span>

 <span data-ttu-id="ac159-118">❌널리 받아들여지지 않는 약어는 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-118">❌ DO NOT use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>

## <a name="avoiding-language-specific-names"></a><span data-ttu-id="ac159-119">언어별 이름 피하기</span><span class="sxs-lookup"><span data-stu-id="ac159-119">Avoiding Language-Specific Names</span></span>
 <span data-ttu-id="ac159-120">✔️ do do는 형식 이름에 대한 언어별 키워드보다는 중요한 용도로 흥미로운 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-120">✔️ DO use semantically interesting names rather than language-specific keywords for type names.</span></span>

 <span data-ttu-id="ac159-121">예를 들어, `GetLength` 보다 더 `GetInt`나은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-121">For example, `GetLength` is a better name than `GetInt`.</span></span>

 <span data-ttu-id="ac159-122">✔️ 식별자가 해당 형식 이외의 의미 체계 의미가 없는 경우 드물게 언어별 이름이 아닌 제네릭 CLR 형식 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-122">✔️ DO use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>

 <span data-ttu-id="ac159-123">예를 <xref:System.Int64> 들어 변환하는 메서드는 `ToInt64`이름이 아니라(C#특정 `ToLong` 별칭의 <xref:System.Int64> `long`CLR 이름이기 때문).</span><span class="sxs-lookup"><span data-stu-id="ac159-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="ac159-124">다음 표에서는 CLR 형식 이름(C#, Visual Basic 및 C++)에 해당하는 형식 이름뿐만 아니라 CLR 형식 이름을 사용하는 여러 기본 데이터 형식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>

|<span data-ttu-id="ac159-125">C#</span><span class="sxs-lookup"><span data-stu-id="ac159-125">C#</span></span>|<span data-ttu-id="ac159-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ac159-126">Visual Basic</span></span>|<span data-ttu-id="ac159-127">C++</span><span class="sxs-lookup"><span data-stu-id="ac159-127">C++</span></span>|<span data-ttu-id="ac159-128">CLR</span><span class="sxs-lookup"><span data-stu-id="ac159-128">CLR</span></span>|
|---------|------------------|-----------|---------|
|<span data-ttu-id="ac159-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="ac159-129">**sbyte**</span></span>|<span data-ttu-id="ac159-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="ac159-130">**SByte**</span></span>|<span data-ttu-id="ac159-131">**char**</span><span class="sxs-lookup"><span data-stu-id="ac159-131">**char**</span></span>|<span data-ttu-id="ac159-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="ac159-132">**SByte**</span></span>|
|<span data-ttu-id="ac159-133">**바이트**</span><span class="sxs-lookup"><span data-stu-id="ac159-133">**byte**</span></span>|<span data-ttu-id="ac159-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="ac159-134">**Byte**</span></span>|<span data-ttu-id="ac159-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="ac159-135">**unsigned char**</span></span>|<span data-ttu-id="ac159-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="ac159-136">**Byte**</span></span>|
|<span data-ttu-id="ac159-137">**short**</span><span class="sxs-lookup"><span data-stu-id="ac159-137">**short**</span></span>|<span data-ttu-id="ac159-138">**짧은**</span><span class="sxs-lookup"><span data-stu-id="ac159-138">**Short**</span></span>|<span data-ttu-id="ac159-139">**short**</span><span class="sxs-lookup"><span data-stu-id="ac159-139">**short**</span></span>|<span data-ttu-id="ac159-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="ac159-140">**Int16**</span></span>|
|<span data-ttu-id="ac159-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="ac159-141">**ushort**</span></span>|<span data-ttu-id="ac159-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="ac159-142">**UInt16**</span></span>|<span data-ttu-id="ac159-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="ac159-143">**unsigned short**</span></span>|<span data-ttu-id="ac159-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="ac159-144">**UInt16**</span></span>|
|<span data-ttu-id="ac159-145">**Int**</span><span class="sxs-lookup"><span data-stu-id="ac159-145">**int**</span></span>|<span data-ttu-id="ac159-146">**정수**</span><span class="sxs-lookup"><span data-stu-id="ac159-146">**Integer**</span></span>|<span data-ttu-id="ac159-147">**Int**</span><span class="sxs-lookup"><span data-stu-id="ac159-147">**int**</span></span>|<span data-ttu-id="ac159-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="ac159-148">**Int32**</span></span>|
|<span data-ttu-id="ac159-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="ac159-149">**uint**</span></span>|<span data-ttu-id="ac159-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="ac159-150">**UInt32**</span></span>|<span data-ttu-id="ac159-151">**부호 없는 정수**</span><span class="sxs-lookup"><span data-stu-id="ac159-151">**unsigned int**</span></span>|<span data-ttu-id="ac159-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="ac159-152">**UInt32**</span></span>|
|<span data-ttu-id="ac159-153">**긴**</span><span class="sxs-lookup"><span data-stu-id="ac159-153">**long**</span></span>|<span data-ttu-id="ac159-154">**긴**</span><span class="sxs-lookup"><span data-stu-id="ac159-154">**Long**</span></span>|<span data-ttu-id="ac159-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="ac159-155">**__int64**</span></span>|<span data-ttu-id="ac159-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="ac159-156">**Int64**</span></span>|
|<span data-ttu-id="ac159-157">**Ulong**</span><span class="sxs-lookup"><span data-stu-id="ac159-157">**ulong**</span></span>|<span data-ttu-id="ac159-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="ac159-158">**UInt64**</span></span>|<span data-ttu-id="ac159-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="ac159-159">**unsigned __int64**</span></span>|<span data-ttu-id="ac159-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="ac159-160">**UInt64**</span></span>|
|<span data-ttu-id="ac159-161">**플 로트**</span><span class="sxs-lookup"><span data-stu-id="ac159-161">**float**</span></span>|<span data-ttu-id="ac159-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="ac159-162">**Single**</span></span>|<span data-ttu-id="ac159-163">**플 로트**</span><span class="sxs-lookup"><span data-stu-id="ac159-163">**float**</span></span>|<span data-ttu-id="ac159-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="ac159-164">**Single**</span></span>|
|<span data-ttu-id="ac159-165">**double**</span><span class="sxs-lookup"><span data-stu-id="ac159-165">**double**</span></span>|<span data-ttu-id="ac159-166">**double**</span><span class="sxs-lookup"><span data-stu-id="ac159-166">**Double**</span></span>|<span data-ttu-id="ac159-167">**double**</span><span class="sxs-lookup"><span data-stu-id="ac159-167">**double**</span></span>|<span data-ttu-id="ac159-168">**double**</span><span class="sxs-lookup"><span data-stu-id="ac159-168">**Double**</span></span>|
|<span data-ttu-id="ac159-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="ac159-169">**bool**</span></span>|<span data-ttu-id="ac159-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="ac159-170">**Boolean**</span></span>|<span data-ttu-id="ac159-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="ac159-171">**bool**</span></span>|<span data-ttu-id="ac159-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="ac159-172">**Boolean**</span></span>|
|<span data-ttu-id="ac159-173">**char**</span><span class="sxs-lookup"><span data-stu-id="ac159-173">**char**</span></span>|<span data-ttu-id="ac159-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="ac159-174">**Char**</span></span>|<span data-ttu-id="ac159-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="ac159-175">**wchar_t**</span></span>|<span data-ttu-id="ac159-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="ac159-176">**Char**</span></span>|
|<span data-ttu-id="ac159-177">**string**</span><span class="sxs-lookup"><span data-stu-id="ac159-177">**string**</span></span>|<span data-ttu-id="ac159-178">**String**</span><span class="sxs-lookup"><span data-stu-id="ac159-178">**String**</span></span>|<span data-ttu-id="ac159-179">**String**</span><span class="sxs-lookup"><span data-stu-id="ac159-179">**String**</span></span>|<span data-ttu-id="ac159-180">**String**</span><span class="sxs-lookup"><span data-stu-id="ac159-180">**String**</span></span>|
|<span data-ttu-id="ac159-181">**개체**</span><span class="sxs-lookup"><span data-stu-id="ac159-181">**object**</span></span>|<span data-ttu-id="ac159-182">**Object**</span><span class="sxs-lookup"><span data-stu-id="ac159-182">**Object**</span></span>|<span data-ttu-id="ac159-183">**Object**</span><span class="sxs-lookup"><span data-stu-id="ac159-183">**Object**</span></span>|<span data-ttu-id="ac159-184">**Object**</span><span class="sxs-lookup"><span data-stu-id="ac159-184">**Object**</span></span>|

 <span data-ttu-id="ac159-185">✔️ 식별자가 의미 체계 `value` 의미가 `item`없고 매개 변수의 형식이 중요하지 않은 경우 드물게 형식 이름을 반복하는 대신 또는 또는 와 같은 공통 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-185">✔️ DO  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>

## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="ac159-186">기존 API의 새 버전 이름 지정</span><span class="sxs-lookup"><span data-stu-id="ac159-186">Naming New Versions of Existing APIs</span></span>
 <span data-ttu-id="ac159-187">✔️ 기존 API의 새 버전을 만들 때 이전 API와 유사한 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-187">✔️ DO use a name similar to the old API when creating new versions of an existing API.</span></span>

 <span data-ttu-id="ac159-188">이렇게 하면 API 간의 관계를 강조 표시하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-188">This helps to highlight the relationship between the APIs.</span></span>

 <span data-ttu-id="ac159-189">✔️ 기존 API의 새 버전을 나타내는 접두사 보다는 접미사를 추가하는 것을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-189">✔️ DO prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>

 <span data-ttu-id="ac159-190">이렇게 하면 문서를 검색하거나 IntelliSense를 사용할 때 검색에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="ac159-191">대부분의 브라우저와 IntelliSense는 알파벳 순으로 식별자를 표시하기 때문에 API의 이전 버전은 새 API에 가깝게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>

 <span data-ttu-id="ac159-192">✔️ 접미사 나 접두사를 추가하는 대신 새롭지만 의미있는 식별자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-192">✔️ CONSIDER using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>

 <span data-ttu-id="ac159-193">✔️ 숫자 접미사를 사용하여 기존 API의 새 버전을 나타내는데, 특히 API의 기존 이름이 의미 있는 유일한 이름(예: 산업 표준인 경우)이고 의미 있는 접미사를 추가하거나 이름을 변경하는 것이 적절한 옵션이 아닌 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-193">✔️ DO use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>

 <span data-ttu-id="ac159-194">❌식별자가 동일한 API의 이전 버전과 구별하기 위해 "Ex" (또는 이와 유사한) 접미사를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-194">❌ DO NOT use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>

 <span data-ttu-id="ac159-195">✔️ 32비트 정수 대신 64비트 정수(긴 정수)에서 작동하는 API 버전을 도입할 때 "64" 접미사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac159-195">✔️ DO use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="ac159-196">기존 32비트 API가 있는 경우에만 이 방법을 사용하면 됩니다. 64비트 버전만 있는 새로운 API에는 이러한 작업을 수행하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ac159-196">You only need to take this approach when the existing 32-bit API exists; don't do it for brand new APIs with only a 64-bit version.</span></span>

 <span data-ttu-id="ac159-197">*&copy; 2005년, 2009년 마이크로소프트. 판권.*</span><span class="sxs-lookup"><span data-stu-id="ac159-197">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="ac159-198">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="ac159-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="ac159-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac159-199">See also</span></span>

- [<span data-ttu-id="ac159-200">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ac159-200">Framework design guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="ac159-201">명명 지침</span><span class="sxs-lookup"><span data-stu-id="ac159-201">Naming guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
- [<span data-ttu-id="ac159-202">EditorConfig에 대한 .NET 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="ac159-202">.NET naming conventions for EditorConfig</span></span>](/visualstudio/ide/editorconfig-naming-conventions)
