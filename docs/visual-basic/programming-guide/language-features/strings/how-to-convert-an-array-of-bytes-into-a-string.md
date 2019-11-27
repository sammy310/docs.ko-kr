---
title: '방법: 바이트 배열을 문자열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
ms.openlocfilehash: 8c1d9d1d2e89390873bc1c3dbb9623f047433a9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351983"
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a><span data-ttu-id="ea26d-102">방법: Visual Basic에서 바이트 배열을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="ea26d-102">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>
<span data-ttu-id="ea26d-103">이 항목에서는 바이트 배열의 바이트를 문자열로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-103">This topic shows how to convert the bytes from a byte array into a string.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea26d-104">예제</span><span class="sxs-lookup"><span data-stu-id="ea26d-104">Example</span></span>  
 <span data-ttu-id="ea26d-105">이 예제에서는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding 클래스의 <xref:System.Text.Encoding.GetString%2A> 메서드를 사용 하 여 바이트 배열의 모든 바이트를 문자열로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-105">This example uses the <xref:System.Text.Encoding.GetString%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert all the bytes from a byte array into a string.</span></span>  
  
 [!code-vb[VbVbalrStrings#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#72)]  
  
 <span data-ttu-id="ea26d-106">여러 인코딩 옵션 중에서 선택 하 여 바이트 배열을 문자열로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-106">You can choose from several encoding options to convert a byte array into a string:</span></span>  
  
- <span data-ttu-id="ea26d-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII (7 비트) 문자 집합에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-107"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="ea26d-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: 빅 endian 바이트 순서를 사용 하는 UTF-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-108"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="ea26d-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-109"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="ea26d-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: 작은 endian 바이트 순서를 사용 하 여 UTF-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-110"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ea26d-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: 작은 endian 바이트 순서를 사용 하 여 32 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-111"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ea26d-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-112"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="ea26d-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ea26d-113"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea26d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea26d-114">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetString%2A>
- [<span data-ttu-id="ea26d-115">방법: Visual Basic에서 문자열을 바이트 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="ea26d-115">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
