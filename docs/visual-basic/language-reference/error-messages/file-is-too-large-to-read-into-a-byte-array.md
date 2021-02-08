---
description: '자세히 알아보기: 파일이 너무 커서 바이트 배열로 읽어 올 수 없습니다.'
title: 파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 8b2eb7bcbbea42c56d607147e55d6c02695c5670
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796290"
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a><span data-ttu-id="e7749-103">파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7749-103">File is too large to read into a byte array</span></span>

<span data-ttu-id="e7749-104">바이트 배열로 읽으려고 하는 파일 크기가 4gb를 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="e7749-104">The size of the file you are attempting to read into a byte array exceeds 4 GB.</span></span> <span data-ttu-id="e7749-105">`My.Computer.FileSystem.ReadAllBytes`메서드가이 크기를 초과 하는 파일을 읽을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e7749-105">The `My.Computer.FileSystem.ReadAllBytes` method cannot read a file that exceeds this size.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e7749-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e7749-106">To correct this error</span></span>  
  
- <span data-ttu-id="e7749-107">을 사용 <xref:System.IO.StreamReader> 하 여 파일을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="e7749-107">Use a <xref:System.IO.StreamReader> to read the file.</span></span> <span data-ttu-id="e7749-108">자세한 내용은 [.NET Framework 파일 i/o 및 파일 시스템의 기본 사항 (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e7749-108">For more information, see [Basics of .NET Framework File I/O and the File System (Visual Basic)](../../developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7749-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e7749-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>
- <xref:System.IO.StreamReader>
- [<span data-ttu-id="e7749-110">Visual Basic을 사용한 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="e7749-110">File Access with Visual Basic</span></span>](../../developing-apps/programming/drives-directories-files/file-access.md)
- [<span data-ttu-id="e7749-111">방법: StreamReader를 사용하여 파일에서 텍스트 읽기</span><span class="sxs-lookup"><span data-stu-id="e7749-111">How to: Read Text from Files with a StreamReader</span></span>](../../developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
