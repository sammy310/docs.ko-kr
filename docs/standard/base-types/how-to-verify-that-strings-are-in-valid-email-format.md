---
title: '방법: 문자열이 올바른 전자 메일 형식인지 확인'
description: .NET에서 정규식을 통해 문자열이 유효한 전자 메일 형식인지 확인하는 방법의 예제를 찹조하세요.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, examples
- user input, examples
- Regex.IsMatch method
- regular expressions [.NET Framework], examples
- examples [Visual Basic], strings
- IsValidEmail
- validation, email strings
- input, checking
- strings [.NET Framework], examples [Visual Basic]
- email [.NET Framework], validating
- IsMatch method
ms.assetid: 7536af08-4e86-4953-98a1-a8298623df92
ms.openlocfilehash: 90e79af649727330c2afa1ccb8c64ffe34733f92
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022950"
---
# <a name="how-to-verify-that-strings-are-in-valid-email-format"></a><span data-ttu-id="d5468-103">방법: 문자열이 올바른 전자 메일 형식인지 확인</span><span class="sxs-lookup"><span data-stu-id="d5468-103">How to verify that strings are in valid email format</span></span>

<span data-ttu-id="d5468-104">다음 예제에서는 정규식을 사용하여 문자열이 올바른 전자 메일 형식인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-104">The following example uses a regular expression to verify that a string is in valid email format.</span></span>

<span data-ttu-id="d5468-105">이 정규식은 실제로 메일로 사용될 수 있는 것에 비해 비교적 단순합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-105">This regular expression is comparatively simple to what can actually be used as an email.</span></span> <span data-ttu-id="d5468-106">정규식을 사용하여 메일의 유효성을 검사하는 것은 메일의 구조가 올바른지 확인하는 데 유용하지만 메일이 실제로 존재하는지 확인하는 작업을 대체하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-106">Using a regular expression to validate an email is useful to make sure the structure of an email is correct, but it isn't a substitution for verifying the email actually exists.</span></span>

<span data-ttu-id="d5468-107">✔️ 작은 정규식을 사용하여 메일의 유효한 구조를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-107">✔️ DO use a small regular expression to check for the valid structure of an email.</span></span>

<span data-ttu-id="d5468-108">✔️ 앱 사용자가 제공한 주소로 테스트 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-108">✔️ DO send a test email to the address provided by a user of your app.</span></span>

<span data-ttu-id="d5468-109">❌ 메일의 유효성을 검사하는 유일한 방법으로 정규식을 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="d5468-109">❌ DON'T use a regular expression as the only way you validate an email.</span></span>

<span data-ttu-id="d5468-110">메일의 구조가 올바른지 확인하는 ‘완벽한’ 정규식을 만들려는 경우 해당 식은 아주 복잡해져서 디버그하거나 개선하기가 매우 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-110">If you try to create the _perfect_ regular expression to validate that the structure of an email is correct, the expression becomes so complex that it's incredibly difficult to debug or improve.</span></span> <span data-ttu-id="d5468-111">정규식은 메일의 구조가 올바르게 구성된 경우에도 메일이 존재하는지 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-111">Regular expressions can't validate an email exists, even if it's structured correctly.</span></span> <span data-ttu-id="d5468-112">메일의 유효성을 검사하는 가장 좋은 방법은 주소로 테스트 메일을 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-112">The best way to validate an email is to send a test email to the address.</span></span>

[!INCLUDE [regex](../../../includes/regex.md)]

## <a name="example"></a><span data-ttu-id="d5468-113">예제</span><span class="sxs-lookup"><span data-stu-id="d5468-113">Example</span></span>

<span data-ttu-id="d5468-114">이 예제에서는 문자열에 유효한 메일 주소가 포함되어 있으면 `IsValidEmail`을 반환하고, 그러지 않으면 `true`를 반환하지만 다른 작업을 수행하지 않는 `false` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-114">The example defines an `IsValidEmail` method, which returns `true` if the string contains a valid email address and `false` if it doesn't, but takes no other action.</span></span>

