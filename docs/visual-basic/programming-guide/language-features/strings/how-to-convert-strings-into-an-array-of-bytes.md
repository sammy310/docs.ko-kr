---
description: '자세한 정보: 방법: 문자열을 Visual Basic 바이트 배열로 변환'
title: '방법: 문자열을 바이트 배열로 변환'
ms.date: 07/20/2015
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- arrays [Visual Basic], converting strings to
- byte arrays
- examples [Visual Basic], string conversion
- arrays [Visual Basic], byte arrays
ms.assetid: f477d35c-a3fc-4a30-b1d4-cd0d353aae1d
ms.openlocfilehash: edd41bc1dd7026c5b4ed061211f4b7884cd6044a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429848"
---
# <a name="how-to-convert-strings-into-an-array-of-bytes-in-visual-basic"></a><span data-ttu-id="ffaed-103">방법: Visual Basic에서 문자열을 바이트 배열로 변환</span><span class="sxs-lookup"><span data-stu-id="ffaed-103">How to: Convert Strings into an Array of Bytes in Visual Basic</span></span>

<span data-ttu-id="ffaed-104">이 항목에서는 문자열을 바이트 배열로 변환 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-104">This topic shows how to convert a string into an array of bytes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ffaed-105">예</span><span class="sxs-lookup"><span data-stu-id="ffaed-105">Example</span></span>  

 <span data-ttu-id="ffaed-106">이 예제에서는 <xref:System.Text.Encoding.GetBytes%2A> encoding 클래스의 메서드를 사용 하 여 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> 문자열을 바이트 배열로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-106">This example uses the <xref:System.Text.Encoding.GetBytes%2A> method of the <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> encoding class to convert a string into an array of bytes.</span></span>  
  
 [!code-vb[VbVbalrStrings#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#74)]  
  
 <span data-ttu-id="ffaed-107">여러 인코딩 옵션 중에서 선택 하 여 문자열을 바이트 배열로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-107">You can choose from several encoding options to convert a string into a byte array:</span></span>  
  
- <span data-ttu-id="ffaed-108"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: ASCII (7 비트) 문자 집합에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-108"><xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: Gets an encoding for the ASCII (7-bit) character set.</span></span>  
  
- <span data-ttu-id="ffaed-109"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: 빅 endian 바이트 순서를 사용 하는 UTF-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-109"><xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the big-endian byte order.</span></span>  
  
- <span data-ttu-id="ffaed-110"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-110"><xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: Gets an encoding for the system's current ANSI code page.</span></span>  
  
- <span data-ttu-id="ffaed-111"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: 작은 endian 바이트 순서를 사용 하 여 UTF-16 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-111"><xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-16 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ffaed-112"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: 작은 endian 바이트 순서를 사용 하 여 32 UTF-8 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-112"><xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-32 format using the little-endian byte order.</span></span>  
  
- <span data-ttu-id="ffaed-113"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: UTF-7 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-113"><xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-7 format.</span></span>  
  
- <span data-ttu-id="ffaed-114"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: UTF-8 형식에 대 한 인코딩을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ffaed-114"><xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Gets an encoding for the UTF-8 format.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffaed-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ffaed-115">See also</span></span>

- <xref:System.Text.Encoding?displayProperty=nameWithType>
- <xref:System.Text.Encoding.GetBytes%2A>
- [<span data-ttu-id="ffaed-116">방법: Visual Basic에서 바이트 배열을 문자열로 변환</span><span class="sxs-lookup"><span data-stu-id="ffaed-116">How to: Convert an Array of Bytes into a String in Visual Basic</span></span>](how-to-convert-an-array-of-bytes-into-a-string.md)
