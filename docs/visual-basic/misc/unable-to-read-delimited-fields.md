---
title: EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: 29682edb78b848897ac2999f2d84dc1a9c1a3367
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100361"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="c96b1-102">EscapeQuotes가 True로 설정되어 있으면 큰따옴표가 올바른 구분 기호가 아니므로 구분된 필드를 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c96b1-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>

<span data-ttu-id="c96b1-103">`TextFieldParser` 는 따옴표(")가 구분 기호로 제공되고 `EscapeQuotes` 가 `True`로 설정되므로 파일에서 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c96b1-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c96b1-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c96b1-104">To correct this error</span></span>  
  
- <span data-ttu-id="c96b1-105">`EscapeQuotes`를 `False`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c96b1-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96b1-106">참조</span><span class="sxs-lookup"><span data-stu-id="c96b1-106">See also</span></span>

- [<span data-ttu-id="c96b1-107">TextFieldParser.SetDelimiters 메서드</span><span class="sxs-lookup"><span data-stu-id="c96b1-107">TextFieldParser.SetDelimiters Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [<span data-ttu-id="c96b1-108">TextFieldParser.Delimiters 속성</span><span class="sxs-lookup"><span data-stu-id="c96b1-108">TextFieldParser.Delimiters Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [<span data-ttu-id="c96b1-109">방법: 쉼표로 구분된 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="c96b1-109">How to: Read From Comma-Delimited Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="c96b1-110">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="c96b1-110">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
