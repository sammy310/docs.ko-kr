---
title: 현재 FieldWidths를 사용하여 줄 <number>의 구문을 분석할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_MalFormedFixedWidthLine
ms.assetid: 84e14245-dfdf-4b62-8b84-e83a31608899
ms.openlocfilehash: bd6fc431a4a943a3a0022e8e75c834a49b952a66
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402137"
---
# <a name="line-number-cannot-be-parsed-using-the-current-fieldwidths"></a><span data-ttu-id="db704-102">현재 FieldWidths를 사용하여 줄 \<number>의 구문을 분석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db704-102">Line \<number> cannot be parsed using the current FieldWidths</span></span>
<span data-ttu-id="db704-103">해당 필드의 너비가 지정된 것과 다르기 때문에 지정한 줄을 구문 분석할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db704-103">The specified line cannot be parsed because its fields have widths other than those specified.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="db704-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="db704-104">To correct this error</span></span>  
  
- <span data-ttu-id="db704-105">줄을 올바르게 구문 분석할 수 있도록 `FieldWidths` 를 조정하거나 줄을 처리하도록 예외 처리 코드를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="db704-105">Adjust `FieldWidths` so the line can be parsed correctly, or insert exception-handling code in order to handle the line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db704-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db704-106">See also</span></span>

- [<span data-ttu-id="db704-107">방법: 여러 형식의 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="db704-107">How to: Read From Text Files with Multiple Formats</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)
- [<span data-ttu-id="db704-108">My.computer.filesystem.opentextfieldparser.</span><span class="sxs-lookup"><span data-stu-id="db704-108">My.Computer.FileSystem.OpenTextFieldParser</span></span>](xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFieldParser%2A)
- [<span data-ttu-id="db704-109">TextFieldParser 개체를 사용하여 텍스트 파일 구문 분석</span><span class="sxs-lookup"><span data-stu-id="db704-109">Parsing Text Files with the TextFieldParser Object</span></span>](../developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)
- [<span data-ttu-id="db704-110">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="db704-110">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
- [<span data-ttu-id="db704-111">TextFieldParser.FieldWidths 속성</span><span class="sxs-lookup"><span data-stu-id="db704-111">TextFieldParser.FieldWidths Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths%2A)
- [<span data-ttu-id="db704-112">TextFieldParser.SetFieldWidths 메서드</span><span class="sxs-lookup"><span data-stu-id="db704-112">TextFieldParser.SetFieldWidths Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A)
