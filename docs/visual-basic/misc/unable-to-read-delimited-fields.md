---
title: EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: ca764d5258daf54a7149661549a78b3aca709718
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619809"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="f03b9-102">EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f03b9-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>
<span data-ttu-id="f03b9-103">`TextFieldParser` 는 따옴표(")가 구분 기호로 제공되고 `EscapeQuotes` 가 `True`로 설정되므로 파일에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f03b9-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f03b9-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f03b9-104">To correct this error</span></span>  
  
- <span data-ttu-id="f03b9-105">`EscapeQuotes`를 `False`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f03b9-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f03b9-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="f03b9-106">See also</span></span>

- [<span data-ttu-id="f03b9-107">TextFieldParser.SetDelimiters 메서드</span><span class="sxs-lookup"><span data-stu-id="f03b9-107">TextFieldParser.SetDelimiters Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [<span data-ttu-id="f03b9-108">TextFieldParser.Delimiters Property</span><span class="sxs-lookup"><span data-stu-id="f03b9-108">TextFieldParser.Delimiters Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [<span data-ttu-id="f03b9-109">방법: 쉼표로 구분된 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="f03b9-109">How to: Read From Comma-Delimited Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="f03b9-110">TextFieldParser 개체</span><span class="sxs-lookup"><span data-stu-id="f03b9-110">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
