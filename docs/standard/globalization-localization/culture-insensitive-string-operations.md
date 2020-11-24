---
title: 문화권을 구분하지 않는 문자열 작업
ms.date: 03/30/2017
helpviewer_keywords:
- culture, culture-insensitive string operations
- case-sensitive comparisons
- globalization [.NET], culture-insensitive string operations
- strings [.NET], culture-insensitive string operations
- localization [.NET], culture-insensitive string operations
- world-ready applications, culture-insensitive string operations
- culture-sensitive string operations
- culture-insensitive string operations
ms.assetid: e6e2bb94-a95d-44e2-b68c-cfdd1db77784
ms.openlocfilehash: 2cfd4bf3428832c204124637fbbe3de2edd554f9
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94827128"
---
# <a name="culture-insensitive-string-operations"></a><span data-ttu-id="8561e-102">문화권을 구분하지 않는 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="8561e-102">Culture-insensitive string operations</span></span>

<span data-ttu-id="8561e-103">문화권 구분 문자열 작업은 문화권별로 사용자에게 결과를 표시하도록 디자인된 애플리케이션을 만드는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-103">Culture-sensitive string operations can be an advantage if you are creating applications designed to display results to users on a per-culture basis.</span></span> <span data-ttu-id="8561e-104">기본적으로 문화권 구분 메서드는 사용할 문화권을 현재 스레드의 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 속성에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-104">By default, culture-sensitive methods obtain the culture to use from the <xref:System.Globalization.CultureInfo.CurrentCulture%2A> property for the current thread.</span></span>

<span data-ttu-id="8561e-105">경우에 따라 문화권 구분 문자열 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-105">Sometimes, culture-sensitive string operations are not the desired behavior.</span></span> <span data-ttu-id="8561e-106">결과가 문화권의 영향을 받지 않아야 하는 경우 문화권 구분 작업을 사용하면, 사용자 지정 연결과 정렬 규칙을 포함한 지정된 문화권에서의 애플리케이션 코드가 제대로 실행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-106">Using culture-sensitive operations when results should be independent of culture can cause application code to fail on cultures with custom case mappings and sorting rules.</span></span> <span data-ttu-id="8561e-107">예제는 [문자열 사용에 대한 모범 사례](../base-types/best-practices-strings.md) 문서에서 ["현재 문화권을 사용하는 문자열 비교"](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8561e-107">For an example, see the ["String Comparisons that Use the Current Culture"](../base-types/best-practices-strings.md#string-comparisons-that-use-the-current-culture) section in the [Best Practices for Using Strings](../base-types/best-practices-strings.md) article.</span></span>

<span data-ttu-id="8561e-108">문자열 작업의 문화권 구분 여부는 애플리케이션에서 작업 결과를 사용하는 방식에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-108">Whether string operations should be culture-sensitive or culture-insensitive depends on how your application uses the results.</span></span> <span data-ttu-id="8561e-109">사용자에게 결과를 표시하는 문자열 작업은 일반적으로 문화권을 구분해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-109">String operations that display results to the user should typically be culture-sensitive.</span></span> <span data-ttu-id="8561e-110">예를 들어 애플리케이션에서 지역화된 문자열 목록을 정렬하여 목록 상자에 표시하는 경우 애플리케이션에서 문화권 구분 정렬을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-110">For example, if an application displays a sorted list of localized strings in a list box, the application should perform a culture-sensitive sort.</span></span>

<span data-ttu-id="8561e-111">내부적으로 사용되는 문자열 작업의 결과는 일반적으로 문화권을 구분하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-111">Results of string operations that are used internally should typically be culture-insensitive.</span></span> <span data-ttu-id="8561e-112">일반적으로 애플리케이션에서 사용자에게 표시되지 않는 파일 이름, 지속성 형식 또는 기호화된 정보로 작업하는 경우 문자열 작업의 결과가 문화권의 영향을 받지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-112">In general, if the application is working with file names, persistence formats, or symbolic information that is not displayed to the user, results of string operations should not vary by culture.</span></span> <span data-ttu-id="8561e-113">예를 들어, 애플리케이션이 문자열을 비교하여 인식되는 XML 태그인지 여부를 결정하는 경우 비교 작업은 문화권을 구분하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-113">For example, if an application compares a string to determine whether it is a recognized XML tag, the comparison should not be culture-sensitive.</span></span> <span data-ttu-id="8561e-114">또한 문자열 비교 또는 대/소문자 변경 작업의 결과에 따라 보안 결정을 수행하는 경우 <xref:System.Globalization.CultureInfo.CurrentCulture%2A> 값의 영향을 받지 않는 결과를 얻기 위해 문화권을 구분하지 않고 작업을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-114">In addition, if a security decision is based on the result of a string comparison or case change operation, the operation should be culture-insensitive to ensure that the result is not affected by the value of <xref:System.Globalization.CultureInfo.CurrentCulture%2A>.</span></span>

<span data-ttu-id="8561e-115">지역화 및 전역화 문제를 처리하는 코드가 포함된 애플리케이션을 개발하는지와 관계없이 기본적으로 문화권 구분 결과를 검색하는 .NET 메서드를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8561e-115">Whether or not you're developing an application that includes code to handle localization and globalization issues, you should be aware of the .NET methods that retrieve culture-sensitive results by default.</span></span>

## <a name="see-also"></a><span data-ttu-id="8561e-116">참조</span><span class="sxs-lookup"><span data-stu-id="8561e-116">See also</span></span>

- [<span data-ttu-id="8561e-117">전역화 및 지역화</span><span class="sxs-lookup"><span data-stu-id="8561e-117">Globalization and Localization</span></span>](index.md)
