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
author: KrzysztofCwalina
ms.openlocfilehash: ae1b7ce83f6698cef470aabf07a12d89042ab8a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026395"
---
# <a name="general-naming-conventions"></a><span data-ttu-id="5f68c-102">일반 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="5f68c-102">General Naming Conventions</span></span>
<span data-ttu-id="5f68c-103">이 섹션에서는 일반 명명 규칙 단어 선택와 관련 된 약어 및 머리글자어 및 권장 사항을 사용 하 여 언어별 이름을 사용 하지 않도록 하는 방법에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-103">This section describes general naming conventions that relate to word choice, guidelines on using abbreviations and acronyms, and recommendations on how to avoid using language-specific names.</span></span>  
  
## <a name="word-choice"></a><span data-ttu-id="5f68c-104">단어 선택</span><span class="sxs-lookup"><span data-stu-id="5f68c-104">Word Choice</span></span>  
 <span data-ttu-id="5f68c-105">**✓ DO** 쉽게 읽을 수 있는 식별자 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-105">**✓ DO** choose easily readable identifier names.</span></span>  
  
 <span data-ttu-id="5f68c-106">예를 들어, 명명 된 속성 `HorizontalAlignment` 좀 더 영어-읽기 보다 `AlignmentHorizontal`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-106">For example, a property named `HorizontalAlignment` is more English-readable than `AlignmentHorizontal`.</span></span>  
  
 <span data-ttu-id="5f68c-107">**✓ DO** 가독성 간결한 설명을 위해 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-107">**✓ DO** favor readability over brevity.</span></span>  
  
 <span data-ttu-id="5f68c-108">속성 이름을 `CanScrollHorizontally` 보다 나은 `ScrollableX` (x 축에는 모호한 참조).</span><span class="sxs-lookup"><span data-stu-id="5f68c-108">The property name `CanScrollHorizontally` is better than `ScrollableX` (an obscure reference to the X-axis).</span></span>  
  
 <span data-ttu-id="5f68c-109">**X DO NOT** 밑줄, 하이픈 또는 기타 영숫자가 아닌 문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-109">**X DO NOT** use underscores, hyphens, or any other nonalphanumeric characters.</span></span>  
  
 <span data-ttu-id="5f68c-110">**X DO NOT** 헝가리 식 표기법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-110">**X DO NOT** use Hungarian notation.</span></span>  
  
 <span data-ttu-id="5f68c-111">**X AVOID** 널리의 키워드와 충돌 하는 식별자를 사용 하 여 프로그래밍 언어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-111">**X AVOID** using identifiers that conflict with keywords of widely used programming languages.</span></span>  
  
 <span data-ttu-id="5f68c-112">규칙 4의는 언어 사양 CLS (공용)에 따라 모든 규격 언어 식별자로 해당 언어의 키워드를 사용 하는 명명 된 항목에 대 한 액세스를 허용 하는 메커니즘을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-112">According to Rule 4 of the Common Language Specification (CLS), all compliant languages must provide a mechanism that allows access to named items that use a keyword of that language as an identifier.</span></span> <span data-ttu-id="5f68c-113">C#의 경우, 예를 들어, 사용 하는 @ 기호가 경우에서 이스케이프 메커니즘으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-113">C#, for example, uses the @ sign as an escape mechanism in this case.</span></span> <span data-ttu-id="5f68c-114">그러나 것이 좋습니다 여전히는 메서드를 사용 하는 이스케이프 시퀀스 없이 개를 사용 하 여 훨씬 더 어렵기 때문에 일반적인 키워드를 방지 하려면.</span><span class="sxs-lookup"><span data-stu-id="5f68c-114">However, it is still a good idea to avoid common keywords because it is much more difficult to use a method with the escape sequence than one without it.</span></span>  
  
