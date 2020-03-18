---
title: '방법: 디렉터리 복사'
ms.date: 12/27/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET Framework], copying directories
- subdirectory copying
- copying directories
- directories [.NET Framework], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: 5d40db7f902dac8bd6bbdc1510be8e56a321be30
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "78159457"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="9670b-102">방법: 디렉터리 복사</span><span class="sxs-lookup"><span data-stu-id="9670b-102">How to: Copy directories</span></span>
<span data-ttu-id="9670b-103">이 항목에서는 I/O 클래스를 사용하여 디렉터리의 내용을 다른 위치로 동기적으로 복사하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9670b-103">This topic demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span>

<span data-ttu-id="9670b-104">비동기 파일 복사의 예제는 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9670b-104">For an example of asynchronous file copy, see [Asynchronous file I/O](../../../docs/standard/io/asynchronous-file-i-o.md).</span></span>

<span data-ttu-id="9670b-105">이 예제는 `DirectoryCopy` 메서드의 `copySubDirs`를 `true`로 설정하여 하위 디렉터리를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9670b-105">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="9670b-106">`DirectoryCopy` 메서드는 더 이상 복사할 항목이 없을 때까지 각 하위 디렉터리에서 자신을 호출하여 하위 디렉터리를 재귀적으로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="9670b-106">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9670b-107">예제</span><span class="sxs-lookup"><span data-stu-id="9670b-107">Example</span></span>  
 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a><span data-ttu-id="9670b-108">참조</span><span class="sxs-lookup"><span data-stu-id="9670b-108">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="9670b-109">파일 및 스트림 I/O</span><span class="sxs-lookup"><span data-stu-id="9670b-109">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
- [<span data-ttu-id="9670b-110">공통 I/O 작업</span><span class="sxs-lookup"><span data-stu-id="9670b-110">Common I/O tasks</span></span>](../../../docs/standard/io/common-i-o-tasks.md)
- [<span data-ttu-id="9670b-111">비동기 파일 I/O</span><span class="sxs-lookup"><span data-stu-id="9670b-111">Asynchronous file I/O</span></span>](../../../docs/standard/io/asynchronous-file-i-o.md)
