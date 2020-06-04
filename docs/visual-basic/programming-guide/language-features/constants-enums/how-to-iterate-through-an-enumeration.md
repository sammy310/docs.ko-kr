---
title: '방법: 열거형 반복'
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [Visual Basic], iterating
- enumerations [Visual Basic], iterating
- ListBox control [Windows Forms], populating from an enumeration
ms.assetid: e5aa10eb-cfcd-4a3b-8e76-f06b8f2002be
ms.openlocfilehash: fb6fbdd45ca0e84ccb9fc55296d78e3867d5fe25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414429"
---
# <a name="how-to-iterate-through-an-enumeration-in-visual-basic"></a><span data-ttu-id="86159-102">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="86159-102">How to: Iterate Through An Enumeration in Visual Basic</span></span>
<span data-ttu-id="86159-103">열거형은 관련된 상수 집합으로 작업하고 이름과 상수 값을 연결하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="86159-103">Enumerations provide a convenient way to work with sets of related constants, and to associate constant values with names.</span></span> <span data-ttu-id="86159-104">열거형을 반복 하려면 메서드를 사용 하 여 배열로 이동할 수 있습니다 <xref:System.Enum.GetValues%2A> .</span><span class="sxs-lookup"><span data-stu-id="86159-104">To iterate through an enumeration, you can move it into an array using the <xref:System.Enum.GetValues%2A> method.</span></span> <span data-ttu-id="86159-105">`For...Each`또는 메서드를 사용 하 여 <xref:System.Enum.GetNames%2A> <xref:System.Enum.GetValues%2A> 문자열 또는 숫자 값을 추출 하는 문을 사용 하 여 열거형을 반복할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86159-105">You could also iterate through an enumeration using a `For...Each` statement, using the <xref:System.Enum.GetNames%2A> or <xref:System.Enum.GetValues%2A> method to extract the string or numeric value.</span></span>  
  
### <a name="to-iterate-through-an-enumeration"></a><span data-ttu-id="86159-106">열거형을 반복 하려면</span><span class="sxs-lookup"><span data-stu-id="86159-106">To iterate through an enumeration</span></span>  
  
- <span data-ttu-id="86159-107">배열을 선언 하 고 <xref:System.Enum.GetValues%2A> 다른 변수와 마찬가지로 배열을 전달 하기 전에 메서드를 사용 하 여 열거형을 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="86159-107">Declare an array and convert the enumeration to it with the <xref:System.Enum.GetValues%2A> method before passing the array as you would any other variable.</span></span> <span data-ttu-id="86159-108">다음 예제에서는 열거형을 반복 하면서 열거형의 각 멤버를 표시 합니다 <xref:Microsoft.VisualBasic.FirstDayOfWeek> .</span><span class="sxs-lookup"><span data-stu-id="86159-108">The following example displays each member of the enumeration <xref:Microsoft.VisualBasic.FirstDayOfWeek> as it iterates through the enumeration.</span></span>  
  
     [!code-vb[VbEnumsTask#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbEnumsTask/VB/Class2.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="86159-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86159-109">See also</span></span>

- [<span data-ttu-id="86159-110">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="86159-110">Enumerations Overview</span></span>](enumerations-overview.md)
- [<span data-ttu-id="86159-111">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="86159-111">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)
- [<span data-ttu-id="86159-112">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="86159-112">When to Use an Enumeration</span></span>](when-to-use-an-enumeration.md)
- [<span data-ttu-id="86159-113">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="86159-113">How to: Determine the String Associated with an Enumeration Value</span></span>](how-to-determine-the-string-associated-with-an-enumeration-value.md)
- [<span data-ttu-id="86159-114">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="86159-114">How to: Refer to an Enumeration Member</span></span>](how-to-refer-to-an-enumeration-member.md)
- [<span data-ttu-id="86159-115">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="86159-115">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)
- [<span data-ttu-id="86159-116">배열</span><span class="sxs-lookup"><span data-stu-id="86159-116">Arrays</span></span>](../arrays/index.md)
