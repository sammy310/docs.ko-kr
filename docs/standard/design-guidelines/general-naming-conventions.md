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
ms.openlocfilehash: c90987fd28d5157cfb7f7eea4680b5ab4be1a200
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290956"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="b390f-102">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="b390f-102">General Naming Conventions</span></span>

<span data-ttu-id="b390f-103">이 섹션에서는 단어 선택, 약어 및 머리글자어 사용에 대 한 지침, 언어별 이름 사용을 방지 하는 방법에 대 한 권장 사항을 설명 하는 일반적인 명명 규칙을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>

## <a name="word-choice"></a><span data-ttu-id="b390f-104">단어 선택</span><span class="sxs-lookup"><span data-stu-id="b390f-104">Word Choice</span></span>
 <span data-ttu-id="b390f-105">쉽게 읽을 수 있는 식별자 이름을 선택 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-105">✔️ DO choose easily readable identifier names.</span></span>

 <span data-ttu-id="b390f-106">예를 들어 라는 속성 `HorizontalAlignment` 은 보다 영어에서 읽을 수 `AlignmentHorizontal` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>

 <span data-ttu-id="b390f-107">✔️를 통해 보다 쉽게 이해할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-107">✔️ DO favor readability over brevity.</span></span>

 <span data-ttu-id="b390f-108">속성 이름이 `CanScrollHorizontally` `ScrollableX` (X 축에 대 한 모호한 참조) 보다 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>

 <span data-ttu-id="b390f-109">❌밑줄, 하이픈 또는 다른 영숫자가 아닌 문자를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b390f-109">❌ DO NOT use underscores, hyphens, or any other nonalphanumeric characters.</span></span>

 <span data-ttu-id="b390f-110">❌헝가리어 표기법은 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b390f-110">❌ DO NOT use Hungarian notation.</span></span>

 <span data-ttu-id="b390f-111">❌널리 사용 되는 프로그래밍 언어의 키워드와 충돌 하는 식별자를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b390f-111">❌ AVOID using identifiers that conflict with keywords of widely used programming languages.</span></span>

 <span data-ttu-id="b390f-112">CLS (공용 언어 사양)의 규칙 4에 따라 모든 규격 언어는 해당 언어의 키워드를 식별자로 사용 하는 명명 된 항목에 대 한 액세스를 허용 하는 메커니즘을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="b390f-113">예를 들어 c #에서는이 경우 이스케이프 메커니즘으로 @ 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="b390f-114">그러나 이스케이프 시퀀스가 없는 메서드를 사용 하는 것은 훨씬 더 어렵기 때문에 일반적인 키워드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>

## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="b390f-115">약어 및 머리글자어 사용</span><span class="sxs-lookup"><span data-stu-id="b390f-115">Using Abbreviations and Acronyms</span></span>
 <span data-ttu-id="b390f-116">❌식별자 이름의 일부로 약어 또는 축약를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b390f-116">❌ DO NOT use abbreviations or contractions as part of identifier names.</span></span>

 <span data-ttu-id="b390f-117">예를 들어 대신를 사용 `GetWindow` `GetWin` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-117">For example, use `GetWindow` rather than `GetWin`.</span></span>

 <span data-ttu-id="b390f-118">❌광범위 하 게 허용 되지 않는 머리글자어를 사용 하 고, 필요한 경우에만 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b390f-118">❌ DO NOT use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>

