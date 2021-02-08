---
description: '자세한 정보: 마지막 요소를 제외한 모든 필드 너비는 0 보다 커야 합니다.'
title: 마지막 요소를 제외한 모든 필드 너비는 0보다 커야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: cf2edb21f017031c7dd333893d554353eceebe73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787385"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a><span data-ttu-id="49743-103">마지막 요소를 제외한 모든 필드 너비는 0보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49743-103">All field widths, except the last element, must be greater than zero</span></span>

<span data-ttu-id="49743-104">마지막 요소를 제외한 모든 필드 너비는 0보다 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49743-104">All field widths, except the last element, must be greater than zero.</span></span> <span data-ttu-id="49743-105">마지막 요소의 0보다 작거나 같은 필드 너비는 마지막 필드가 가변 길이임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="49743-105">A field width less than or equal to zero in the last element indicates the last field is of variable length.</span></span>  
  
 <span data-ttu-id="49743-106">마지막 요소 이외의 다른 필드 너비가 0 이하로 설정되었으므로 작업이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="49743-106">The operation has failed because a field width other than the last element is set to zero or less.</span></span> <span data-ttu-id="49743-107">0보다 작거나 같은 필드 너비를 마지막 요소로 사용하여 마지막 필드가 가변 길이임을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49743-107">A field width less than or equal to zero can be used as the last element to indicate that the last field is of variable length, but it cannot be used as any other element.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="49743-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="49743-108">To correct this error</span></span>  
  
- <span data-ttu-id="49743-109">필드 너비를 올바른 길이로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="49743-109">Set the field width to the correct length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49743-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49743-110">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [<span data-ttu-id="49743-111">방법: 고정 너비 텍스트 파일에서 읽기</span><span class="sxs-lookup"><span data-stu-id="49743-111">How to: Read From Fixed-width Text Files</span></span>](../developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="49743-112">TextFieldParser Object</span><span class="sxs-lookup"><span data-stu-id="49743-112">TextFieldParser Object</span></span>](../language-reference/objects/textfieldparser-object.md)
