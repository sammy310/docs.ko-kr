---
title: '방법: 문자 값의 배열에서 문자열 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- examples [Visual Basic], arrays
- examples [Visual Basic], Char data type
ms.assetid: 69f94e85-d57c-4ccc-a62a-426e829f5c5e
ms.openlocfilehash: 08ad2f1c9455853e92533a7f00726c73b6adb87e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071159"
---
# <a name="how-to-create-a-string-from-an-array-of-char-values-visual-basic"></a><span data-ttu-id="3c39a-102">방법: Char 값으로 이루어진 배열로 문자열 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c39a-102">How to: Create a String from An Array of Char Values (Visual Basic)</span></span>

<span data-ttu-id="3c39a-103">이 예에서는 개별 문자에서 "abcd" 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3c39a-103">This example creates the string "abcd" from individual characters.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c39a-104">예제</span><span class="sxs-lookup"><span data-stu-id="3c39a-104">Example</span></span>  

 [!code-vb[VbVbalrStrings#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#61)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="3c39a-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3c39a-105">Compile the code</span></span>  

 <span data-ttu-id="3c39a-106">이 메서드에는 특별 한 요구 사항이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3c39a-106">This method has no special requirements.</span></span>  
  
 <span data-ttu-id="3c39a-107">작은따옴표 `"a"c` `c` 에서 단일 문자 뒤에 오는 구문은 문자 리터럴을 만드는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c39a-107">The syntax `"a"c`, where a single `c` follows a single character in quotation marks, is used to create a character literal.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="3c39a-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="3c39a-108">Robust Programming</span></span>  

 <span data-ttu-id="3c39a-109">문자열에서 Null 문자 (에 해당 `Chr(0)` )를 사용 하면 문자열을 사용 하는 경우 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c39a-109">Null characters (equivalent to `Chr(0)`) in the string lead to unexpected results when using the string.</span></span> <span data-ttu-id="3c39a-110">Null 문자는 문자열에 포함 되지만 null 문자 다음에 나오는 문자는 일부 상황에서 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c39a-110">The null character will be included with the string, but characters following the null character will not be displayed in some situations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c39a-111">참조</span><span class="sxs-lookup"><span data-stu-id="3c39a-111">See also</span></span>

- <xref:System.String>
- [<span data-ttu-id="3c39a-112">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3c39a-112">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="3c39a-113">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3c39a-113">Data Types</span></span>](../data-types/index.md)
