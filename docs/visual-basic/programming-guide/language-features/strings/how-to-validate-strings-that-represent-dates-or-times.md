---
title: '방법: 날짜 또는 시간을 나타내는 문자열 확인 (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f24ff05e48327c21c02eb92b07db17266f743a80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024614"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="20fb9-102">방법: 날짜 또는 시간을 나타내는 문자열 확인 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20fb9-102">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>
<span data-ttu-id="20fb9-103">다음 코드 예제에서는 `Boolean` 문자열이 유효한 날짜 또는 시간을 나타내는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="20fb9-103">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20fb9-104">예제</span><span class="sxs-lookup"><span data-stu-id="20fb9-104">Example</span></span>  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="20fb9-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="20fb9-105">Compiling the Code</span></span>  
 <span data-ttu-id="20fb9-106">바꿉니다 `("01/01/03")` 고 `"9:30 PM"` 유효성을 검사 하려는 시간과 날짜를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="20fb9-106">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="20fb9-107">사용 하 여 다른 하드 코드 된 문자열을 사용 하 여 문자열을 바꿀 수 있습니다는 `String` 변수나 메서드를 사용 하 여 반환 하는 문자열 같은 `InputBox`합니다.</span><span class="sxs-lookup"><span data-stu-id="20fb9-107">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="20fb9-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="20fb9-108">Robust Programming</span></span>  
 <span data-ttu-id="20fb9-109">이 메서드를 사용 하 여 문자열 변환 하려고 하기 전에 유효성을 검사 합니다 `String` 에 `DateTime` 변수.</span><span class="sxs-lookup"><span data-stu-id="20fb9-109">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="20fb9-110">날짜 또는 시간을 먼저 확인 하 여 런타임 시 예외를 생성을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20fb9-110">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20fb9-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="20fb9-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="20fb9-112">Visual Basic의 문자열 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="20fb9-112">Validating Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
