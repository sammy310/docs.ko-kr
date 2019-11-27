---
title: '방법: 문자열을 바이트 배열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: 76fde3120ce629ce32f29ca28d90eba24fff726c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351966"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="75e75-102">방법: Visual Basic에서 문자열을 바이트 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="75e75-102">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>
<span data-ttu-id="75e75-103">이 항목에서는 문자열을 바이트 배열로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-103">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75e75-104">예제</span><span class="sxs-lookup"><span data-stu-id="75e75-104">Example</span></span>  
 <span data-ttu-id="75e75-105">이 예제에서는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding 클래스의 <xref:System.Text.Encoding.GetBytes%2A> 메서드를 사용 하 여 문자열을 바이트 배열로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-105">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="75e75-106">여러 인코딩 옵션 중에서 선택 하 여 문자열을 바이트 배열로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-106">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="75e75-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII (7 비트) 문자 집합에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="75e75-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: 빅 endian 바이트 순서를 사용 하는 UTF-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="75e75-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="75e75-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: 작은 endian 바이트 순서를 사용 하 여 UTF-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="75e75-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: 작은 endian 바이트 순서를 사용 하 여 32 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="75e75-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="75e75-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="75e75-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75e75-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75e75-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="75e75-115">방법: 바이트 배열을 Visual Basic의 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="75e75-115">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-an-array-of-bytes-into-a-string.md)
