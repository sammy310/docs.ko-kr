---
title: '방법: Visual Basic의 문자열 바이트 배열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: f0676548bea2d4037f66fb15498c175b2d110d8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024627"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="3bf2a-102">방법: Visual Basic의 문자열 바이트 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="3bf2a-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="3bf2a-103">이 항목에는 바이트 배열에서 바이트를 문자열로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bf2a-104">예제</span><span class="sxs-lookup"><span data-stu-id="3bf2a-104">Example</span></span>  
 <span data-ttu-id="3bf2a-105">이 예제에서는 합니다 <xref:System.Text.Encoding.GetString%2A> 메서드는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> 인코딩 바이트 배열에서 모든 바이트를 문자열로 변환 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="3bf2a-106">바이트 배열을 문자열로 변환 하려면 여러 인코딩 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="3bf2a-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII(7비트) 문자 집합에 대한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="3bf2a-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Big endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="3bf2a-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="3bf2a-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="3bf2a-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하 여 UTF-32 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="3bf2a-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 형식에 대한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="3bf2a-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 형식에 대한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3bf2a-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bf2a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="3bf2a-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="3bf2a-115">방법: Visual Basic에서 바이트 배열을 문자열 변환</span><span class="sxs-lookup"><span data-stu-id="3bf2a-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
