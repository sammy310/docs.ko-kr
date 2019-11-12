---
title: .NET의 기본적인 문자열 작업
description: 문자열에서 수행할 수 있는 기본 작업에 대해 알아봅니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- strings [.NET Framework], basic string operations
- custom strings
ms.assetid: 8133d357-90b5-4b62-9927-43323d99b6b6
ms.custom: seadec18
ms.openlocfilehash: 05cdf399e104fc9e528c954adb19634a5c136664
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132921"
---
# <a name="basic-string-operations-in-net"></a><span data-ttu-id="38205-103">.NET의 기본적인 문자열 작업</span><span class="sxs-lookup"><span data-stu-id="38205-103">Basic String Operations in .NET</span></span>
<span data-ttu-id="38205-104">애플리케이션에서 사용자 입력을 기반으로 메시지를 생성하여 사용자에게 응답하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="38205-104">Applications often respond to users by constructing messages based on user input.</span></span> <span data-ttu-id="38205-105">예를 들어 웹 사이트에서 사용자 이름을 포함하는 특수 인사말을 사용하여 새로 로그온한 사용자에게 응답하는 경우도 드물지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38205-105">For example, it is not uncommon for Web sites to respond to a newly logged-on user with a specialized greeting that includes the user's name.</span></span> <span data-ttu-id="38205-106"><xref:System.String?displayProperty=nameWithType> 및 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 클래스의 여러 메서드를 통해 사용자 인터페이스에 표시할 사용자 지정 문자열을 동적으로 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38205-106">Several methods in the <xref:System.String?displayProperty=nameWithType> and <xref:System.Text.StringBuilder?displayProperty=nameWithType> classes allow you to dynamically construct custom strings to display in your user interface.</span></span> <span data-ttu-id="38205-107">이러한 메서드는 바이트 배열에서 새 문자열 만들기, 문자열 값 비교, 기존 문자열 수정 등의 여러 기본적인 문자열 작업을 수행하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38205-107">These methods also help you perform a number of basic string operations like creating new strings from arrays of bytes, comparing the values of strings, and modifying existing strings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="38205-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="38205-108">In This Section</span></span>  
 [<span data-ttu-id="38205-109">새 문자열 만들기</span><span class="sxs-lookup"><span data-stu-id="38205-109">Creating New Strings</span></span>](../../../docs/standard/base-types/creating-new.md)  
 <span data-ttu-id="38205-110">개체를 문자열로 변환하고 문자열을 결합하는 기본적인 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-110">Describes basic ways to convert objects into strings and to combine strings.</span></span>  
  
 [<span data-ttu-id="38205-111">문자 트리밍 및 제거</span><span class="sxs-lookup"><span data-stu-id="38205-111">Trimming and Removing Characters</span></span>](../../../docs/standard/base-types/trimming.md)  
 <span data-ttu-id="38205-112">문자열의 문자를 자르거나 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-112">Describes how to trim or remove characters in a string.</span></span>  
  
 [<span data-ttu-id="38205-113">문자열 채우기</span><span class="sxs-lookup"><span data-stu-id="38205-113">Padding Strings</span></span>](../../../docs/standard/base-types/padding.md)  
 <span data-ttu-id="38205-114">문자열에 문자 또는 공백을 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-114">Describes how to insert characters or empty spaces into a string.</span></span>  
  
 [<span data-ttu-id="38205-115">문자열 비교</span><span class="sxs-lookup"><span data-stu-id="38205-115">Comparing Strings</span></span>](../../../docs/standard/base-types/comparing.md)  
 <span data-ttu-id="38205-116">둘 이상의 문자열 내용을 비교하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-116">Describes how to compare the contents of two or more strings.</span></span>  
  
 [<span data-ttu-id="38205-117">대/소문자 바꾸기</span><span class="sxs-lookup"><span data-stu-id="38205-117">Changing Case</span></span>](../../../docs/standard/base-types/changing-case.md)  
 <span data-ttu-id="38205-118">문자열 내 문자의 대/소문자를 변경하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-118">Describes how to change the case of characters within a string.</span></span>  
  
 [<span data-ttu-id="38205-119">StringBuilder 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="38205-119">Using the StringBuilder Class</span></span>](../../../docs/standard/base-types/stringbuilder.md)  
 <span data-ttu-id="38205-120"><xref:System.Text.StringBuilder> 클래스를 사용하여 동적 문자열 개체를 만들고 수정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-120">Describes how to create and modify dynamic string objects with the <xref:System.Text.StringBuilder> class.</span></span>  
  
 [<span data-ttu-id="38205-121">방법: 기본적인 문자열 조작 수행</span><span class="sxs-lookup"><span data-stu-id="38205-121">How to: Perform Basic String Manipulations</span></span>](../../../docs/standard/base-types/basic-manipulations.md)  
 <span data-ttu-id="38205-122">기본적인 문자열 작업의 사용을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="38205-122">Demonstrates the use of basic string operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="38205-123">관련 단원</span><span class="sxs-lookup"><span data-stu-id="38205-123">Related Sections</span></span>  
 [<span data-ttu-id="38205-124">.NET에서 형식 변환</span><span class="sxs-lookup"><span data-stu-id="38205-124">Type Conversion in .NET</span></span>](../../../docs/standard/base-types/type-conversion.md)  
 <span data-ttu-id="38205-125">형식 간에 변환하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-125">Describes how to convert one type into another type.</span></span>  
  
 [<span data-ttu-id="38205-126">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="38205-126">Formatting Types</span></span>](../../../docs/standard/base-types/formatting-types.md)  
 <span data-ttu-id="38205-127">형식 지정자를 사용하여 문자열 서식을 지정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="38205-127">Describes how to format strings using format specifiers.</span></span>