## <a name="avoiding-language-specific-names"></a><span data-ttu-id="b390f-119">언어별 이름 방지</span><span class="sxs-lookup"><span data-stu-id="b390f-119">Avoiding Language-Specific Names</span></span>
 <span data-ttu-id="b390f-120">✔️ 형식 이름에 대해 언어별 키워드 대신 의미 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-120">✔️ DO use semantically interesting names rather than language-specific keywords for type names.</span></span>

 <span data-ttu-id="b390f-121">예를 들어 `GetLength` 는 보다 더 나은 이름입니다 `GetInt` .</span><span class="sxs-lookup"><span data-stu-id="b390f-121">For example, `GetLength` is a better name than `GetInt`.</span></span>

 <span data-ttu-id="b390f-122">드문 경우 이지만 식별자에 형식 이외의 의미 체계가 없는 경우에는 언어별 이름이 아니라 제네릭 CLR 형식 이름을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-122">✔️ DO use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>

 <span data-ttu-id="b390f-123">예를 들어를로 변환 하는 메서드는 <xref:System.Int64> `ToInt64` `ToLong` ( <xref:System.Int64> c # 관련 별칭의 CLR 이름)이 아니라로 명명 되어야 합니다 `long` .</span><span class="sxs-lookup"><span data-stu-id="b390f-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="b390f-124">다음 표에서는 CLR 형식 이름 뿐만 아니라 c #, Visual Basic 및 c + +에 해당 하는 형식 이름을 사용 하는 여러 기본 데이터 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>

|<span data-ttu-id="b390f-125">C#</span><span class="sxs-lookup"><span data-stu-id="b390f-125">C#</span></span>|<span data-ttu-id="b390f-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b390f-126">Visual Basic</span></span>|<span data-ttu-id="b390f-127">C++</span><span class="sxs-lookup"><span data-stu-id="b390f-127">C++</span></span>|<span data-ttu-id="b390f-128">CLR</span><span class="sxs-lookup"><span data-stu-id="b390f-128">CLR</span></span>|
|---------|------------------|-----------|---------|
|<span data-ttu-id="b390f-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="b390f-129">**sbyte**</span></span>|<span data-ttu-id="b390f-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="b390f-130">**SByte**</span></span>|<span data-ttu-id="b390f-131">**char**</span><span class="sxs-lookup"><span data-stu-id="b390f-131">**char**</span></span>|<span data-ttu-id="b390f-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="b390f-132">**SByte**</span></span>|
|<span data-ttu-id="b390f-133">**바이트**</span><span class="sxs-lookup"><span data-stu-id="b390f-133">**byte**</span></span>|<span data-ttu-id="b390f-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="b390f-134">**Byte**</span></span>|<span data-ttu-id="b390f-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="b390f-135">**unsigned char**</span></span>|<span data-ttu-id="b390f-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="b390f-136">**Byte**</span></span>|
|<span data-ttu-id="b390f-137">**short**</span><span class="sxs-lookup"><span data-stu-id="b390f-137">**short**</span></span>|<span data-ttu-id="b390f-138">**간략히**</span><span class="sxs-lookup"><span data-stu-id="b390f-138">**Short**</span></span>|<span data-ttu-id="b390f-139">**short**</span><span class="sxs-lookup"><span data-stu-id="b390f-139">**short**</span></span>|<span data-ttu-id="b390f-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="b390f-140">**Int16**</span></span>|
|<span data-ttu-id="b390f-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="b390f-141">**ushort**</span></span>|<span data-ttu-id="b390f-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="b390f-142">**UInt16**</span></span>|<span data-ttu-id="b390f-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="b390f-143">**unsigned short**</span></span>|<span data-ttu-id="b390f-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="b390f-144">**UInt16**</span></span>|
|<span data-ttu-id="b390f-145">**int**</span><span class="sxs-lookup"><span data-stu-id="b390f-145">**int**</span></span>|<span data-ttu-id="b390f-146">**값**</span><span class="sxs-lookup"><span data-stu-id="b390f-146">**Integer**</span></span>|<span data-ttu-id="b390f-147">**int**</span><span class="sxs-lookup"><span data-stu-id="b390f-147">**int**</span></span>|<span data-ttu-id="b390f-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="b390f-148">**Int32**</span></span>|
|<span data-ttu-id="b390f-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="b390f-149">**uint**</span></span>|<span data-ttu-id="b390f-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="b390f-150">**UInt32**</span></span>|<span data-ttu-id="b390f-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="b390f-151">**unsigned int**</span></span>|<span data-ttu-id="b390f-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="b390f-152">**UInt32**</span></span>|
|<span data-ttu-id="b390f-153">**long**</span><span class="sxs-lookup"><span data-stu-id="b390f-153">**long**</span></span>|<span data-ttu-id="b390f-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="b390f-154">**Long**</span></span>|<span data-ttu-id="b390f-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="b390f-155">**__int64**</span></span>|<span data-ttu-id="b390f-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="b390f-156">**Int64**</span></span>|
|<span data-ttu-id="b390f-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="b390f-157">**ulong**</span></span>|<span data-ttu-id="b390f-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="b390f-158">**UInt64**</span></span>|<span data-ttu-id="b390f-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="b390f-159">**unsigned __int64**</span></span>|<span data-ttu-id="b390f-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="b390f-160">**UInt64**</span></span>|
|<span data-ttu-id="b390f-161">**float**</span><span class="sxs-lookup"><span data-stu-id="b390f-161">**float**</span></span>|<span data-ttu-id="b390f-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="b390f-162">**Single**</span></span>|<span data-ttu-id="b390f-163">**float**</span><span class="sxs-lookup"><span data-stu-id="b390f-163">**float**</span></span>|<span data-ttu-id="b390f-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="b390f-164">**Single**</span></span>|
|<span data-ttu-id="b390f-165">**double**</span><span class="sxs-lookup"><span data-stu-id="b390f-165">**double**</span></span>|<span data-ttu-id="b390f-166">**double**</span><span class="sxs-lookup"><span data-stu-id="b390f-166">**Double**</span></span>|<span data-ttu-id="b390f-167">**double**</span><span class="sxs-lookup"><span data-stu-id="b390f-167">**double**</span></span>|<span data-ttu-id="b390f-168">**double**</span><span class="sxs-lookup"><span data-stu-id="b390f-168">**Double**</span></span>|
|<span data-ttu-id="b390f-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="b390f-169">**bool**</span></span>|<span data-ttu-id="b390f-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="b390f-170">**Boolean**</span></span>|<span data-ttu-id="b390f-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="b390f-171">**bool**</span></span>|<span data-ttu-id="b390f-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="b390f-172">**Boolean**</span></span>|
|<span data-ttu-id="b390f-173">**char**</span><span class="sxs-lookup"><span data-stu-id="b390f-173">**char**</span></span>|<span data-ttu-id="b390f-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="b390f-174">**Char**</span></span>|<span data-ttu-id="b390f-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="b390f-175">**wchar_t**</span></span>|<span data-ttu-id="b390f-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="b390f-176">**Char**</span></span>|
|<span data-ttu-id="b390f-177">**string**</span><span class="sxs-lookup"><span data-stu-id="b390f-177">**string**</span></span>|<span data-ttu-id="b390f-178">**String**</span><span class="sxs-lookup"><span data-stu-id="b390f-178">**String**</span></span>|<span data-ttu-id="b390f-179">**String**</span><span class="sxs-lookup"><span data-stu-id="b390f-179">**String**</span></span>|<span data-ttu-id="b390f-180">**String**</span><span class="sxs-lookup"><span data-stu-id="b390f-180">**String**</span></span>|
|<span data-ttu-id="b390f-181">**object**</span><span class="sxs-lookup"><span data-stu-id="b390f-181">**object**</span></span>|<span data-ttu-id="b390f-182">**Object**</span><span class="sxs-lookup"><span data-stu-id="b390f-182">**Object**</span></span>|<span data-ttu-id="b390f-183">**Object**</span><span class="sxs-lookup"><span data-stu-id="b390f-183">**Object**</span></span>|<span data-ttu-id="b390f-184">**Object**</span><span class="sxs-lookup"><span data-stu-id="b390f-184">**Object**</span></span>|

 <span data-ttu-id="b390f-185">`value` `item` 드문 경우 이지만 식별자에 의미 체계가 없고 매개 변수의 형식이 중요 하지 않은 경우에는 형식 이름을 반복 하는 대신 또는와 같은 일반 이름을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-185">✔️ DO  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>

## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="b390f-186">새 버전의 기존 Api 이름 지정</span><span class="sxs-lookup"><span data-stu-id="b390f-186">Naming New Versions of Existing APIs</span></span>
 <span data-ttu-id="b390f-187">기존 api의 새 버전을 만들 때 이전 API와 유사한 이름을 사용 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-187">✔️ DO use a name similar to the old API when creating new versions of an existing API.</span></span>

 <span data-ttu-id="b390f-188">이렇게 하면 Api 간의 관계를 강조 표시 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-188">This helps to highlight the relationship between the APIs.</span></span>

 <span data-ttu-id="b390f-189">기존 API의 새 버전을 나타내기 위해 접두사 대신 접미사를 추가 하는 것이 좋습니다 ✔️.</span><span class="sxs-lookup"><span data-stu-id="b390f-189">✔️ DO prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>

 <span data-ttu-id="b390f-190">그러면 설명서를 찾아보거나 IntelliSense를 사용 하 여 검색을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="b390f-191">대부분의 브라우저와 IntelliSense는 식별자를 사전순으로 표시 하기 때문에 이전 버전의 API는 새 Api와 거의 유사 하 게 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>

 <span data-ttu-id="b390f-192">✔️ 접미사 또는 접두사를 추가 하는 대신 새로운 브랜드의 의미 있는 식별자를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-192">✔️ CONSIDER using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>

 <span data-ttu-id="b390f-193">기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다. 특히 API의 기존 이름이 적절 한 이름 (예: 업계 표준) 인 경우에는 의미 있는 접미사를 추가 하거나 이름을 변경 하는 것이 적절 한 옵션이 아닌 경우에 ✔️ 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-193">✔️ DO use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>

 <span data-ttu-id="b390f-194">❌식별자에 대해 "Ex" (또는 이와 유사한) 접미사를 사용 하 여 동일한 API의 이전 버전과 구별 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b390f-194">❌ DO NOT use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>

 <span data-ttu-id="b390f-195">✔️ 32 비트 정수 대신 64 비트 정수 (long 정수)에서 작동 하는 Api 버전을 도입할 때 "64" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b390f-195">✔️ DO use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="b390f-196">기존 32 비트 API가 있는 경우에만이 방법을 사용 해야 합니다. 64 비트 버전만 사용 하는 새로운 Api에 대해서는이 작업을 수행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b390f-196">You only need to take this approach when the existing 32-bit API exists; don't do it for brand new APIs with only a 64-bit version.</span></span>

 <span data-ttu-id="b390f-197">*&copy;2005 부분, 2009 Microsoft Corporation. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="b390f-197">*Portions &copy; 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="b390f-198">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="b390f-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="b390f-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b390f-199">See also</span></span>

- [<span data-ttu-id="b390f-200">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b390f-200">Framework design guidelines</span></span>](index.md)
- [<span data-ttu-id="b390f-201">명명 지침</span><span class="sxs-lookup"><span data-stu-id="b390f-201">Naming guidelines</span></span>](naming-guidelines.md)
- [<span data-ttu-id="b390f-202">EditorConfig에 대한 .NET 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="b390f-202">.NET naming conventions for EditorConfig</span></span>](/visualstudio/ide/editorconfig-naming-conventions)