<span data-ttu-id="d5468-115">전자 메일 주소가 올바른지 확인하기 위해 `IsValidEmail` 메서드는 <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> 정규식 패턴으로 `(@)(.+)$` 메서드를 호출하여 전자 메일 주소에서 도메인 이름을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-115">To verify that the email address is valid, the `IsValidEmail` method calls the <xref:System.Text.RegularExpressions.Regex.Replace%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.MatchEvaluator%29?displayProperty=nameWithType> method with the `(@)(.+)$` regular expression pattern to separate the domain name from the email address.</span></span> <span data-ttu-id="d5468-116">세 번째 매개 변수는 일치하는 텍스트를 처리하고 대체하는 메서드를 나타내는 <xref:System.Text.RegularExpressions.MatchEvaluator> 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-116">The third parameter is a <xref:System.Text.RegularExpressions.MatchEvaluator> delegate that represents the method that processes and replaces the matched text.</span></span> <span data-ttu-id="d5468-117">정규식 패턴은 다음과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-117">The regular expression pattern is interpreted as follows.</span></span>

| <span data-ttu-id="d5468-118">무늬</span><span class="sxs-lookup"><span data-stu-id="d5468-118">Pattern</span></span> | <span data-ttu-id="d5468-119">설명</span><span class="sxs-lookup"><span data-stu-id="d5468-119">Description</span></span>                                                                         |
|---------|-------------------------------------------------------------------------------------|
| `(@)`   | <span data-ttu-id="d5468-120">@ 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-120">Match the @ character.</span></span> <span data-ttu-id="d5468-121">이 부분은 첫 번째 캡처 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-121">This part is the first capturing group.</span></span>                           |
| `(.+)`  | <span data-ttu-id="d5468-122">하나 이상의 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-122">Match one or more occurrences of any character.</span></span> <span data-ttu-id="d5468-123">이 부분은 두 번째 캡처 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-123">This part is the second capturing group.</span></span> |
| `$`     | <span data-ttu-id="d5468-124">문자열의 끝 부분에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-124">End the match at the end of the string.</span></span>                                             |

<span data-ttu-id="d5468-125">@ 문자와 함께 도메인 이름이 `DomainMapper` 메서드로 전달됩니다. 이 메서드는 <xref:System.Globalization.IdnMapping> 클래스를 사용하여 US-ASCII 문자 범위 외부에 있는 유니코드 문자를 Punycode로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-125">The domain name along with the @ character is passed to the `DomainMapper` method, which uses the <xref:System.Globalization.IdnMapping> class to translate Unicode characters that are outside the US-ASCII character range to Punycode.</span></span> <span data-ttu-id="d5468-126">이 메서드는 `invalid` 메서드가 도메인 이름에서 잘못된 문자를 발견하는 경우 `True` 플래그를 <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-126">The method also sets the `invalid` flag to `True` if the <xref:System.Globalization.IdnMapping.GetAscii%2A?displayProperty=nameWithType> method detects any invalid characters in the domain name.</span></span> <span data-ttu-id="d5468-127">메서드는 앞에 @ 기호가 있는 Punycode 도메인 이름을 `IsValidEmail` 메서드에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-127">The method returns the Punycode domain name preceded by the @ symbol to the `IsValidEmail` method.</span></span>

> [!TIP]
> <span data-ttu-id="d5468-128">단순한 `(@)(.+)$` 정규식 패턴을 사용하여 도메인을 정규화한 후에 성공 또는 실패를 나타내는 값을 반환하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-128">It's recommended that you use use the simple `(@)(.+)$` regular expression pattern to normalize the domain and then return a value indicating that it passed or failed.</span></span> <span data-ttu-id="d5468-129">하지만 이 문서의 예제에서는 정규식을 추가로 사용하여 메일의 유효성을 검사하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-129">However, the example in this article describes how to further use a regular expression to validate the email.</span></span> <span data-ttu-id="d5468-130">메일의 유효성을 검사하는 방법과 관계없이, 항상 주소로 테스트 메일을 전송하여 메일이 존재하는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-130">Regardless of how you validate an email, you should always send a test email to the address to make sure it exists.</span></span>

<span data-ttu-id="d5468-131">그러면 `IsValidEmail` 메서드는 <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> 메서드를 호출하여 주소가 정규식 패턴을 따르는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-131">The `IsValidEmail` method then calls the <xref:System.Text.RegularExpressions.Regex.IsMatch%28System.String%2CSystem.String%29?displayProperty=nameWithType> method to verify that the address conforms to a regular expression pattern.</span></span>

