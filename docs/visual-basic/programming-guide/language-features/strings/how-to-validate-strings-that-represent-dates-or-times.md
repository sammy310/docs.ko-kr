---
title: '방법: 날짜 또는 시간을 나타내는 문자열 확인'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5321e7a85c45ddb6ce17433bd25ce9ca2165f0a3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75348407"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="6d62b-102">방법: 날짜 또는 시간을 나타내는 문자열 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d62b-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="6d62b-103">다음 코드 예제에서는 문자열이 유효한 날짜 또는 시간을 나타내는지 여부를 나타내는 `Boolean` 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d62b-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d62b-104">예제</span><span class="sxs-lookup"><span data-stu-id="6d62b-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="6d62b-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="6d62b-105">Compile the code</span></span>  
 <span data-ttu-id="6d62b-106">`("01/01/03")` 및 `"9:30 PM"`의 유효성을 검사할 날짜 및 시간으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6d62b-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="6d62b-107">문자열을 하드 코드 된 다른 문자열로 바꿀 수 있습니다. `String` 변수를 사용 하거나 `InputBox`와 같이 문자열을 반환 하는 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d62b-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="6d62b-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="6d62b-108">Robust Programming</span></span>  
 <span data-ttu-id="6d62b-109">`String`를 `DateTime` 변수로 변환 하기 전에이 메서드를 사용 하 여 문자열의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d62b-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="6d62b-110">먼저 날짜나 시간을 확인 하 여 런타임에 예외가 생성 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d62b-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d62b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d62b-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="6d62b-112">Visual Basic의 문자열 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="6d62b-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
