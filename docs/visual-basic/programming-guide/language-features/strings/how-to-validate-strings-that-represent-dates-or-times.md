---
description: '자세한 정보: 방법: 날짜 또는 시간을 나타내는 문자열 유효성 검사 (Visual Basic)'
title: '방법: 날짜 또는 시간을 나타내는 문자열의 유효성 검사'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 4e9255717d1711d8e9839c218a78b359549d9eef
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424257"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a><span data-ttu-id="c5043-103">방법: 날짜 또는 시간을 나타내는 문자열 확인(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5043-103">How to: Validate Strings That Represent Dates or Times (Visual Basic)</span></span>

<span data-ttu-id="c5043-104">다음 코드 예제에서는 `Boolean` 문자열이 유효한 날짜 또는 시간을 나타내는지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5043-104">The following code example sets a `Boolean` value that indicates whether a string represents a valid date or time.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c5043-105">예</span><span class="sxs-lookup"><span data-stu-id="c5043-105">Example</span></span>  

 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="c5043-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c5043-106">Compile the code</span></span>  

 <span data-ttu-id="c5043-107">`("01/01/03")`및을 `"9:30 PM"` 유효성을 검사할 날짜 및 시간으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c5043-107">Replace `("01/01/03")` and `"9:30 PM"` with the date and time you want to validate.</span></span> <span data-ttu-id="c5043-108">문자열을 하드 코드 된 다른 문자열, `String` 변수 또는 문자열을 반환 하는 메서드 (예:)로 바꿀 수 있습니다 `InputBox` .</span><span class="sxs-lookup"><span data-stu-id="c5043-108">You can replace the string with another hard-coded string, with a `String` variable, or with a method that returns a string, such as `InputBox`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="c5043-109">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="c5043-109">Robust Programming</span></span>  

 <span data-ttu-id="c5043-110">를 변수로 변환 하기 전에이 메서드를 사용 하 여 문자열의 유효성을 검사 합니다 `String` `DateTime` .</span><span class="sxs-lookup"><span data-stu-id="c5043-110">Use this method to validate the string before trying to convert the `String` to a `DateTime` variable.</span></span> <span data-ttu-id="c5043-111">먼저 날짜나 시간을 확인 하 여 런타임에 예외가 생성 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5043-111">By checking the date or time first, you can avoid generating an exception at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5043-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c5043-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [<span data-ttu-id="c5043-113">Visual Basic의 문자열 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="c5043-113">Validating Strings in Visual Basic</span></span>](validating-strings.md)