<span data-ttu-id="d5468-132">`IsValidEmail` 메서드는 메일 형식이 메일 주소에 유효한지 여부를 확인할 뿐이며 메일이 존재하는지 여부를 확인하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-132">The `IsValidEmail` method merely determines whether the email format is valid for an email address, it doesn't validate that the email exists.</span></span> <span data-ttu-id="d5468-133">또한 `IsValidEmail` 메서드는 최상위 도메인 이름이 조회 작업 시 요구되는 [IANA 루트 영역 데이터베이스](https://www.iana.org/domains/root/db)에 나열된 유효한 도메인 이름인지 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-133">Also, the `IsValidEmail` method doesn't verify that the top-level domain name is a valid domain name listed at the [IANA Root Zone Database](https://www.iana.org/domains/root/db), which would require a look-up operation.</span></span>

:::code language="csharp" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/csharp/RegexUtilities.cs":::

:::code language="vb" source="snippets/how-to-verify-that-strings-are-in-valid-email-format/vb/RegexUtilities.vb":::

<span data-ttu-id="d5468-134">이 예제에서 정규식 패턴 `^[^@\s]+@[^@\s]+\.[^@\s]+$`는 다음 테이블과 같이 해석됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-134">In this example, the regular expression pattern `^[^@\s]+@[^@\s]+\.[^@\s]+$` is interpreted as shown in the following table.</span></span> <span data-ttu-id="d5468-135">정규식은 <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> 플래그를 사용하여 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-135">The regular expression is compiled using the <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> flag.</span></span>

| <span data-ttu-id="d5468-136">무늬</span><span class="sxs-lookup"><span data-stu-id="d5468-136">Pattern</span></span>   | <span data-ttu-id="d5468-137">설명</span><span class="sxs-lookup"><span data-stu-id="d5468-137">Description</span></span>                                                                              |
|-----------|------------------------------------------------------------------------------------------|
| `^`       | <span data-ttu-id="d5468-138">문자열의 시작 부분에서 일치 항목 찾기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-138">Begin the match at the start of the string.</span></span>                                              |
| `[^@\s]+` | <span data-ttu-id="d5468-139">@ 문자나 공백 이외의 다른 문자를 하나 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-139">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `@`       | <span data-ttu-id="d5468-140">@ 문자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-140">Match the @ character.</span></span>                                                                   |
| `[^@\s]+` | <span data-ttu-id="d5468-141">@ 문자나 공백 이외의 다른 문자를 하나 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-141">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `\.`      | <span data-ttu-id="d5468-142">마침표 문자 하나를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-142">Match a single period character.</span></span>                                                         |
| `[^@\s]+` | <span data-ttu-id="d5468-143">@ 문자나 공백 이외의 다른 문자를 하나 이상 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-143">Match one or more occurrences of any character other than the @ character or whitespace.</span></span> |
| `$`       | <span data-ttu-id="d5468-144">문자열의 끝 부분에서 일치 항목 찾기를 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-144">End the match at the end of the string.</span></span>                                                  |

> [!IMPORTANT]
> <span data-ttu-id="d5468-145">이 정규식은 유효한 메일 주소의 모든 측면을 포괄하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-145">This regular expression is not intended to cover every aspect of a valid email address.</span></span> <span data-ttu-id="d5468-146">필요에 따라 확장하는 예제로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5468-146">It's provided as an example for you to extend as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5468-147">참조</span><span class="sxs-lookup"><span data-stu-id="d5468-147">See also</span></span>

- [<span data-ttu-id="d5468-148">.NET Framework 정규식</span><span class="sxs-lookup"><span data-stu-id="d5468-148">.NET Framework Regular Expressions</span></span>](regular-expressions.md)
- [<span data-ttu-id="d5468-149">어느 정도까지 메일 주소의 유효성을 검사해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="d5468-149">How far should one take e-mail address validation?</span></span>](https://softwareengineering.stackexchange.com/questions/78353/how-far-should-one-take-e-mail-address-validation#78363)
