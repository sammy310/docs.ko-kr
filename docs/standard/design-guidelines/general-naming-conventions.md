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
ms.openlocfilehash: d1b01fac7368ffeceb554c6f12aecb8f8760fa1d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709337"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="5bd14-102">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="5bd14-102">General Naming Conventions</span></span>
<span data-ttu-id="5bd14-103">이 섹션에서는 단어 선택, 약어 및 머리글자어 사용에 대 한 지침, 언어별 이름 사용을 방지 하는 방법에 대 한 권장 사항을 설명 하는 일반적인 명명 규칙을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="5bd14-104">단어 선택</span><span class="sxs-lookup"><span data-stu-id="5bd14-104">Word Choice</span></span>  
 <span data-ttu-id="5bd14-105">**✓ DO** 쉽게 읽을 수 있는 식별자 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="5bd14-106">예를 들어 `HorizontalAlignment` 라는 속성은 `AlignmentHorizontal`보다 영어를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="5bd14-107">**✓ DO** 가독성 간결한 설명을 위해 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="5bd14-108">속성 이름 `CanScrollHorizontally` `ScrollableX` (X-축에 대 한 모호한 참조) 보다 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="5bd14-109">**X DO NOT** 밑줄, 하이픈 또는 기타 영숫자가 아닌 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="5bd14-110">**X DO NOT** 헝가리 식 표기법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="5bd14-111">**X AVOID** 널리의 키워드와 충돌 하는 식별자를 사용 하 여 프로그래밍 언어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="5bd14-112">CLS (공용 언어 사양)의 규칙 4에 따라 모든 규격 언어는 해당 언어의 키워드를 식별자로 사용 하는 명명 된 항목에 대 한 액세스를 허용 하는 메커니즘을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="5bd14-113">C#예를 들어은이 경우 이스케이프 메커니즘으로 @ 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="5bd14-114">그러나 이스케이프 시퀀스가 없는 메서드를 사용 하는 것은 훨씬 더 어렵기 때문에 일반적인 키워드를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="5bd14-115">약어 및 머리글자어 사용</span><span class="sxs-lookup"><span data-stu-id="5bd14-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="5bd14-116">**X DO NOT** 식별자 이름의 일부로 약어 또는 축약을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="5bd14-117">예를 들어 `GetWin`대신 `GetWindow`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="5bd14-118">**X DO NOT** 폭넓게 활용 되 고 필요한 경우에 있는 경우에 하지 않은 머리글자어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="5bd14-119">언어별 이름 방지</span><span class="sxs-lookup"><span data-stu-id="5bd14-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="5bd14-120">**✓ DO** 형식 이름에 대 한 언어별 키워드 보다는 특별 한 의미가 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="5bd14-121">예를 들어 `GetLength`은 `GetInt`보다 더 나은 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="5bd14-122">**✓ DO** 드문 경우 식별자 의미가 없는 해당 형식 이상의 때의 언어 관련 이름 대신 일반 CLR 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="5bd14-123">예를 들어 <xref:System.Int64>로 변환 하는 메서드는 `ToLong` 아닌 `ToInt64`이름이 지정 되어야 합니다 (<xref:System.Int64>는 특정 별칭 `long`에 C#대 한 CLR 이름).</span><span class="sxs-lookup"><span data-stu-id="5bd14-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="5bd14-124">다음 표에서는 CLR 형식 이름 및, Visual Basic 및 C# C++의 해당 형식 이름을 사용 하는 여러 가지 기본 데이터 형식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="5bd14-125">C#</span><span class="sxs-lookup"><span data-stu-id="5bd14-125">C#</span></span>|<span data-ttu-id="5bd14-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5bd14-126">Visual Basic</span></span>|<span data-ttu-id="5bd14-127">C++</span><span class="sxs-lookup"><span data-stu-id="5bd14-127">C++</span></span>|<span data-ttu-id="5bd14-128">CLR</span><span class="sxs-lookup"><span data-stu-id="5bd14-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="5bd14-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="5bd14-129">**sbyte**</span></span>|<span data-ttu-id="5bd14-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="5bd14-130">**SByte**</span></span>|<span data-ttu-id="5bd14-131">**char**</span><span class="sxs-lookup"><span data-stu-id="5bd14-131">**char**</span></span>|<span data-ttu-id="5bd14-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="5bd14-132">**SByte**</span></span>|  