## <a name="using-abbreviations-and-acronyms"></a><span data-ttu-id="5f68c-115">머리 글자어와 약어를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="5f68c-115">Using Abbreviations and Acronyms</span></span>  
 <span data-ttu-id="5f68c-116">**X DO NOT** 식별자 이름의 일부로 약어 또는 축약을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-116">**X DO NOT** use abbreviations or contractions as part of identifier names.</span></span>  
  
 <span data-ttu-id="5f68c-117">사용 예를 들어 `GetWindow` 대신 `GetWin`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-117">For example, use `GetWindow` rather than `GetWin`.</span></span>  
  
 <span data-ttu-id="5f68c-118">**X DO NOT** 폭넓게 활용 되 고 필요한 경우에 있는 경우에 하지 않은 머리글자어를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-118">**X DO NOT** use any acronyms that are not widely accepted, and even if they are, only when necessary.</span></span>  
  
## <a name="avoiding-language-specific-names"></a><span data-ttu-id="5f68c-119">언어별 이름을 방지</span><span class="sxs-lookup"><span data-stu-id="5f68c-119">Avoiding Language-Specific Names</span></span>  
 <span data-ttu-id="5f68c-120">**✓ DO** 형식 이름에 대 한 언어별 키워드 보다는 특별 한 의미가 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-120">**✓ DO** use semantically interesting names rather than language-specific keywords for type names.</span></span>  
  
 <span data-ttu-id="5f68c-121">예를 들어 `GetLength` 보다 더 나은 이름이 `GetInt`합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-121">For example, `GetLength` is a better name than `GetInt`.</span></span>  
  
 <span data-ttu-id="5f68c-122">**✓ DO** 드문 경우 식별자 의미가 없는 해당 형식 이상의 때의 언어 관련 이름 대신 일반 CLR 형식 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-122">**✓ DO** use a generic CLR type name, rather than a language-specific name, in the rare cases when an identifier has no semantic meaning beyond its type.</span></span>  
  
 <span data-ttu-id="5f68c-123">변환할 메서드 예를 들어 <xref:System.Int64> 명명할 `ToInt64`가 아닌 `ToLong` (때문에 <xref:System.Int64> 은 C#에 대 한 CLR 이름-특정 별칭 `long`).</span><span class="sxs-lookup"><span data-stu-id="5f68c-123">For example, a method converting to <xref:System.Int64> should be named `ToInt64`, not `ToLong` (because <xref:System.Int64> is a CLR name for the C#-specific alias `long`).</span></span> <span data-ttu-id="5f68c-124">다음 표에서 몇 가지 기본 데이터 형식을 CLR을 사용 하 여 형식 이름 (해당 형식 이름은 뿐만 아니라 C#, Visual Basic의 경우 및 C++).</span><span class="sxs-lookup"><span data-stu-id="5f68c-124">The following table presents several base data types using the CLR type names (as well as the corresponding type names for C#, Visual Basic, and C++).</span></span>  
  
|<span data-ttu-id="5f68c-125">C#</span><span class="sxs-lookup"><span data-stu-id="5f68c-125">C#</span></span>|<span data-ttu-id="5f68c-126">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5f68c-126">Visual Basic</span></span>|<span data-ttu-id="5f68c-127">C++</span><span class="sxs-lookup"><span data-stu-id="5f68c-127">C++</span></span>|<span data-ttu-id="5f68c-128">CLR</span><span class="sxs-lookup"><span data-stu-id="5f68c-128">CLR</span></span>|  
|---------|------------------|-----------|---------|  
|<span data-ttu-id="5f68c-129">**sbyte**</span><span class="sxs-lookup"><span data-stu-id="5f68c-129">**sbyte**</span></span>|<span data-ttu-id="5f68c-130">**SByte**</span><span class="sxs-lookup"><span data-stu-id="5f68c-130">**SByte**</span></span>|<span data-ttu-id="5f68c-131">**char**</span><span class="sxs-lookup"><span data-stu-id="5f68c-131">**char**</span></span>|<span data-ttu-id="5f68c-132">**SByte**</span><span class="sxs-lookup"><span data-stu-id="5f68c-132">**SByte**</span></span>|  
|<span data-ttu-id="5f68c-133">**byte**</span><span class="sxs-lookup"><span data-stu-id="5f68c-133">**byte**</span></span>|<span data-ttu-id="5f68c-134">**Byte**</span><span class="sxs-lookup"><span data-stu-id="5f68c-134">**Byte**</span></span>|<span data-ttu-id="5f68c-135">**unsigned char**</span><span class="sxs-lookup"><span data-stu-id="5f68c-135">**unsigned char**</span></span>|<span data-ttu-id="5f68c-136">**Byte**</span><span class="sxs-lookup"><span data-stu-id="5f68c-136">**Byte**</span></span>|  
|<span data-ttu-id="5f68c-137">**short**</span><span class="sxs-lookup"><span data-stu-id="5f68c-137">**short**</span></span>|<span data-ttu-id="5f68c-138">**Short**</span><span class="sxs-lookup"><span data-stu-id="5f68c-138">**Short**</span></span>|<span data-ttu-id="5f68c-139">**short**</span><span class="sxs-lookup"><span data-stu-id="5f68c-139">**short**</span></span>|<span data-ttu-id="5f68c-140">**Int16**</span><span class="sxs-lookup"><span data-stu-id="5f68c-140">**Int16**</span></span>|  
|<span data-ttu-id="5f68c-141">**ushort**</span><span class="sxs-lookup"><span data-stu-id="5f68c-141">**ushort**</span></span>|<span data-ttu-id="5f68c-142">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="5f68c-142">**UInt16**</span></span>|<span data-ttu-id="5f68c-143">**unsigned short**</span><span class="sxs-lookup"><span data-stu-id="5f68c-143">**unsigned short**</span></span>|<span data-ttu-id="5f68c-144">**UInt16**</span><span class="sxs-lookup"><span data-stu-id="5f68c-144">**UInt16**</span></span>|  
|<span data-ttu-id="5f68c-145">**int**</span><span class="sxs-lookup"><span data-stu-id="5f68c-145">**int**</span></span>|<span data-ttu-id="5f68c-146">**Integer**</span><span class="sxs-lookup"><span data-stu-id="5f68c-146">**Integer**</span></span>|<span data-ttu-id="5f68c-147">**int**</span><span class="sxs-lookup"><span data-stu-id="5f68c-147">**int**</span></span>|<span data-ttu-id="5f68c-148">**Int32**</span><span class="sxs-lookup"><span data-stu-id="5f68c-148">**Int32**</span></span>|  
|<span data-ttu-id="5f68c-149">**uint**</span><span class="sxs-lookup"><span data-stu-id="5f68c-149">**uint**</span></span>|<span data-ttu-id="5f68c-150">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="5f68c-150">**UInt32**</span></span>|<span data-ttu-id="5f68c-151">**unsigned int**</span><span class="sxs-lookup"><span data-stu-id="5f68c-151">**unsigned int**</span></span>|<span data-ttu-id="5f68c-152">**UInt32**</span><span class="sxs-lookup"><span data-stu-id="5f68c-152">**UInt32**</span></span>|  
|<span data-ttu-id="5f68c-153">**long**</span><span class="sxs-lookup"><span data-stu-id="5f68c-153">**long**</span></span>|<span data-ttu-id="5f68c-154">**Long**</span><span class="sxs-lookup"><span data-stu-id="5f68c-154">**Long**</span></span>|<span data-ttu-id="5f68c-155">**__int64**</span><span class="sxs-lookup"><span data-stu-id="5f68c-155">**__int64**</span></span>|<span data-ttu-id="5f68c-156">**Int64**</span><span class="sxs-lookup"><span data-stu-id="5f68c-156">**Int64**</span></span>|  
|<span data-ttu-id="5f68c-157">**ulong**</span><span class="sxs-lookup"><span data-stu-id="5f68c-157">**ulong**</span></span>|<span data-ttu-id="5f68c-158">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="5f68c-158">**UInt64**</span></span>|<span data-ttu-id="5f68c-159">**unsigned __int64**</span><span class="sxs-lookup"><span data-stu-id="5f68c-159">**unsigned __int64**</span></span>|<span data-ttu-id="5f68c-160">**UInt64**</span><span class="sxs-lookup"><span data-stu-id="5f68c-160">**UInt64**</span></span>|  
|<span data-ttu-id="5f68c-161">**float**</span><span class="sxs-lookup"><span data-stu-id="5f68c-161">**float**</span></span>|<span data-ttu-id="5f68c-162">**Single**</span><span class="sxs-lookup"><span data-stu-id="5f68c-162">**Single**</span></span>|<span data-ttu-id="5f68c-163">**float**</span><span class="sxs-lookup"><span data-stu-id="5f68c-163">**float**</span></span>|<span data-ttu-id="5f68c-164">**Single**</span><span class="sxs-lookup"><span data-stu-id="5f68c-164">**Single**</span></span>|  
|<span data-ttu-id="5f68c-165">**double**</span><span class="sxs-lookup"><span data-stu-id="5f68c-165">**double**</span></span>|<span data-ttu-id="5f68c-166">**Double**</span><span class="sxs-lookup"><span data-stu-id="5f68c-166">**Double**</span></span>|<span data-ttu-id="5f68c-167">**double**</span><span class="sxs-lookup"><span data-stu-id="5f68c-167">**double**</span></span>|<span data-ttu-id="5f68c-168">**Double**</span><span class="sxs-lookup"><span data-stu-id="5f68c-168">**Double**</span></span>|  
|<span data-ttu-id="5f68c-169">**bool**</span><span class="sxs-lookup"><span data-stu-id="5f68c-169">**bool**</span></span>|<span data-ttu-id="5f68c-170">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5f68c-170">**Boolean**</span></span>|<span data-ttu-id="5f68c-171">**bool**</span><span class="sxs-lookup"><span data-stu-id="5f68c-171">**bool**</span></span>|<span data-ttu-id="5f68c-172">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5f68c-172">**Boolean**</span></span>|  
|<span data-ttu-id="5f68c-173">**char**</span><span class="sxs-lookup"><span data-stu-id="5f68c-173">**char**</span></span>|<span data-ttu-id="5f68c-174">**Char**</span><span class="sxs-lookup"><span data-stu-id="5f68c-174">**Char**</span></span>|<span data-ttu-id="5f68c-175">**wchar_t**</span><span class="sxs-lookup"><span data-stu-id="5f68c-175">**wchar_t**</span></span>|<span data-ttu-id="5f68c-176">**Char**</span><span class="sxs-lookup"><span data-stu-id="5f68c-176">**Char**</span></span>|  
|<span data-ttu-id="5f68c-177">**string**</span><span class="sxs-lookup"><span data-stu-id="5f68c-177">**string**</span></span>|<span data-ttu-id="5f68c-178">**String**</span><span class="sxs-lookup"><span data-stu-id="5f68c-178">**String**</span></span>|<span data-ttu-id="5f68c-179">**String**</span><span class="sxs-lookup"><span data-stu-id="5f68c-179">**String**</span></span>|<span data-ttu-id="5f68c-180">**String**</span><span class="sxs-lookup"><span data-stu-id="5f68c-180">**String**</span></span>|  
|<span data-ttu-id="5f68c-181">**object**</span><span class="sxs-lookup"><span data-stu-id="5f68c-181">**object**</span></span>|<span data-ttu-id="5f68c-182">**개체**</span><span class="sxs-lookup"><span data-stu-id="5f68c-182">**Object**</span></span>|<span data-ttu-id="5f68c-183">**개체**</span><span class="sxs-lookup"><span data-stu-id="5f68c-183">**Object**</span></span>|<span data-ttu-id="5f68c-184">**개체**</span><span class="sxs-lookup"><span data-stu-id="5f68c-184">**Object**</span></span>|  
  
 <span data-ttu-id="5f68c-185">**✓ DO** 와 같은 일반 이름을 사용 하 여 `value` 또는 `item`, 형식 이름 식별자 의미가 없는 및 매개 변수의 형식이 중요 하지 않은 경우 드문 경우에서를 반복할 필요 없이 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-185">**✓ DO**  use a common name, such as `value` or `item`, rather than repeating the type name, in the rare cases when an identifier has no semantic meaning and the type of the parameter is not important.</span></span>  
  
## <a name="naming-new-versions-of-existing-apis"></a><span data-ttu-id="5f68c-186">새 버전의 기존 Api 이름</span><span class="sxs-lookup"><span data-stu-id="5f68c-186">Naming New Versions of Existing APIs</span></span>  
 <span data-ttu-id="5f68c-187">**✓ DO** 기존 API의 새 버전을 만들 때 기존 API와 유사한 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-187">**✓ DO** use a name similar to the old API when creating new versions of an existing API.</span></span>  
  
 <span data-ttu-id="5f68c-188">이렇게 하면 Api 간의 관계를 강조 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-188">This helps to highlight the relationship between the APIs.</span></span>  
  
 <span data-ttu-id="5f68c-189">**✓ DO** 선호 기존 API의 새 버전을 나타내는 접두사 보다는 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-189">**✓ DO** prefer adding a suffix rather than a prefix to indicate a new version of an existing API.</span></span>  
  
 <span data-ttu-id="5f68c-190">설명서를 검색할 때 검색 데 도움이 되는이 IntelliSense를 사용 하 여 또는입니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-190">This will assist discovery when browsing documentation, or using IntelliSense.</span></span> <span data-ttu-id="5f68c-191">대부분의 브라우저 및 IntelliSense 식별자 사전순으로 표시 되므로 새로운 Api를 가까운 API의 이전 버전을 구성할 수 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-191">The old version of the API will be organized close to the new APIs, because most browsers and IntelliSense show identifiers in alphabetical order.</span></span>  
  
 <span data-ttu-id="5f68c-192">**✓ CONSIDER** 접두사 또는 접미사를 추가 하는 대신 새로운, 하지만 의미 있는 식별자를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-192">**✓ CONSIDER** using a brand new, but meaningful identifier, instead of adding a suffix or a prefix.</span></span>  
  
 <span data-ttu-id="5f68c-193">**✓ DO** 특히 API의 기존 이름이 경우 (즉,이 산업 표준) 쉽게 알아볼 수 있는 유일한 이름이 어떤 의미 있는 추가 하는 경우 접미사 (또는 이름을 변경) 되지 않은 경우 응용 프로그램에 기존 API의 새 버전을 나타내기 위해 숫자 접미사를 사용 합니다. ropriate 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-193">**✓ DO** use a numeric suffix to indicate a new version of an existing API, particularly if the existing name of the API is the only name that makes sense (i.e., if it is an industry standard) and if adding any meaningful suffix (or changing the name) is not an appropriate option.</span></span>  
  
 <span data-ttu-id="5f68c-194">**X DO NOT** "Ex" (또는 유사한)를 사용 하 여 이전 버전의 동일한 API와 구분 식별자에 대 한 접미사입니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-194">**X DO NOT** use the "Ex" (or a similar) suffix for an identifier to distinguish it from an earlier version of the same API.</span></span>  
  
 <span data-ttu-id="5f68c-195">**✓ DO** 32 비트 정수 대신 64 비트 정수 (long 정수)에서 작동 하는 Api의 버전을 도입할 때 "64" 접미사를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f68c-195">**✓ DO** use the "64" suffix when introducing versions of APIs that operate on a 64-bit integer (a long integer) instead of a 32-bit integer.</span></span> <span data-ttu-id="5f68c-196">기존 32 비트 API 있는 경우이 방법을 사용 해야 64 비트 버전만 사용 하 여 새로운 Api에 대 한 수행 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="5f68c-196">You only need to take this approach when the existing 32-bit API exists; don’t do it for brand new APIs with only a 64-bit version.</span></span>  
  
 <span data-ttu-id="5f68c-197">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="5f68c-197">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="5f68c-198">*사용 권한에서 교육, inc. 피어슨 재인쇄 [Framework 디자인 지침: 다시 사용할 수 있는.NET 라이브러리, 2nd Edition에 대 한 규칙, 관용구 패턴과](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina를 Brad Abrams Addison Wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*</span><span class="sxs-lookup"><span data-stu-id="5f68c-198">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f68c-199">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f68c-199">See also</span></span>

- [<span data-ttu-id="5f68c-200">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="5f68c-200">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="5f68c-201">명명 지침</span><span class="sxs-lookup"><span data-stu-id="5f68c-201">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
