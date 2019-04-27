---
title: 파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 0c7d35e08eeb42e35c4c40e47434a64393d829b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800882"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="4aca1-102">파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aca1-102">File is too large to read into a byte array</span></span>
<span data-ttu-id="4aca1-103">바이트 배열로 읽어 들일 하려는 파일의 크기는 4GB를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="4aca1-103">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="4aca1-104">`My.Computer.FileSystem.ReadAllBytes` 메서드는이 크기를 초과 하는 파일을 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4aca1-104">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4aca1-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="4aca1-105">To correct this error</span></span>  
  
-   <span data-ttu-id="4aca1-106">사용 된 <xref:System.IO.StreamReader> 파일을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4aca1-106">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="4aca1-107">자세한 내용은 [기본 사항의.NET Framework 파일 I/O 및 파일 시스템 (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4aca1-107">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4aca1-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="4aca1-108">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="4aca1-109">Visual Basic을 사용한 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="4aca1-109">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="4aca1-110">방법: StreamReader 사용 하 여 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="4aca1-110">How to: Read Text from Files with a StreamReader</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