|<span data-ttu-id="5bd14-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="5bd14-133">**byte**</span></span>|<span data-ttu-id="5bd14-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="5bd14-134">**Byte**</span></span>|<span data-ttu-id="5bd14-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="5bd14-135">**unsigned char**</span></span>|<span data-ttu-id="5bd14-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="5bd14-136">**Byte**</span></span>|  
|<span data-ttu-id="5bd14-137">**short**</span><span class="sxs-lookup"><span data-stu-id="5bd14-137">**short**</span></span>|<span data-ttu-id="5bd14-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="5bd14-138">**Short**</span></span>|<span data-ttu-id="5bd14-139">**short**</span><span class="sxs-lookup"><span data-stu-id="5bd14-139">**short**</span></span>|<span data-ttu-id="5bd14-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="5bd14-140">**Int16**</span></span>|  
|<span data-ttu-id="5bd14-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="5bd14-141">**ushort**</span></span>|<span data-ttu-id="5bd14-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="5bd14-142">**UInt16**</span></span>|<span data-ttu-id="5bd14-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="5bd14-143">**unsigned short**</span></span>|<span data-ttu-id="5bd14-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="5bd14-144">**UInt16**</span></span>|  
|<span data-ttu-id="5bd14-145">**int**</span><span class="sxs-lookup"><span data-stu-id="5bd14-145">**int**</span></span>|<span data-ttu-id="5bd14-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="5bd14-146">**Integer**</span></span>|<span data-ttu-id="5bd14-147">**int**</span><span class="sxs-lookup"><span data-stu-id="5bd14-147">**int**</span></span>|<span data-ttu-id="5bd14-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="5bd14-148">**Int32**</span></span>|  
|<span data-ttu-id="5bd14-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="5bd14-149">**uint**</span></span>|<span data-ttu-id="5bd14-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="5bd14-150">**UInt32**</span></span>|<span data-ttu-id="5bd14-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="5bd14-151">**unsigned int**</span></span>|<span data-ttu-id="5bd14-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="5bd14-152">**UInt32**</span></span>|  
|<span data-ttu-id="5bd14-153">**long**</span><span class="sxs-lookup"><span data-stu-id="5bd14-153">**long**</span></span>|<span data-ttu-id="5bd14-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="5bd14-154">**Long**</span></span>|<span data-ttu-id="5bd14-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="5bd14-155">**__int64**</span></span>|<span data-ttu-id="5bd14-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="5bd14-156">**Int64**</span></span>|  
|<span data-ttu-id="5bd14-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="5bd14-157">**ulong**</span></span>|<span data-ttu-id="5bd14-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="5bd14-158">**UInt64**</span></span>|<span data-ttu-id="5bd14-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="5bd14-159">**unsigned __int64**</span></span>|<span data-ttu-id="5bd14-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="5bd14-160">**UInt64**</span></span>|  
|<span data-ttu-id="5bd14-161">**float**</span><span class="sxs-lookup"><span data-stu-id="5bd14-161">**float**</span></span>|<span data-ttu-id="5bd14-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="5bd14-162">**Single**</span></span>|<span data-ttu-id="5bd14-163">**float**</span><span class="sxs-lookup"><span data-stu-id="5bd14-163">**float**</span></span>|<span data-ttu-id="5bd14-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="5bd14-164">**Single**</span></span>|  
|<span data-ttu-id="5bd14-165">**double**</span><span class="sxs-lookup"><span data-stu-id="5bd14-165">**double**</span></span>|<span data-ttu-id="5bd14-166">**double**</span><span class="sxs-lookup"><span data-stu-id="5bd14-166">**Double**</span></span>|<span data-ttu-id="5bd14-167">**double**</span><span class="sxs-lookup"><span data-stu-id="5bd14-167">**double**</span></span>|<span data-ttu-id="5bd14-168">**double**</span><span class="sxs-lookup"><span data-stu-id="5bd14-168">**Double**</span></span>|  
|<span data-ttu-id="5bd14-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="5bd14-169">**bool**</span></span>|<span data-ttu-id="5bd14-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5bd14-170">**Boolean**</span></span>|<span data-ttu-id="5bd14-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="5bd14-171">**bool**</span></span>|<span data-ttu-id="5bd14-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5bd14-172">**Boolean**</span></span>|  
|<span data-ttu-id="5bd14-173">**char**</span><span class="sxs-lookup"><span data-stu-id="5bd14-173">**char**</span></span>|<span data-ttu-id="5bd14-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="5bd14-174">**Char**</span></span>|<span data-ttu-id="5bd14-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="5bd14-175">**wchar_t**</span></span>|<span data-ttu-id="5bd14-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="5bd14-176">**Char**</span></span>|  
|<span data-ttu-id="5bd14-177">**string**</span><span class="sxs-lookup"><span data-stu-id="5bd14-177">**string**</span></span>|<span data-ttu-id="5bd14-178">**String**</span><span class="sxs-lookup"><span data-stu-id="5bd14-178">**String**</span></span>|<span data-ttu-id="5bd14-179">**String**</span><span class="sxs-lookup"><span data-stu-id="5bd14-179">**String**</span></span>|<span data-ttu-id="5bd14-180">**String**</span><span class="sxs-lookup"><span data-stu-id="5bd14-180">**String**</span></span>|  
|<span data-ttu-id="5bd14-181">**object**</span><span class="sxs-lookup"><span data-stu-id="5bd14-181">**object**</span></span>|<span data-ttu-id="5bd14-182">**개체**</span><span class="sxs-lookup"><span data-stu-id="5bd14-182">**Object**</span></span>|<span data-ttu-id="5bd14-183">**개체**</span><span class="sxs-lookup"><span data-stu-id="5bd14-183">**Object**</span></span>|<span data-ttu-id="5bd14-184">**개체**</span><span class="sxs-lookup"><span data-stu-id="5bd14-184">**Object**</span></span>|  
  
 <span data-ttu-id="5bd14-185">**✓ DO** 와 같은 일반 이름을 사용 하 여 `value` 또는 `item`, 형식 이름 식별자 의미가 없는 및 매개 변수의 형식이 중요 하지 않은 경우 드문 경우에서를 반복할 필요 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="5bd14-186">새 버전의 기존 Api 이름 지정</span><span class="sxs-lookup"><span data-stu-id="5bd14-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="5bd14-187">**✓ DO** 기존 API의 새 버전을 만들 때 기존 API와 유사한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="5bd14-188">이렇게 하면 Api 간의 관계를 강조 표시 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="5bd14-189">**✓ DO** 선호 기존 API의 새 버전을 나타내는 접두사 보다는 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="5bd14-190">그러면 설명서를 찾아보거나 IntelliSense를 사용 하 여 검색을 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="5bd14-191">대부분의 브라우저와 IntelliSense는 식별자를 사전순으로 표시 하기 때문에 이전 버전의 API는 새 Api와 거의 유사 하 게 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="5bd14-192">**✓ CONSIDER** 접두사 또는 접미사를 추가 하는 대신 새로운, 하지만 의미 있는 식별자를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="5bd14-193">**✓ DO** 특히 API의 기존 이름이 경우 (즉,이 산업 표준) 쉽게 알아볼 수 있는 유일한 이름이 어떤 의미 있는 추가 하는 경우 접미사 (또는 이름을 변경) 되지 않은 경우 응용 프로그램에 기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다. ropriate 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="5bd14-194">**X DO NOT** "Ex" (또는 유사한)를 사용 하 여 이전 버전의 동일한 API와 구분 식별자에 대 한 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="5bd14-195">**✓ DO** 32 비트 정수 대신 64 비트 정수 (long 정수)에서 작동 하는 Api의 버전을 도입할 때 "64" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5bd14-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="5bd14-196">기존 32 비트 API가 있는 경우에만이 방법을 사용 해야 합니다. 64 비트 버전만 사용 하는 새로운 Api에 대해서는이 작업을 수행 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="5bd14-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="5bd14-197">*2005, 2009 Microsoft Corporation © 부분입니다. All rights reserved.*</span><span class="sxs-lookup"><span data-stu-id="5bd14-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5bd14-198">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5bd14-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd14-199">참조</span><span class="sxs-lookup"><span data-stu-id="5bd14-199">See also</span></span>

- [<span data-ttu-id="5bd14-200">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5bd14-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="5bd14-201">명명 지침</span><span class="sxs-lookup"><span data-stu-id="5bd14-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
